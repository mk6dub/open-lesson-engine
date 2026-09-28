# 0004. No student data, permanently

- **Status:** Proposed
- **Date:** 2026-09-28

## Context

Student data is sensitive and legally protected: FERPA and COPPA in the United States, GDPR elsewhere, plus state student-privacy laws. Special education information (IEPs, 504 plans, evaluations) is among the most sensitive. The project's principles say to avoid collecting or storing personally identifiable student information.

Differentiation, a core feature, is exactly where a design could drift into modeling individual students ("generate a worksheet for Jamie's IEP").

## Decision

- The domain model has **no** `Student`, `Class`, `Roster`, `IEP`, `Grade`, or student-work entity, and never will.
- **Learner needs describe materials, not people.** `learner_needs: [reading]` means the material provides reading support. The categories are functional needs (`reading`, `executive_function`, `fine_motor`, …), not diagnoses or disability labels.
- Composition requests are about materials ("include reading supports"), never about individuals.
- Contributor information is limited to a display name (pseudonyms welcome), a role, and an optional link. No email addresses.
- The engine, CLI, and future website collect **no telemetry**.
- The validator includes a **privacy lint** that warns about patterns that look like personal information (email addresses, phone numbers, phrases such as "student name").
- Contribution and review guidelines treat student information as a serious issue even when it is accidental.
- Any future AI adapter receives only component content. There is nothing else to send.

## Consequences

- Schools can adopt the tools without data-privacy agreements, because the tools never touch student data.
- A teacher who wants a *specific* student's accommodations must pick the matching supports themselves. This is intentional: the teacher, who legitimately holds that information, stays the one applying it.
- Features like progress tracking or personalized assignment are out of scope for this project. Other systems with proper privacy controls can consume Open Lesson Engine components.

## Alternatives considered

- **Optional, local-only student profiles:** rejected. Even local-only storage creates breach, backup, and sharing risks, and it would pull the project toward accounts and compliance work.
