# Agent Spec Superpowers Skill Constitution

## Purpose

This repository defines the required workflow order for agent-assisted project work:

1. Spec Kit
2. Superpowers
3. Agent Skill

The order is intentional. Specs define what should be true. Superpowers discipline defines how work should proceed. Skills provide reusable execution knowledge after the contract and discipline are already known.

## Principles

### 1. Spec Kit First

Start with durable product memory and feature contracts.

Every meaningful change should have a feature folder under `specs/<feature>/` with:

- `spec.md`: user goals, scenarios, requirements, and acceptance checks.
- `plan.md`: technical approach, constraints, risks, and validation plan.
- `tasks.md`: ordered checklist that can be executed and updated.

If the spec is missing, create it. If it is stale, update it before implementation.

### 2. Superpowers Second

After the spec is clear, use execution discipline:

- Clarify the user goal.
- Plan the work before broad changes.
- Prefer small vertical slices.
- Use test-first or verification-first thinking.
- Review the result before handoff.
- State what was verified and what remains uncertain.

### 3. Agent Skill Third

Only after the spec and execution discipline are established, use a skill for reusable project-specific instructions.

Skills live under `skills/<skill-name>/SKILL.md` and should be portable, focused, and explicit about when to use them.

### 4. Do Not Start From A Skill

A skill is not the source of product truth. A skill can guide execution, but it must not replace the spec.

### 5. Keep Memory Durable

Keep decisions in source-controlled markdown, not only in chat history.

## Definition Of Done

A workflow adoption is done when:

- The required order is visible in `README.md` and `AGENTS.md`.
- The constitution defines the order and hard rules.
- A feature spec, plan, and task list exist.
- A reusable skill exists.
- The downstream project can point agents to this workflow without relying on prior chat context.
