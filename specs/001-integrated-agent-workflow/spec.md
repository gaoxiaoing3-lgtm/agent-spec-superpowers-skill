# Feature Spec: Integrated Agent Workflow

## Status

Accepted baseline.

## Required Order

1. Spec Kit
2. Superpowers
3. Agent Skill

## User Need

A user needs agent work to follow one repeatable order across projects so future conversations can resume from durable project files instead of relying on unsynchronized chat history.

## Requirements

- FR-001: The workflow must explicitly state that Spec Kit comes first.
- FR-002: The workflow must explicitly state that Superpowers comes second.
- FR-003: The workflow must explicitly state that Agent Skill comes third.
- FR-004: Agents must read or update specs before meaningful implementation.
- FR-005: Agents must use Superpowers-style execution discipline after the spec is known.
- FR-006: Agents must use skills as reusable project instructions, not as the first source of truth.
- FR-007: The repository must include `README.md`, `AGENTS.md`, `.specify/memory/constitution.md`, a feature spec folder, and a `SKILL.md`.

## Acceptance Checks

- AC-001: `README.md` shows the order as Spec Kit, Superpowers, Agent Skill.
- AC-002: `AGENTS.md` gives agents the same order.
- AC-003: The constitution says not to start from a skill when the spec is missing or stale.
- AC-004: The skill states that it is step 3, after Spec Kit and Superpowers.

## Out Of Scope

- Replacing any upstream tool.
- Implementing a CLI.
- Enforcing the workflow through automation in this baseline version.
