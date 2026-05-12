# Implementation Plan: Integrated Agent Workflow

## Approach

Create a small, portable repository standard that other projects can copy or reference.

The structure mirrors the required order:

1. Spec Kit files define durable memory and feature contracts.
2. Superpowers language defines execution discipline in agent-facing instructions.
3. Agent Skill files provide reusable project-specific guidance.

## Files

- `README.md`: public overview and order.
- `AGENTS.md`: agent entrypoint and read order.
- `.specify/memory/constitution.md`: non-negotiable workflow rules.
- `specs/001-integrated-agent-workflow/spec.md`: requirements.
- `specs/001-integrated-agent-workflow/plan.md`: implementation plan.
- `specs/001-integrated-agent-workflow/tasks.md`: checklist.
- `skills/agent-spec-superpowers/SKILL.md`: reusable skill.

## Adoption Steps

1. Add the files to a project.
2. Replace the sample feature spec with the project's active feature.
3. Add or update the project-specific skill.
4. Ensure `AGENTS.md` points future agents to the right read order.
5. Keep tasks updated as work progresses.

## Validation

Validate by checking that the required order appears in:

- `README.md`
- `AGENTS.md`
- `.specify/memory/constitution.md`
- `skills/agent-spec-superpowers/SKILL.md`

## Risks

- Agents may jump directly to skills if the order is not repeated in multiple files.
- Projects may create specs but fail to keep tasks updated.
- Teams may confuse Superpowers execution discipline with product requirements unless the spec remains first.
