# Agent Spec Superpowers Skill

This repository defines a strict combined workflow for agent-assisted engineering.

Required order:

1. Spec Kit
2. Superpowers
3. Agent Skill

The order matters. Spec Kit establishes durable product memory and feature contracts first. Superpowers governs execution discipline second. Agent Skills provide portable, reusable project-specific instructions third.

## Repository Map

- `AGENTS.md`: short entrypoint for agents.
- `.specify/memory/constitution.md`: non-negotiable workflow constitution.
- `specs/001-integrated-agent-workflow/spec.md`: workflow requirements.
- `specs/001-integrated-agent-workflow/plan.md`: implementation and adoption plan.
- `specs/001-integrated-agent-workflow/tasks.md`: adoption checklist.
- `skills/agent-spec-superpowers/SKILL.md`: reusable skill instructions.

## Rule

Do not start from an Agent Skill when a feature spec is missing or stale. Start with Spec Kit, execute with Superpowers discipline, then apply the relevant Agent Skill.
