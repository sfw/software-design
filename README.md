# PRD + Software Design Process for Loom

A [Loom](https://github.com/sfw/loom) process package that turns a project goal
into a full Product Requirements Document (PRD) and Software Design
Specification handoff package for implementation teams and agentic engineers.

## What this process does

This package runs a strict 8-phase workflow:

1. Intake and stakeholder interview (`ask_user` driven)
2. Context and constraints discovery
3. Requirements and success metrics authoring (PRD core)
4. User experience and scope design
5. Software architecture and data design
6. Quality, security, and operations design
7. Implementation planning and ADR logging
8. Final traceability and handoff synthesis

## Human-in-the-loop behavior

The intake phase explicitly uses `ask_user` to gather structured answers with a
`Yes/No/Custom` pattern for decision-critical questions.

Expected behavior:

- Prefer asking over guessing for critical unknowns.
- For `Custom` responses, ask one immediate follow-up clarification.
- Persist responses into `interview-log.csv` and derive assumptions/open
  questions when answers are missing.

## New schema usage

This package uses updated process definition fields:

- `risk_level`
- process-level `validity_contract`
- phase-level `validity_contract` override on synthesis
- phase `iteration` gates on final handoff quality

## Installation

From a local path:

```bash
loom install /Users/sfw/Development/software-design
```

Install into a specific workspace:

```bash
loom install /Users/sfw/Development/software-design -w /path/to/project
```

## Usage

Interactive cowork mode:

```bash
loom cowork --process prd-software-design
```

Then run:

```text
/run Create a PRD and software design specification for a customer self-serve billing portal with subscription upgrades, invoice management, and role-based approvals.
```

This process is optimized for interactive cowork sessions so intake questions
can be answered by a human. If run non-interactively, unresolved interview
items should be treated as assumptions pending confirmation.

## Core deliverables

- `project-intake.md`
- `interview-log.csv`
- `decision-register.csv`
- `assumptions-and-open-questions.md`
- `context-brief.md`
- `existing-system-inventory.csv`
- `constraints-register.csv`
- `prd.md`
- `requirements-catalog.csv`
- `success-metrics.md`
- `non-functional-requirements.csv`
- `user-journeys.md`
- `user-story-map.csv`
- `release-scope-plan.csv`
- `software-design-spec.md`
- `architecture-view.md`
- `data-model-and-state.md`
- `api-and-integration-contracts.md`
- `test-strategy.md`
- `quality-attributes-and-slos.md`
- `security-and-compliance-plan.md`
- `observability-and-runbooks.md`
- `implementation-roadmap.md`
- `agent-execution-plan.csv`
- `adr-log.md`
- `dependency-and-risk-register.csv`
- `requirements-traceability-matrix.csv`
- `specification-package.md`
- `handoff-checklist.md`

## Verification highlights

The process enforces checks for:

- interview completeness and structured intake coverage
- requirement testability and specificity
- non-functional requirement coverage
- architecture-to-requirement alignment
- security/operations implementation readiness
- execution-plan granularity for agentic implementation
- end-to-end traceability
- no placeholder content (`[TBD]`, `[TODO]`, `[INSERT]`, `[PLACEHOLDER]`)

## Testing

Run deterministic package test:

```bash
loom process test /Users/sfw/Development/software-design --case smoke
```

Run live canary test:

```bash
loom process test /Users/sfw/Development/software-design --live
```

## License

MIT
