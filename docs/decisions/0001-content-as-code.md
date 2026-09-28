# 0001. Store components as YAML files in git

- **Status:** Proposed
- **Date:** 2026-09-28

## Context

Open Lesson Engine needs somewhere to keep community-contributed educational components. It also needs a way to review contributions, credit contributors, track changes, and let people adapt each other's work. The project principles call for simplicity, community contribution as a first-class activity, no accounts, and usefulness without paid services.

## Decision

Each component is a plain-text YAML file in the `library/` folder of the git repository. There is no database and no server. Contributions arrive as pull requests. A generated index (`catalog.json`, `CATALOG.md`) provides search and browsing.

## Consequences

**Easier**

- Every change has an author, a date, and a reviewable diff.
- Adapting work is built in: forks, and variants that point to their source.
- Hosting is free, and anyone can download the whole library and use it offline.
- A district can keep its own private library and point the same tools at it.
- There are no accounts to secure, no servers to run, and no data to breach.

**Harder**

- Git and GitHub are unfamiliar to most teachers. Mitigations: issue forms that need no git knowledge, GitHub's in-browser editor, a step-by-step educator guide (task 7), and later a website with "suggest a component" links.
- Dynamic features such as ratings, comments, and live collaboration aren't available. GitHub issues and reviews stand in for now.
- Search needs a build step to generate the index.

**Revisit when:** contribution volume, library size, or a real feature need outgrows plain files. Moving later is low-risk, because a database can be loaded from the same validated files.

## Alternatives considered

- **Web app with a database (for example Postgres):** needs hosting, accounts, moderation tooling, backups, and money before providing any value.
- **Headless CMS:** adds a vendor dependency and accounts, and makes attribution and review history harder.
- **Google Drive or shared folders:** familiar to teachers, but offers no validation, no structure, no review workflow, and weak attribution.
