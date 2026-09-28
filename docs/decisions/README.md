# Architecture Decision Records

An Architecture Decision Record (ADR) is a short document that records one significant decision: what was decided, why, and what else was considered. ADRs keep major choices out in the open. Nobody has to guess why something is the way it is, and anybody can propose changing it.

| ADR | Decision | Status |
| --- | --- | --- |
| [0001](0001-content-as-code.md) | Store components as YAML files in git; no database or server | Proposed |
| [0002](0002-typescript-zod-json-schema.md) | TypeScript, with Zod schemas exported to JSON Schema | Proposed |
| [0003](0003-licensing.md) | MIT for software; CC BY 4.0 for educational content | Proposed |
| [0004](0004-no-student-data.md) | No student data, permanently | Proposed |
| [0005](0005-deterministic-composition-ai-optional.md) | Deterministic, rule-based composition; AI only as an optional adapter | Proposed |

## Statuses

- **Proposed**: written and open for feedback.
- **Accepted**: merged by a maintainer with no outstanding objections.
- **Superseded by NNNN**: replaced by a later ADR. Old ADRs are never deleted; they are the project's memory.

## When to write one

Write an ADR before you:

- change the component file format in a breaking way
- add a component type
- add a major dependency or a new interface (for example a website, a server, or an AI adapter)
- change licensing
- do anything that affects the principles in [DEVELOPMENT.md §2](../../DEVELOPMENT.md#2-philosophy)

## Template

Copy this into `docs/decisions/NNNN-short-title.md` and open a pull request:

```markdown
# NNNN. Title

- **Status:** Proposed
- **Date:** YYYY-MM-DD

## Context
What problem are we solving? What constraints matter?

## Decision
What we will do.

## Consequences
What gets easier, what gets harder, and what we'll need to watch.

## Alternatives considered
The other options and why they weren't chosen.
```
