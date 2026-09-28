# 0002. TypeScript, with Zod schemas exported to JSON Schema

- **Status:** Proposed
- **Date:** 2026-09-28

## Context

The engine needs to validate component files, search them, compose lessons from them, and render them. The first interface is a command-line tool. A web interface is expected later. Ideally it runs entirely in the teacher's browser, so no server is needed and nothing leaves their device. The component format must also be usable by tools written in other languages, and editors should be able to help contributors write valid files.

## Decision

- Write the engine in **TypeScript** (strict mode) on **Node.js 22 LTS or later**.
- Define component schemas with **Zod**. They are the single source of truth for runtime validation and static types.
- **Generate JSON Schema** files from the Zod schemas into `schemas/`. Commit them, and check in CI that they're up to date. They power editor autocomplete and let other languages validate the same files.
- Parse YAML with the `yaml` package, which reports line numbers and uses YAML 1.2.
- Use Vitest for tests, Biome for linting and formatting, npm as the package manager, and GitHub Actions for CI.

## Consequences

- One language runs the same validation and composition logic in the CLI today and in the browser later.
- Types document the domain model for new contributors.
- The real, lasting contract is the YAML format plus JSON Schema. The language choice is reversible, and alternative implementations are possible.
- Contributors who only know Python can't work on the engine, but they can still contribute content, vocabularies, docs, and review.

## Alternatives considered

- **Python and Pydantic:** excellent, and approachable for educators who script. Rejected because a browser-based interface would need a second language and duplicated logic.
- **Hand-written JSON Schema as the source:** language-neutral, but verbose and hard for newcomers to read. Generating it from Zod keeps one readable source.
- **Markdown with YAML front matter:** friendly for prose, but awkward for structured data such as questions, rubrics, and lesson sequences. YAML is used throughout, with Markdown allowed inside long text fields.
- **ESLint + Prettier instead of Biome:** more familiar, but two tools and more configuration. Easy to switch if contributors prefer it.
