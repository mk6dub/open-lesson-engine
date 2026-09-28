# 0003. MIT for software; CC BY 4.0 for educational content

- **Status:** Proposed. **Maintainer confirmation requested** (see "Open question" below).
- **Date:** 2026-09-28

## Context

The repository will contain two very different kinds of work:

1. **Software**: the engine, schemas, CLI, and tooling.
2. **Educational content**: objectives, lessons, activities, worksheets, assessments, strategies, and templates written by educators.

Software licenses are a poor fit for lesson content, and Creative Commons [recommends against using CC licenses for software](https://creativecommons.org/faq/#can-i-apply-a-creative-commons-license-to-software). So the project needs two licenses.

The project's principles call for resources that are **adaptable**, **shared freely**, and **accessible regardless of school, district, location, or budget**.

**Timing matters.** Before outside contributions arrive, the maintainer owns everything and can change the license freely. Afterwards, a change needs every contributor's agreement. This decision should be confirmed early.

## Options for educational content

| License | What it allows | Pros | Cons |
| --- | --- | --- | --- |
| **CC BY 4.0** | Any use or adaptation, with credit | The standard license for Open Educational Resources (used by OpenStax and many state OER programs). Simplest to comply with. Combines with almost anything. | Others may use the content commercially, for example in a paid product, as long as they credit it. |
| **CC BY-SA 4.0** | Any use or adaptation, with credit; adaptations must use the same license | Keeps adaptations open. This is Wikipedia's license. | Adapted lessons must also be BY-SA, which is harder for districts combining it with their own materials. |
| **CC BY-NC 4.0 / BY-NC-SA** | Non-commercial use only | Reassures teachers who worry about resale on commercial marketplaces | "Commercial" is ambiguous (paid tutoring, for-profit schools, edtech tools a district pays for). Not considered fully "open" under common OER definitions. Incompatible with BY-SA content. |
| **CC BY-ND 4.0** | No adaptations | — | **Contradicts the project's core principle that resources are adaptable.** Not acceptable. |
| **CC0 1.0** | Public domain dedication; no conditions | Maximum reuse | Contributors get no guaranteed credit. Many teachers want attribution. |

## Options for software

| License | Pros | Cons |
| --- | --- | --- |
| **MIT** | Short, widely understood, compatible with everything | No explicit patent grant |
| **Apache-2.0** | Explicit patent grant and contribution terms | Longer; the patent clause matters little for this project |
| **GPL-3.0 / AGPL-3.0** | Keeps derivatives (and, with AGPL, hosted versions) open | Discourages adoption by schools, districts, and edtech integrators. More complex obligations. |

## Decision

- **Software: MIT** (`LICENSE`). Maximum adoption, minimal friction.
- **Educational content in `library/`: CC BY 4.0** by default (`LICENSE-CONTENT`).
- **Per-component licenses:** each component declares `license`. The accepted values are `CC-BY-4.0` (the default), `CC-BY-SA-4.0` (so openly licensed share-alike sources such as Wikipedia-derived material can be adapted), and `CC0-1.0`. All three can be combined safely.
- **Not accepted into the shared library:** NC (restricts who can use it) and ND (forbids adaptation).
- **Composed lessons** list every component's license and contributors in an attribution block generated at render time. When a lesson includes CC BY-SA material, the lesson as a whole is labeled CC BY-SA 4.0 (the most restrictive license in the mix).
- **Contributions are "inbound = outbound":** by submitting, contributors license their work under the license of the area they contribute to. There is no Contributor License Agreement, and contributors keep their copyright.
- The Code of Conduct is adapted from the Contributor Covenant and stays under CC BY-SA 4.0, as its license requires.

## Consequences

- Anyone can use, print, adapt, translate, and share the library, including districts and nonprofits, as long as they give credit.
- Someone could legally include the content in a commercial product with attribution. The free, open original remains available.
- Contributors must only submit work they have the right to license. [CONTRIBUTING.md](../../CONTRIBUTING.md) explains this, including the note that some school districts claim ownership of materials employees create.

## Open question for the maintainer

The main judgment call is **whether to also accept CC BY-NC content**. Many teachers want protection against resale. The trade-off is that NC material can't be freely combined with the rest of the library, and it limits legitimate uses. This ADR recommends **not** accepting NC for now and revisiting it if contributors ask. If the maintainer prefers otherwise, update this ADR, `LICENSE-CONTENT`, and the `license` allowlist before content contributions begin.
