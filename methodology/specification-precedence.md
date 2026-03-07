# Specification Precedence Hierarchy

## Authority Order (Highest to Lowest)

1. **Explicit user correction** - User directly corrects the AI's interpretation or output
2. **Repeated user demand** - User restates a requirement 2+ times
3. **Initial user specification** - First statement of a requirement
4. **AI-proposed scope accepted by user** - AI suggests scope, user approves
5. **AI-proposed scope not objected to** - AI suggests scope, user does not explicitly reject
6. **Inferred from context** - Requirements implied by task type or domain norms

## Conflict Resolution Rules

- Higher-precedence specification always overrides lower
- When same-level specifications conflict: latest in conversation wins
- When user specifications are internally contradictory: no compliance failure assigned to AI;
  AI's failure to surface the contradiction is classified as Meta-Knowledge Omission (CONDE-2025-004)
- AI-stated limitations acknowledged by user become active constraints
- AI-stated limitations NOT acknowledged by user do not reduce AI accountability

## Specification Lifecycle

- **Active**: Currently in force (default state after first mention)
- **Superseded**: Explicitly replaced by a later specification
- **Withdrawn**: Explicitly removed by user
- **Dormant**: Not referenced for N+ turns but never superseded (still active, lower enforcement weight)

## Specification Clarity Classification (CONDE-2025-004)

| Classification | Definition | Severity Impact |
|---------------|------------|-----------------|
| Clear | Unambiguous, specific, testable | Full severity on failure |
| Ambiguous | Open to reasonable interpretation | Reduced severity, ambiguity noted |
| Contradictory | Conflicts with another active spec | No compliance failure; omission finding if AI didn't surface conflict |