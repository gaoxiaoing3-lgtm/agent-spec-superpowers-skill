---
name: agent-spec-superpowers-workflow
description: Use this skill when planning or executing software development with AI agents and you want a disciplined workflow that combines Spec Kit as the lifecycle backbone, Superpowers as execution discipline, and Agent Skills such as Google or Gemini skills as on-demand domain knowledge. Trigger for requests involving spec-driven development, agent skills workflows, Superpowers, Spec Kit, Google skills, Gemini API skills, AI coding agent process design, feature planning, implementation gates, TDD, debugging, verification, or multi-agent task execution.
---

# Agent Spec Superpowers Workflow

Use this skill to run a software task through three clearly separated layers:

1. Spec Kit is the main lifecycle backbone.
2. Superpowers supplies execution discipline and quality gates.
3. Agent Skills supply on-demand domain knowledge, especially Google/Gemini/Cloud skills when relevant.

Do not let domain skills drive the project lifecycle. Do not let Superpowers replace the spec artifacts. Do not implement before the spec, plan, and task list are coherent unless the user explicitly asks for a quick patch.

## Priority Model

| Priority | System | Best at | Use for |
| --- | --- | --- | --- |
| 1 | Spec Kit | Product and implementation artifact chain | constitution, requirements, clarification, plan, tasks, consistency analysis, implementation |
| 2 | Superpowers | Agent work discipline | brainstorming, planning hygiene, TDD, systematic debugging, verification, review handling, subagent coordination |
| 3 | Agent Skills | Current domain knowledge | SDK rules, cloud platform constraints, API examples, provider-specific best practices |

Short rule: Spec Kit manages what gets built, Superpowers manages how the agent works, Agent Skills manage what the agent must know for a specific technology.

## Workflow

### 1. Intake

Use Superpowers-style brainstorming before generating artifacts:

- Identify the user, problem, outcome, non-goals, constraints, and acceptance criteria.
- Ask only blocking questions. Make reasonable assumptions for low-risk gaps and record them.
- Detect domain skills needed later, but do not load or apply them until they are relevant.

### 2. Constitution

Use Spec Kit constitution as the project governance source.

If no constitution exists, create or request one covering:

- code quality
- test standards
- security and privacy
- performance expectations
- UX consistency
- AI-generated code verification rules

If a constitution exists, treat it as binding unless the user explicitly changes it.

### 3. Specification

Use Spec Kit specify for the product behavior:

- user stories
- functional requirements
- non-functional requirements
- edge cases
- acceptance scenarios
- out-of-scope items

Keep implementation choices out of the spec unless they are hard constraints from the user.

Run clarify when requirements are ambiguous enough to affect architecture, data, security, or user-visible behavior.

### 4. Domain Skill Selection

Before planning, choose only the domain skills needed for this task.

For Google-related work:

- Use `google/skills` for Google Cloud, Agent Platform, Cloud Run, Firebase, BigQuery, GKE, AlloyDB, Cloud SQL, and Well-Architected Framework topics.
- Use `google-gemini/gemini-skills` for Gemini API, Gemini SDKs, Live API, Interactions API, multimodal work, function calling, structured output, model usage, or SDK migration.
- Prefer official docs or MCP-backed documentation for unstable API details, model names, pricing, auth behavior, regions, and deprecations.

Domain skills inform the plan and implementation. They do not override the spec unless they reveal an impossibility, security risk, or platform constraint; in that case, update the spec or plan explicitly.

### 5. Plan

Use Spec Kit plan for the technical design.

The plan should include:

- architecture
- data model
- API boundaries
- dependency choices
- domain-skill assumptions
- risks and alternatives
- test strategy
- migration or rollback notes when relevant

Use Superpowers writing-plans discipline to keep the plan sequential, testable, and scoped.

### 6. Tasks

Use Spec Kit tasks to generate implementation units.

Each task should have:

- a requirement or plan source
- a clear file/module ownership area
- a verification method
- dependency ordering
- a parallelization marker when safe

Use Superpowers subagent-driven-development only for independent tasks with non-overlapping write scopes. Tell subagents they are not alone in the codebase and must not revert other work.

### 7. Analyze

Run a consistency pass before implementation:

- every requirement has tasks
- every task maps to a requirement or plan decision
- tests cover key acceptance scenarios
- domain assumptions are verified or marked as assumptions
- no task contradicts the constitution

If gaps exist, go back to the right artifact instead of patching around them during implementation.

### 8. Implement

Use Spec Kit implement to execute the task list.

Apply Superpowers discipline during execution:

- Prefer TDD for logic, API contracts, regressions, and bug fixes.
- Use systematic debugging for failures: reproduce, isolate, fix, verify.
- Keep edits scoped to the active task.
- Update spec/plan/tasks if implementation reveals a real requirement or platform constraint change.

### 9. Verify

Before claiming completion, use Superpowers verification-before-completion:

- run relevant tests
- run lint/typecheck/build when available
- check acceptance scenarios against the spec
- check constitution compliance
- verify Google/Gemini/Cloud SDK or API assumptions if relevant

If a verification step cannot run, report exactly why and what residual risk remains.

### 10. Review

Use Superpowers requesting-code-review or receiving-code-review when preparing or responding to review.

Review against:

- spec behavior
- plan adherence
- test coverage
- stale SDK/API usage
- secrets and hard-coded cloud resources
- maintainability of generated code

## Fast Routing

- New feature: brainstorming -> constitution -> specify -> clarify -> domain skills -> plan -> tasks -> analyze -> implement -> verify -> review.
- Bug fix: systematic debugging -> update spec if behavior gap exists -> domain skills if provider/API related -> fix with regression test -> verify.
- Refactor: specify behavior-preservation requirements -> plan small steps -> tasks with tests -> implement -> verify no behavior drift.
- Google/Gemini work: keep Spec Kit as lifecycle, load Google/Gemini skills only at planning and implementation points that need current platform knowledge.

## Reference

For the detailed phase guide, read `references/workflow-guide.md` when the user asks for the full process, wants to install or adapt the workflow, or needs a project template.

