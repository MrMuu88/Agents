---
name: implementation-react-renderer
description: "Use when: implementing React renderer features, components, and UI behavior connected to backend contracts."
---

# Implementation Adapter: React Renderer

This skill provides React implementation guidance for renderer/frontend delivery.

Shared rules that apply across stacks are defined in `.github/instructions/SharedDeveloperGuidelines.instruction.md`.
This skill focuses only on React-specific implementation behavior.

## When to use

- Work is primarily in renderer/frontend React files.
- Scope includes component logic, screen behavior, state, and visual implementation.
- The feature consumes a pre-defined IPC or HTTP contract.

## UI fidelity checklist

- Match relevant UI specification and HTML prototype structure and behavior.
- Preserve established layout and shared component contracts unless change is explicit.
- Include clear loading, empty, error, and success states for data views.

## Component design checklist

- Use functional components with explicit TypeScript prop/state/event typing.
- Keep components small and single-purpose.
- Prefer composition and custom hooks over large monolithic components.
- Keep non-trivial logic outside JSX in helper functions/hooks.

## Styling checklist

- Define module-local `const styles` objects at file bottom.
- Avoid complex inline style objects in JSX.
- Keep styles scoped to the component module.

## Accessibility and performance checklist

- Ensure semantic markup and accessible labels for interactive elements.
- Ensure keyboard usability for interactive flows.
- Use memoization (`useMemo`, `useCallback`, `React.memo`) when render cost justifies it.
- For large lists, use virtualization when needed.

## Test checklist

- Add/update component tests for critical behavior.
- Prefer user-observable behavior assertions over implementation details.
- Mock external dependencies where needed to isolate behavior.
