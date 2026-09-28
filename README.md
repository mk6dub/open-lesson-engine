# Open Lesson Engine

**An open-source toolkit for teachers to create, adapt, differentiate, and share high-quality lessons and classroom materials.**

> **Build once. Adapt endlessly. Share freely.**

## What is Open Lesson Engine?

Open Lesson Engine is a community-driven project designed to make it easier for educators to create useful, adaptable instructional materials.

Teachers spend enormous amounts of time creating and recreating:

- Lesson plans
- Worksheets
- Activities
- Assessments
- Exit tickets
- Answer keys
- Vocabulary resources
- Differentiated materials
- Visual supports

Open Lesson Engine aims to provide an open foundation where these resources can be created, adapted, improved, and shared by educators.

The project is being built with a simple belief:

**Teachers should spend more time teaching and less time reinventing the wheel.**

## How It Works

Open Lesson Engine is **not** an AI lesson-plan generator. It is a framework of **reusable educational components**, such as objectives, activities, worksheets, assessments, differentiation strategies, and lesson templates. Teachers write and share these components as small, structured files:

```yaml
# An excerpt. See DEVELOPMENT.md for a complete component.
id: floating-leaf-disks
type: activity
title: Floating leaf disks
topics: [photosynthesis]
grades: 7
duration_minutes: 45
difficulty: standard
activity_type: hands_on
standards: [NGSS:MS-LS1-6]
```

Components can be adapted into variants for different learners. They can also be **composed into complete lessons**, either by hand or by a transparent, rule-based composer that explains its choices. Everything works offline, without accounts, and without an AI service.

See [DEVELOPMENT.md](DEVELOPMENT.md) for the full architecture and domain model.

---

## Who Is It For?

Open Lesson Engine is being designed for:

- Classroom teachers
- Special education teachers
- Curriculum developers
- Instructional coaches
- Homeschool educators
- Teacher teams
- Educational technologists
- Developers building educational tools

It is intended to work across subjects, grade levels, and instructional environments.

---

## Core Principles

### Teachers remain the experts

Technology should support teacher expertise, not replace it.

### Differentiation is fundamental

Instructional materials should be adaptable to different learners rather than treating differentiation as an afterthought.

### Context matters

A lesson isn't good simply because it looks good on paper. Grade level, student needs, available time, classroom environment, and instructional goals all matter.

### Share what works

When educators solve a problem, other educators shouldn't have to solve the same problem from scratch.

### Open by default

The project is intended to remain accessible to educators regardless of school, district, location, or budget.

---

## What We're Building

The project is currently in early development.

The long-term vision includes tools for:

- Lesson planning
- Lesson adaptation
- Differentiated instruction
- Worksheets
- Classroom activities
- Assessments
- Exit tickets
- Answer keys
- Vocabulary resources
- Reading-level adaptation
- Special education supports
- Standards alignment
- Printable classroom materials
- Community-contributed resources
- AI-assisted generation

Features will be added incrementally based on actual educator needs.

---

# Getting Started

## For Educators

You don't need to be a programmer to participate in Open Lesson Engine.

If you have a lesson, activity, worksheet, differentiation strategy, or idea that could help another educator, you can contribute.

### 1. Explore the project

Start by browsing the repository and looking through the existing resources and documentation.

### 2. Try an existing resource

Find something relevant to your subject or classroom and see how it works in practice.

### 3. Adapt it

Modify the resource for your:

- Grade level
- Subject
- Students
- Learning objectives
- Available class time
- Instructional setting

### 4. Share your improvement

If your adaptation could benefit other educators, consider contributing it back to the project.

---

## For Developers

### Start here

Read [DEVELOPMENT.md](DEVELOPMENT.md) for the architecture, technology stack (TypeScript on Node.js 22+), domain model, and MVP scope. The first ten implementation tasks are in [docs/roadmap/mvp-tasks.md](docs/roadmap/mvp-tasks.md), and major decisions are recorded in [docs/decisions/](docs/decisions/).

### Prerequisites

The project skeleton arrives with the first roadmap task. Once it is in place, this section will document:

- Required software
- Supported versions
- Installation
- Environment variables
- Local development
- Testing
- Building
- Deployment

### Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/open-lesson-engine.git
cd open-lesson-engine
```

### Install dependencies

```bash
# Installation instructions will be added as the project architecture is finalized.
```

### Run the project

```bash
# Development instructions will be added as the initial application is implemented.
```

### Run tests

```bash
# Testing instructions will be added with the initial test suite.
```

---

# Contributing

Contributions are welcome.

You do **not** need to be a developer to contribute.

## Educators can contribute

- Lessons
- Activities
- Worksheets
- Assessments
- Templates
- Differentiation strategies
- Classroom-tested ideas
- Documentation
- Feedback

## Developers can contribute

- Features
- Bug fixes
- Tests
- Documentation
- Integrations
- Accessibility improvements
- Performance improvements
- Developer tooling

## Before contributing

Please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

If you're unsure whether an idea belongs in the project, open an issue and start a conversation.

---

# Project Status

🚧 **Early Development**

Open Lesson Engine is currently in the early stages of development.

The architecture, features, and workflows will evolve as the project is tested and as educators contribute ideas and feedback.

Early contributors are encouraged to help shape the direction of the project.

---

# Roadmap

### Foundation

- [x] Establish project architecture (see [DEVELOPMENT.md](DEVELOPMENT.md))
- [ ] Define lesson data model
- [ ] Create initial development environment
- [ ] Build core lesson structure
- [ ] Establish contribution workflow

### Classroom Tools

- [ ] Lesson composer (assemble lessons from reusable components)
- [ ] Worksheet builder
- [ ] Assessment builder
- [ ] Exit ticket builder
- [ ] Answer keys (rendered from worksheet and assessment data)
- [ ] Differentiation tools
- [ ] Printable exports

### Community

- [ ] Community resource library
- [ ] Teacher contributions
- [ ] Subject collections
- [ ] Search and discovery
- [ ] Resource versioning
- [ ] Community feedback

### AI-Assisted Tools

- [ ] Lesson adaptation
- [ ] Reading-level adaptation
- [ ] Differentiation assistance
- [ ] Standards alignment
- [ ] AI-assisted resource creation

---

# A Note About AI

AI may become an important part of Open Lesson Engine, but it is not the purpose of the project.

The goal is to help educators create better instructional materials and spend more time working with students.

AI-generated material should always be reviewed by a qualified educator before being used in the classroom.

---

# Privacy & Student Data

Open Lesson Engine should not require personally identifiable student information.

**Do not contribute student names, identifying information, educational records, or other sensitive student data to this repository.**

When sharing examples, use fictional or anonymized information.

---

# License

This project is open source and uses two licenses:

- **Educational content** in `library/` is licensed under [Creative Commons Attribution 4.0 (CC BY 4.0)](LICENSE-CONTENT). You may use, print, adapt, and share it for any purpose, with credit to its contributors.
- **Software** (everything else) is licensed under the [MIT License](LICENSE).

See [ADR 0003](docs/decisions/0003-licensing.md) for why these licenses were chosen.

---

# Join the Project

Open Lesson Engine is being built in the open.

Whether you're a teacher with a great activity, a developer with an idea, or someone who simply wants to help improve educational resources, you're welcome here.

**Build something useful. Share what works. Make it better together.**

---

**Open Lesson Engine**

*Built for teachers. Open to everyone.*
