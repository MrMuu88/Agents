# Simple Agent Definition Standard

## Goal

Use one clean format for all agents.
Do not split by agent type.
Keep every agent short, predictable, and easy to maintain.

## One Frontmatter Format

Use this field order for every agent file.

```yaml
---
name: AgentName
description: "Use when: clear trigger in one sentence."
argument-hint: Optional short input hint
model: Optional model override
disable-model-invocation: Optional true/false
user-invocable: Optional true/false
tools: [agent, search, read, edit, execute, web, vscode/askQuestions, vscode/memory, todo]
agents: [OptionalSubAgent1, OptionalSubAgent2]
handoffs:
  - label: Optional action label
    agent: Optional target agent
    prompt: Optional handoff prompt
    send: true
---
```

## Frontmatter Rules

1. Always include name, description, and tools.
2. Keep description in this format: Use when: ...
3. Only include optional fields when needed.
4. If a field is not used, remove it.
5. Keep tools minimal. Add only tools the agent actually needs.

## One Body Structure

Use this same section structure in every agent.

```markdown
## Role
What this agent is responsible for.

## Skills
Which skills this agent should apply and when. this should be a direct reference to the skills in the skills library if possible

## Rules
Hard constraints and required behavior.

## Boundaries
What this agent must not do.

## Workflow
Short step-by-step process (3 to 7 steps).

If necessary, Use multiple workflow sections when the agent has distinct modes, for example:
## Ingest Workflow
## Query Workflow
## Lint Workflow

## Output
What the agent must produce.

## Quality Checks
Quick checks before finishing.
```

## Body Rules

1. Keep total length practical (target: 60 to 140 lines).
2. Prefer short bullets over long prose.
3. Remove repeated policy text if it is already covered in global instructions.
4. Keep workflows concrete and executable.
5. An agent may define multiple workflow sections if it has clearly distinct operating modes.
6. If using multiple workflows, name each section as [Mode] Workflow and keep each one short and actionable.
7. Keep Skills and Rules short and specific.
8. Do not mix planning, design, and coding rules in one long section.

## Tools: Keep Only What Is Needed

Start from this minimal list and add only if necessary:

```yaml
tools: [read, search, edit, vscode/askQuestions, vscode/memory]
```

Add agent only if delegation is required.
Add execute only if terminal tasks are required.
Add web only if web research is required.
Add todo only if the workflow is multi-step.

## Handoffs: Single Simple Pattern

Use handoffs only when they are truly needed.

```yaml
handoffs:
  - label: Start Implementation
    agent: TargetAgent
    prompt: Short clear instruction
    send: true
```

Limit handoffs to 1 to 3 per agent.

## One Copy-Paste Template

```markdown
---
name: AgentName
description: "Use when: ..."
tools: [read, search, edit, vscode/askQuestions, vscode/memory]
---

## Role
- Primary responsibility.

## Skills
- Skill name and when to use it.

## Rules
- Required behavior and constraints.

## Boundaries
- What this agent must not change.

## Workflow
1. Discover context.
2. Clarify missing input.
3. Execute the task.
4. Verify result.

<!-- Optional: use multiple mode-specific workflows instead of a single Workflow section -->
<!--
## Ingest Workflow
1. ...

## Query Workflow
1. ...
-->

## Output
- Expected deliverables.

## Quality Checks
- Correct location
- Correct format
- Consistent with project instructions
```

## Simplification Plan For Current Agents

1. Use the same frontmatter field order in all agent files.
2. Keep only required fields plus truly needed optional fields.
3. Rewrite all descriptions to one-line Use when: ... format.
4. Remove duplicated rule text that repeats global instructions.
5. Apply the same required body structure to every agent (single Workflow or multiple [Mode] Workflow sections).
6. Reduce oversized files by removing redundant content.
7. Keep tool lists lean and role-specific.

## Definition of Done

Your agent set is simple when:

- Every file follows the same shape.
- Every description is clear in one line.
- Every workflow is short and actionable.
- Agents with multi-mode behavior may use multiple [Mode] Workflow sections instead of one generic Workflow section.
- Every tool list is minimal.
- No agent contains large duplicated policy blocks.
