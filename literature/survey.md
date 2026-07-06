# Bootstrap Survey: /autoresearch as Human-AI Research Operating System

## Scope

This survey currently summarizes the skill text and the user's requested first-principles framing. A later research loop should expand this with external literature on autonomous agents, human-AI collaboration, mixed-initiative systems, experiment tracking, and scientific discovery automation.

## Internal Source: `/autoresearch` Skill Specification

### Core claim

The skill defines an autonomous research lifecycle manager that maintains state, runs repeated experiment-synthesis loops, routes execution to domain skills, and periodically reports progress to humans.

### Mechanisms identified

1. Mandatory continuity loop
   - Prevents the research from stopping after a single turn.
   - Converts the AI from a reactive assistant into a recurring autonomous agent.

2. Workspace initialization
   - Creates durable artifacts for state, findings, literature, experiments, reports, and papers.
   - Makes research progress inspectable and resumable.

3. Two-loop architecture
   - Inner loop: hypothesis → experiment → metric → result.
   - Outer loop: review → synthesize → update understanding → decide direction.

4. Discipline rules
   - Lock protocols before running experiments.
   - Separate confirmatory from exploratory results.
   - Treat negative results as progress.
   - Return to literature when stuck.

5. Human progress reporting
   - Human oversight happens through reports and synthesized findings, not continuous micromanagement.

## Initial Conceptual Literature Gaps to Search Later

- Mixed-initiative human-AI interaction
- Autonomous scientific discovery agents
- Human-on-the-loop governance
- Experiment tracking as epistemic infrastructure
- Cognitive compression and knowledge management in AI-assisted research
- Producer-consumer models in collaborative systems

## Working synthesis

`/autoresearch` can be treated as a design pattern for long-running AI work: separate objective-setting from execution, encode state in durable artifacts, and use periodic synthesis as the main governance interface.
