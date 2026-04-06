---
name: features-and-userstories
description:>
Use when: creating or updating feature folders and user story markdown files
  under Documentations/Features for this project.
applyTo:
  - "Documentations/Features/**"
---

## Purpose

This instruction describes how to document features and their related user stories in the project so that an agent can easily understand and automate them.

## Folder structure

1. There is a `Documentations` folder at the root of the project.
2. Inside the `Documentations` folder there is a `Features` folder.
3. Every feature has its own subfolder under `Documentations/Features`.

Example:

- `Documentations/Features/FE-001-felhasznaloi-auth`
- `Documentations/Features/FE-002-riportolas`

## Rules for feature folders

For every feature, create a new folder under `Documentations/Features` as follows:

1. Every feature must have a **unique feature identifier** in the entire project in the form `FE-XXX` (e.g. `FE-001`, `FE-002`, ...).
2. The folder name should start with this feature identifier, followed by a hyphen and a short, lowercase, hyphen-separated slug of the feature name (spaces and accents are allowed in the slug if needed, but a simple, readable name is recommended).
3. The feature folder must contain a `FE-XXX-[FeatureName].md` file named after the feature, which summarizes the feature.

### Contents of `FE-XXX-[FeatureName].md`

The feature description file must contain at least the following sections:

1. **Feature name / short description**
2. **List of related user stories** (as links to the user story files in the same folder)
3. **Acceptance criteria** (at feature level, if any – high-level business/product goals being met)
4. **Relation to the PRD / higher-level requirements** (if relevant, e.g. which PRD chapter the feature is based on)
5. **Other important information** (e.g. technical constraints, dependencies, open questions)

Recommended structure:

```md
# [FE-XXX] [Feature name]

## Short description

## Related PRD / requirements
- PRD_Database_manager.md section 3.2
- ...

## Related user stories
- [US-001 - ...](US-001-...md)
- [US-002 - ...](US-002-...md)

## Feature-level acceptance criteria
- [AC-001] ...

## Other notes
- ...
```

## Rules for user story files

The user stories describing each feature must be created inside the feature’s own folder.

1. **Create a separate `.md` file for every user story.**
2. **File name convention:**
  - based on the user story title,
  - only **lowercase letters**, **numbers**, and **hyphens (`-`)** may be used,
  - there must be no spaces in the file name,
  - the file name must start with a US identifier (e.g. `US-001`) – this is mandatory for agents and strongly recommended for manual editing.

Example file names:

- `US-001-adatbazis-hozzaferes.md`
- `US-010-felhasznaloi-jelszo-modositas.md`

## Required contents of a user story file

Every user story file must contain at least the following parts:

1. **User story description** – in the following format:

  "As a [user role], I want to [goal] so that [reason]."

2. **List of acceptance criteria** – as a bullet list, with each criterion on its own line.

Recommended template:

```md
# [US-XXX] [User story title]

## User story
As a [user role], I want to [goal] so that [reason].

## Acceptance criteria
- [AC-001] ...
- [AC-002] ...
```

## Use of US and AC identifiers

- Every user story must have a **unique US identifier** in the entire project (e.g. `US-001`, `US-002`, ...).
- The **first element** of the user story file name must be this identifier (e.g. `US-001-adatbazis-hozzaferes.md`).
- The user story heading must follow the template: `# [US-XXX] [User story title]`, where `US-XXX` matches the identifier used in the file name.
- The acceptance criteria for a given user story must be numbered **within that story**: `[AC-001]`, `[AC-002]`, ...; AC numbering **restarts for each user story**, it does not need to be globally unique.
- Feature-level acceptance criteria (in the `[FeatureName].md` file) may also use `[AC-001]` notation; these are interpreted **within the context of that specific feature document**.

## Language conventions

- The **user story** sentence must always follow the English template: `"As a [user role], I want to [goal] so that [reason]."`.
- Titles, acceptance criteria, and other descriptive text may be **in Hungarian**.
- For agents, if there is no specific requirement, the user story sentence should be **in English**, while the rest of the content can be **in Hungarian**, so that both developers and business stakeholders can easily understand it.

## Key points for the agent (summary)

1. Every feature:
  - has a unique feature identifier `FE-XXX` (e.g. `FE-001`),
  - location: `Documentations/Features/FE-XXX-[feature-slug]`,
  - contains: `FE-XXX-[FeatureName].md` with short description, list of related user stories, feature-level acceptance criteria, relation to the PRD + multiple user story `.md` files
2. Every user story file:
  - is a separate `.md` file in the same feature folder,
  - file name: only lowercase letters, numbers and hyphens, with a mandatory US identifier at the beginning (e.g. `US-001-adatbazis-hozzaferes.md`),
  - content: a single English “As a ...” sentence + acceptance criteria in a bullet list in the form `[AC-001]`, `[AC-002]`, ...