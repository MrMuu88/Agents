---
name: features-and-userstories
description: "Use when: translating requirements into feature folders and properly structured user story markdown files."
---

# Features & User Stories Skill

This skill provides step-by-step instructions on how to translate requirements into feature folders and properly structured user story markdown files.
The goal is to maintain a consistent structure across `Documentations/Features/**`.

## Step 1: Feature Extraction
- Break down the product into high-level features.
- Create a new folder for the feature: `Documentations/Features/FE-XXX-[feature-slug]`. `FE-XXX` MUST be a globally unique identifier in the project.

## Step 2: Feature Markdown Creation (FE-XXX-FeatureName.md)
In the folder, create `FE-XXX-[FeatureName].md` with the following structure:
```md
# [FE-XXX] [Feature name]

## Short description

## Related PRD / requirements
- PRD_Database_manager.md section 3.2

## Related user stories
- [US-001 - ...](US-001-...md)
- [US-002 - ...](US-002-...md)

## Feature-level acceptance criteria
- [AC-001] ...

## Other notes
- Dependencies, open questions...
```

## Step 3: User Story Extraction and Markdown Creation
- Inside the same feature folder, create a separate `.md` file for EVERY user story.
- **File name convention:** `US-XXX-[story-slug].md`. Only lowercase letters, numbers, and hyphens. NO SPACES.
- The `US-XXX` identifier MUST be globally unique in the project.
- Template for the user story file:
```md
# [US-XXX] [User story title]

## User story
As a [user role], I want to [goal] so that [reason].

## Acceptance criteria
- [AC-001] ...
- [AC-002] ...
```
- AC numbering restarts for each user story (i.e. every story starts with `[AC-001]`).

## Language Rules
- The “As a...” sentence MUST always be in English.
- Titles, acceptance criteria, and explanatory content MUST be in English.