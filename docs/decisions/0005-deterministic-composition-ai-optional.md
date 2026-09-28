# 0005. Deterministic, rule-based composition; AI only as an optional adapter

- **Status:** Proposed
- **Date:** 2026-09-28

## Context

The project aims to assemble complete lessons from reusable components. That could be done by asking a large language model to "write a lesson." The project principles reject that as the core idea: teachers are the experts, AI is optional infrastructure, and the project must be useful without an AI API.

## Decision

- **Composition is deterministic and rule-based.** The composer fills a template's slots with library components by filtering (type, grade range, slot constraints) and scoring (objective, standard, topic, supports, review status). Ties break by ID, so the same library and request always produce the same draft.
- **Composition is explainable.** Every choice comes with its reasons and alternatives. Every unfilled slot is reported as a gap, which doubles as a contribution opportunity.
- **Composition produces drafts.** Output is an editable `lesson_plan` file with `status: draft`. The teacher decides what to use.
- **AI, if added later, is an adapter:** a separate, optional module behind a narrow interface, off by default, with no AI dependencies in the core. Its output is draft components that go through the same validation, `ai_assisted: true` labeling, and human review as any contribution. The interface will be designed in its own ADR after the deterministic engine is proven.

## Consequences

- The whole system works offline, costs nothing to run, and has no API keys to manage.
- Results are reproducible and testable.
- Composition quality depends on the library's size and metadata. That makes contributions and good metadata more valuable, which fits the project's community focus.
- The composer can't write new content. Gaps are filled by teachers, or later by an optional adapter.

## Alternatives considered

- **LLM-first generation:** fast to demo, but it makes the AI the product. It requires paid APIs, produces unverifiable content, and sidelines teacher expertise.
- **Embedding or semantic search for matching:** possibly useful later for discovery. Structured metadata comes first because it is transparent and free.
