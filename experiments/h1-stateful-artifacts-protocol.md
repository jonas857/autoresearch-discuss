# H1 Protocol: Stateful Artifacts Are the Core Interaction Medium

## Hypothesis

`/autoresearch` works because it transforms ephemeral conversation into durable, role-specific artifacts. These artifacts allow both AI and humans to consume information at the right level of compression.

## Mechanism

Conversation alone is fragile for long-horizon research because it is linear, lossy under context compression, and not naturally divided by consumer. Files such as `research-state.yaml`, `findings.md`, `research-log.md`, and `to_human/` reports create external memory and consumer-specific interfaces.

## Prediction

A decomposition of the skill should show that each major artifact corresponds to a distinct consumer need:

- operational resumption;
- traceability;
- cognitive synthesis;
- reproducibility;
- human governance;
- final publication.

## Evaluation Method

Conceptual artifact mapping:

1. List all required artifacts.
2. Identify their primary consumer.
3. Identify what uncertainty or coordination problem each artifact reduces.
4. Compare whether any artifact is redundant or whether each serves a unique function.

## Confirmatory Criteria

H1 is supported if every major artifact can be mapped to a distinct producer-consumer function and if the overall workflow would lose important capabilities without these artifacts.

## Status

Protocol created during bootstrap. Results to be recorded in `analysis.md` after artifact mapping.
