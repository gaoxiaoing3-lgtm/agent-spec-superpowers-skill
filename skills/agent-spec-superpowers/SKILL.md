---
name: agent-spec-superpowers
description: Use when a project must follow the integrated workflow order: Spec Kit first, Superpowers second, Agent Skill third.
---

# Agent Spec Superpowers Skill

## When To Use

Use this skill when setting up, auditing, or continuing a project that must follow the integrated workflow order:

1. Spec Kit
2. Superpowers
3. Agent Skill

## Important

This skill is step 3. Do not use it as the first source of truth.

Before applying this skill, confirm that the project has or needs:

- `.specify/memory/constitution.md`
- `specs/<feature>/spec.md`
- `specs/<feature>/plan.md`
- `specs/<feature>/tasks.md`

## Required Workflow

1. Spec Kit: read or create the constitution and active feature spec folder.
2. Superpowers: clarify, plan, implement in small vertical slices, verify, review, and hand off.
3. Agent Skill: use project-specific skill guidance to execute consistently.

## Project Setup Checklist

- Add `AGENTS.md` with the required order and read order.
- Add `.specify/memory/constitution.md` with hard workflow rules.
- Add `specs/<feature>/spec.md` for user goals and acceptance checks.
- Add `specs/<feature>/plan.md` for technical plan and validation.
- Add `specs/<feature>/tasks.md` for ordered work.
- Add `skills/<project-skill>/SKILL.md` for reusable project instructions.

## Audit Checklist

- `README.md` says Spec Kit, Superpowers, Agent Skill in that order.
- `AGENTS.md` says the same order.
- The constitution forbids starting from a skill when the spec is missing or stale.
- The project skill says it is step 3.
- The active feature task list reflects the current next work.

## Handoff Format

When finishing work, report:

- What spec files changed.
- What implementation files changed, if any.
- What verification was run.
- What remains incomplete or risky.
