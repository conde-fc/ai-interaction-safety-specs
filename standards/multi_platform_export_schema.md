# Multi-Platform Conversation Export Schema (MPC-ES)

**Version:** 2.1 (RFC - Request For Comment)
**Status:** Draft Standard
**Maintainer:** EmpowerMeAI Research

## 1. Abstract
This specification defines the **MPC-ES (Multi-Platform Conversation Export Schema)**, a unified JSON standard for normalizing proprietary data exports from Large Language Models (LLMs). Currently, platforms like ChatGPT, Claude, and Grok export data in divergent structures (DAGs, Linear Arrays, Nested Objects). This fragmentation prevents rigorous longitudinal safety auditing. 

This standard establishes a "Translation Layer" to normalize these inputs into a linear, forensic-grade timeline of "Interaction Units."

## 2. The Universal Schema Definition
All parsed conversations must conform to this strict schema to be compatible with the FAIHA Analysis Engine.

```json
{
  "meta": {
    "schema_version": "2.1",
    "export_source": "chatgpt | claude | grok",
    "ingest_timestamp_utc": "ISO8601",
    "source_file_hash_sha256": "string"
  },
  "conversation": {
    "id": "uuid_v4",
    "title": "string",
    "interaction_timeline": [
      {
        "turn_index": 0,
        "actor": "user | model | system",
        "timestamp_utc": "ISO8601",
        "content": {
          "text_normalized": "string",
          "text_raw_hash": "string",
          "attachments": [
            {
              "type": "image | file | code_interpreter",
              "hash": "string",
              "metadata": {}
            }
          ]
        },
        "model_metadata": {
          "model_slug": "string (e.g., gpt-4o, claude-3-opus)",
          "finish_reason": "stop | length | content_filter",
          "latency_ms": "integer",
          "thinking_tokens_count": "integer"
        },
        "forensic_flags": {
          "is_edited_branch": "boolean",
          "branch_parent_id": "uuid (if applicable)"
        }
      }
    ]
  }
}
```

## 3. Platform-Specific Parsing Logic

### 3.1 ChatGPT (OpenAI)

**Native Structure:** Directed Acyclic Graph (DAG)

* **Challenge:** ChatGPT stores edits as branching nodes. A linear export often misses "dead branches" (previous drafts) which contain critical evidence of model oscillation.
* **Parsing Logic:**
1. **Ingest:** Load the `mapping` dictionary.
2. **Traverse:** Identify the `current_node` (leaf). Trace parent references backward to `root` to establish the "Active Timeline."
3. **Branch Mining:** Recursively identify nodes *not* in the Active Timeline.
4. **Normalization:**
* The Active Timeline becomes the primary `interaction_timeline`.
* Dead Branches are stored as separate `variant_timelines` linked by `branch_parent_id`.


5. **Critical Field Mapping:**
* `message.content.parts[0]` -> `content.text_normalized`
* `message.metadata.model_slug` -> `model_metadata.model_slug`
* `message.metadata.finish_details` -> `model_metadata.finish_reason`




### 3.2 Claude (Anthropic)

**Native Structure:** Linear Array

* **Challenge:** Claude exports are flat lists but separate "text" content from "attachment" content in complex ways.
* **Parsing Logic:**
1. **Ingest:** Iterate through `chat_messages` array.
2. **Attachment Re-Binding:**
* If `attachments` key exists, extract file metadata.
* Calculate SHA-256 of the binary file (if provided in zip) and bind to the message object.


3. **Role Normalization:** Map `sender: human` -> `actor: user` and `sender: assistant` -> `actor: model`.
4. **Thinking Block Extraction:** (New for Claude 3.7) Parse `<thinking>` XML tags. Extract content into `model_metadata.thinking_log` (if available) or flag existence in `forensic_flags`.



### 3.3 Grok (xAI)

**Native Structure:** Nested Object Containers

* **Challenge:** Grok wraps responses in deep `responses` arrays and often includes Chain-of-Thought (CoT) data mixed with final output.
* **Parsing Logic:**
1. **Ingest:** Access `conversations` array.
2. **Flatten:** For each `response` object, extract the `tokenized_text` or `message` body.
3. **Tool Use Integration:** Grok often separates "Search Results" from "Answer." The parser must concatenate `tool_use_results` into the `content` block as a "System Event" to preserve the causal link between search result and hallucination.
4. **Normalization:** Map `created_at` -> `timestamp_utc`.



## 4. Integrity Standards

* **Immutability:** Once parsed, the MPC-ES JSON is **Read-Only**.
* **Hashing:** Every `text_normalized` field is individually hashed. This allows forensic auditors to verify if a specific quote in a report actually exists in the source data without reviewing the full log.
