# H4 Protocol: Progress Reports Are the Primary Governance Interface

## Hypothesis

Progress reports are the primary human governance interface in `/autoresearch`. They are not merely presentation artifacts; they are the mechanism by which humans consume compressed meaning, evaluate direction, and update the value signal without micromanaging the AI.

## Mechanism

Long-running AI research requires autonomy at the execution level but accountability at the direction level. Human-facing reports solve this by translating internal artifacts (`research-state.yaml`, `findings.md`, `experiments/`, `literature/`) into a decision-oriented interface.

## Prediction

A governance report should contain enough information for a human to answer:

1. Is the research still pursuing the right objective?
2. Is the AI producing understanding rather than activity?
3. What evidence supports the current claims?
4. What uncertainties remain?
5. What decision or feedback is needed from the human?
6. Should the project deepen, broaden, pivot, or conclude?

## Evaluation Method

1. Map report fields to governance functions.
2. Identify failure modes caused by missing or poor reports.
3. Compare report-based governance against micromanagement and full autonomy.
4. Derive a reusable progress report template.

## Confirmatory Criteria

H4 is supported if reports can be shown to close the human loop in the broader Stateful Value-Signal Research Loop:

```text
AI meaning synthesis → human report → human value-signal update → AI reprioritization
```
