# Contributing to Open Lesson Engine

Thank you for helping. Open Lesson Engine is built by **educators and developers together**. **You don't need to write code to contribute.** The most valuable contributions are often a well-described activity, an honest classroom-test report, or a thoughtful review.

- New here? Read the [README](README.md) for the big picture.
- Want to know how things work? Read [DEVELOPMENT.md](DEVELOPMENT.md).
- Everyone participating agrees to the [Code of Conduct](CODE_OF_CONDUCT.md).

> **Project status: foundation stage.** The component file format is being implemented now (see the [roadmap tasks](docs/roadmap/mvp-tasks.md)). Until automated validation lands (task 6), the best way to share educational content is by [opening an issue](#share-a-resource-or-idea-no-git-needed). Developers can pick up roadmap tasks right away.

---

## Ground rules

Please read these before contributing anything.

### 1. Protect student privacy (always)

**Never include information that could identify a student.** That means no names, photos, work samples, grades, IEP or 504 details, behavior notes, or anything else from a student's record. This applies to issues, pull requests, comments, and contributed materials. Use obviously fictional names and examples.

Once something is pushed to a public repository it can be copied quickly, and it is very hard to fully remove from git history. If you notice student information anywhere in the project, tell a maintainer right away (see the [Code of Conduct](CODE_OF_CONDUCT.md#reporting-an-issue)).

### 2. Only share what you have the right to share

| ✅ OK to contribute | ❌ Not OK |
| --- | --- |
| Your own original work | Textbook or publisher materials |
| Openly licensed material (CC BY, CC BY-SA, CC0, public domain), with credit in the component's `sources` field | Resources you bought (for example from teacher marketplaces), even if you've modified them |
| Adaptations of components already in this library | Copyrighted worksheets, images, or tests found online |
| | District-owned materials, unless your district gives permission |

> **A note for teachers:** some school districts claim ownership of instructional materials that employees create as part of their job. If you're unsure about something you made, check your district's policy or employment agreement before contributing it.

### 3. Your contribution is shared under the project's licenses

By submitting a contribution, you agree that it is licensed as follows (the project calls this "inbound = outbound"):

- **Educational content** (anything in `library/`) is licensed under [CC BY 4.0](LICENSE-CONTENT), unless you set the component's `license` field to `CC-BY-SA-4.0` or `CC0-1.0`.
- **Everything else** (code, schemas, vocabularies, documentation) is licensed under the [MIT License](LICENSE).

You keep your copyright. There's no separate agreement to sign. See [ADR 0003](docs/decisions/0003-licensing.md) for why these licenses were chosen.

### 4. AI-assisted work is welcome, but you are the expert

If AI tools helped you draft something, that's fine as long as:

- you have personally reviewed it for accuracy, safety, and age-appropriateness,
- it meets the same standards as anything else, and
- you say so, by setting `ai_assisted: true` in the component and mentioning it in your pull request.

---

## Ways to contribute

### For educators (no coding needed)

| Contribution | What it involves |
| --- | --- |
| **Share a resource or idea** | Describe an activity, worksheet, assessment, or strategy that works in your classroom. [How to do it without git](#share-a-resource-or-idea-no-git-needed). |
| **Review a component** | Check a proposed component for accuracy, age-appropriateness, clarity, safety, accessibility, and realistic timing. Comment on its pull request. |
| **Classroom-test a component** | Use it with your students, then report what happened in general terms: "took 60 minutes, not 45"; "step 3 confused students"; "the word bank really helped." **No student names or data.** |
| **Adapt a component** | Create a variant for different learners, grade levels, settings, or languages. See [Adapting a component](#adapting-a-component). |
| **Suggest vocabulary** | Propose a missing subject, activity type, learner-need category, or standards framework. |
| **Improve the docs** | Point out confusing wording, add glossary terms, or write guides for other teachers. |

### For developers

| Contribution | Where to start |
| --- | --- |
| **Build the engine** | Pick an unassigned task from the [roadmap](docs/roadmap/mvp-tasks.md) (or its GitHub issue) and comment that you're taking it. |
| **Fix bugs and improve tests** | Look for open issues labeled `bug` or `good first issue`. |
| **Accessibility** | Rendered output must work with screen readers and print cleanly. |
| **Review pull requests** | Code review is a contribution, too. |

---

## Share a resource or idea (no git needed)

1. Go to the repository's **Issues** tab and click **New issue**.
2. Give it a title like "Activity: Soil texture jar test (grades 9–10)".
3. Describe the resource. It helps to include:
   - subject, topic, and grade level(s)
   - how long it takes
   - materials needed and any safety notes
   - the steps, as you would explain them to a substitute teacher
   - what students should learn (objectives), and any standards codes you use
   - how you adapt it for different learners
4. Say whether you'd like help turning it into a component file. A volunteer can do the formatting and credit you as the author.

Issue forms that guide you through these questions are planned (task 6).

---

## Writing a component

Once the format is implemented (tasks 2–7), a component is a single YAML file. The easiest way to write one is to copy a similar example from `library/` and edit it. The [DEVELOPMENT.md examples](DEVELOPMENT.md#62-from-a-teachers-notes-to-a-component) show what they look like.

### Where files go

`library/<type-folder>/<id>.yaml`. For example, the activity `floating-leaf-disks` lives at `library/activities/floating-leaf-disks.yaml`. The `id` must match the file name.

### Checklist for a good component

- [ ] **Title and summary** are written for another teacher. Would a colleague know when to use it?
- [ ] **One thing per file.** An activity and its worksheet are two components that reference each other.
- [ ] **Timing is realistic.** Put your honest estimate in `duration_minutes`.
- [ ] **Safety notes** are included for anything hands-on: labs, tools, greenhouse or shop work, food, heat, chemicals.
- [ ] **Objectives are linked**, and standards codes use the `FRAMEWORK:CODE` format (for example `NGSS:MS-LS1-6`).
- [ ] **Grade range, difficulty, and reading level** are set separately where relevant ([why](DEVELOPMENT.md#54-shared-value-types)).
- [ ] **Answers are in the file.** Worksheets and assessments include answers, and the renderer removes them from student copies.
- [ ] **Everything is fictional.** No real student, colleague, or school details.
- [ ] **Sources are credited** in `sources`, and `license` is set.
- [ ] **You're credited** in `contributors`, with a name of your choice (a pseudonym is fine).

### Component status

Every component has a `status`, which tells other teachers how much confidence to place in it:

| Status | Meaning | How a component gets there |
| --- | --- | --- |
| `draft` | Newly contributed; not yet checked by anyone else | Every new component starts here. |
| `reviewed` | Another educator has checked it for accuracy, clarity, safety, and appropriateness | A reviewer who isn't the author approves the pull request and adds themselves as a `reviewer`. |
| `classroom_tested` | Used with real students, with feedback recorded | A classroom-test report (with no student data) is linked or summarized, and the tester is credited as a `classroom_tester`. |

---

## Adapting a component

The project encourages adaptation instead of overwriting. If you change a component to fit your students, **create a variant** so the original stays available:

1. Copy the original file to a new file with a new `id`, for example `photosynthesis-equation-supported`.
2. Add `derived_from` with the original's `id` and `version`.
3. Add an `adaptation` block:
   - `kind`: `accommodation` if it changes *how* students access the work; `modification` if it changes *what* they're expected to do; `extension` if it adds depth
   - `learner_needs`: the needs it supports
   - `strategies`: the strategies you used
   - `notes`: a short description of what you changed
4. **Keep the original contributors** and add yourself with `role: adapter`. Credit is required by the license, and it's also the right thing to do.
5. If the original is `CC-BY-SA-4.0`, your variant must be too.

**When to edit the original instead:** to fix an error such as a typo, a wrong answer, a safety problem, or broken timing. Bump its `version` as described in [DEVELOPMENT.md §6.5](DEVELOPMENT.md#65-versioning).

---

## Pull requests

### First time using GitHub?

You can contribute entirely in your web browser:

1. Open the folder where your file belongs, such as `library/activities/`.
2. Click **Add file → Create new file**. GitHub will offer to create your own copy (a "fork").
3. Name the file, paste your component, and click **Propose new file**, then **Create pull request**.

You can also [open an issue](#share-a-resource-or-idea-no-git-needed) and ask for help. People are happy to help.

### What happens after you open a pull request

| Change | Automated checks | Human review |
| --- | --- | --- |
| **Content** (`library/`) | Validation, once task 6 lands | One educator reviewer |
| **Vocabularies** (`vocabularies/`) | Validation | One maintainer |
| **Code** (`src/`, `tests/`) | Lint, type check, tests | One maintainer |
| **File format or architecture** | All of the above | A maintainer, plus an [ADR](docs/decisions/README.md) and discussion |

Reviewers of content look at: accuracy, safety, age-appropriateness, accessibility, clarity, realistic timing, privacy, licensing, and whether the metadata will help others find it.

### Guidelines for developers

- Read [DEVELOPMENT.md](DEVELOPMENT.md), especially the [philosophy](DEVELOPMENT.md#2-philosophy) and [coding standards](DEVELOPMENT.md#17-development-workflow).
- **Open an issue before starting a large change**, particularly anything that changes the file format, adds a component type or dependency, or touches the project principles.
- Keep pull requests small and focused, and link the issue they address.
- Include tests for behavior changes. Include documentation updates for anything user-facing.
- The core engine stays offline and AI-free: no network calls and no AI SDKs in `src/`.
- Write commit messages that explain *why*, not only *what*.

Setup commands will be documented here and in [DEVELOPMENT.md §17](DEVELOPMENT.md#17-development-workflow) when the project skeleton lands (task 1).

---

## Getting help

- **Questions:** open an issue and label it `question`.
- **Ideas and proposals:** open an issue to start a conversation before investing a lot of time.
- **Conduct concerns:** follow the reporting steps in the [Code of Conduct](CODE_OF_CONDUCT.md#reporting-an-issue).

Thank you for helping teachers spend more time teaching and less time reinventing the wheel.
