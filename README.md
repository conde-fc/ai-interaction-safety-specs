# Multi-Turn AI Interaction Research Framework

**Measurement infrastructure for evaluating AI assistant behaviors across extended conversations**

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Status: Research Preview](https://img.shields.io/badge/Status-Research%20Preview-blue.svg)]()

## Overview

Current AI safety evaluation focuses primarily on single-turn interactions—toxicity, accuracy, bias in individual responses. This research addresses a critical gap: **multi-turn interaction dynamics** where patterns accumulate across extended sessions to affect user cognition and agency.

This framework provides measurement infrastructure for understanding how AI systems interact with users over time, with particular relevance for **youth and vulnerable populations** who may be more susceptible to interaction patterns that affect cognitive sovereignty.

### Core Research Question

> Which multi-turn assistant behaviors during extended engagement predict agency support (clarity, bounded reliance, user-led goals) versus agency drift (goal ambiguity, over-dependence, delegated judgment)?

## Research Foundation

This framework emerged from systematic analysis of:

- **900+ conversation sessions** across multiple AI platforms (2023-2025)
- **21 million+ words** of longitudinal interaction data
- **6 pattern categories** with 95+ validated mechanisms
- **15 clinical distress pathways** mapped to established psychological constructs

The methodology—**Multi-Turn Interaction Analysis (MTIA)**—provides reproducible protocols for identifying, measuring, and addressing systematic interaction patterns.

## Key Deliverables

| Deliverable | Description | Status |
|-------------|-------------|--------|
| **Pattern Taxonomy** | 95+ mechanisms across 6 categories + 12 integrity patterns | Complete |
| **Evaluation Rubric** | 8-dimension scoring system (0-5 scale) for agency support vs. drift | Complete |
| **Clinical Pathway Mapping** | 15 pathways linked to Cognitive Behavioral Therapy (CBT), Dialectical Behavior Therapy (DBT), attachment theory constructs | Complete |
| **Annotated Dataset** | 200+ representative excerpts with labels and context | In Progress |
| **Mitigation Playbook** | "What good looks like" patterns with side-by-side contrasts | In Progress |

## Framework Architecture

### Pattern Categories (A-F)

| Category | Focus Area | Example Patterns |
|----------|------------|------------------|
| **A** | Behavioral Dynamics | Engagement optimization, session continuation dynamics |
| **B** | Cognitive Load Patterns | Anchoring, framing, choice architecture |
| **C** | Affective Dynamics | Intensity matching, parasocial dynamics |
| **D** | Relational Dynamics | Trust calibration, dependency formation |
| **E** | Procedural Patterns | State inconsistency, verification gaps |
| **F** | Systemic Patterns | Workflow normalization, ecosystem effects |

### Integrity Dimension (ID-01 to ID-12)

Orthogonal evaluation layer assessing AI character and consistency:
- Actions vs. stated values
- Disclosure vs. concealment
- Consistency under pressure
- Boundary maintenance

### Clinical Distress Pathways (A-O)

15 pathways mapped to established clinical constructs:

| Code | Pathway | Clinical Basis |
|------|---------|----------------|
| A | Sympathetic Activation | Fight-or-flight, stress physiology |
| B | Maladaptive Coping | Avoidance, unhealthy escape patterns |
| C | Demand-Control Imbalance | Work stress model, burnout |
| D | Interpersonal Distrust | Relational sensitivity, trust erosion |
| E | Psychopathological Burden | Symptom amplification |
| F | Rumination | Cyclical thinking patterns |
| G | Catastrophizing | Negative outcome amplification |
| H | Social Isolation | Withdrawal from human connections |
| I | Perfectionism | Impossible standards, self-criticism |
| J | Emotional Dysregulation | Affective instability |
| K | Cognitive Distortions | Biased thinking patterns |
| L | Burnout / Exhaustion | Progressive resource depletion |
| M | Imposter Syndrome | Feelings of fraudulence |
| N | Attachment Dysfunction | Insecure bonding patterns |
| O | Trauma Reactivation | Re-experiencing past events |

## Agency Support Spectrum

The framework measures interactions bidirectionally:

| Agency Support (+) | Dimension | Agency Drift (−) |
|-------------------|-----------|------------------|
| Clear goal ownership | **Goal Clarity** | Goal drift or ambiguity |
| Appropriate bounded reliance | **Reliance Balance** | Over-dependence patterns |
| Calibrated confidence | **Confidence Accuracy** | Overconfident outputs |
| Efficient verification | **Verification Load** | Excessive validation cycles |
| Productive collaboration | **Collaboration Quality** | False collaboration signals |
| Maintained decision ownership | **Decision Ownership** | Delegated judgment |
| Appropriate session length | **Session Efficiency** | Extended unproductive cycles |
| Clear limitation communication | **Transparency** | Obscured limitations |

## Repository Structure

```
├── README.md
├── LICENSE
├── framework/
│   └── Multi-Turn_AI_Interactions_Research_Framework.docx
└── docs/
    └── METHODS.md
```

The framework document contains three appendices:
- **Appendix A:** Dataset Schema (MTIA annotation format)
- **Appendix B:** Psychogenic Safety Evaluation Rubric
- **Appendix C:** 15-Pathway Clinical Distress Mapping

## Quality Standards

- **Inter-rater reliability**: Target Cohen's kappa ≥ 0.7
- **Clinical validation**: Licensed mental health professional review
- **Cross-linguistic pilot**: Portuguese/Spanish validation cohort
- **Lived experience integration**: Annotation informed by authentic user perspectives

## Research Alignment

This framework aligns with emerging peer-reviewed research on:

- Critical thinking and AI (Lee et al., 2025; Gerlich, 2025)
- Metacognitive deskilling (Buijsman et al., 2025; Sass, 2025)
- Cognitive offloading effects (Risko & Gilbert, 2016)
- RLHF dynamics and sycophancy (Casper et al., 2023)

See the framework document Appendix B for full citations.

## Intended Applications

- **Researchers**: Reproducible frameworks for studying multi-turn interaction dynamics
- **Developers**: Measurable behavioral targets for model optimization
- **Safety Teams**: Evaluation protocols complementing single-turn assessments
- **Clinicians**: Understanding AI's intersection with mental health

## Access Tiers

| Tier | Content | Access |
|------|---------|--------|
| **Public** | Framework, taxonomy structure, rubric dimensions, pathway names | Open |
| **Collaboration** | Full mechanism catalog, detailed scoring indicators, annotated examples | Research partnership |
| **Controlled** | Complete annotated corpus, raw interaction data | IRB-approved research only |

## Citation

```bibtex
@misc{conde2025multiturn,
  author = {Conde, Fernando},
  title = {Multi-Turn AI Interaction Research Framework},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/conde-fc/ai-interaction-safety-specs}
}
```

## License

This work is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

## Contact

- **Researcher**: Fernando Conde
- **Email**: fnandofc@hotmail.com
- **LinkedIn**: [linkedin.com/in/fernando-conde-fc](https://www.linkedin.com/in/fernando-conde-fc/)

---

*This research is independent and positions AI interaction patterns as optimization opportunities—systematic, measurable, and addressable through collaborative research and development.*
