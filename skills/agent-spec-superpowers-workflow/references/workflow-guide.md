# Detailed Workflow Guide

## Sources

- Google Agent Skills: https://github.com/google/skills
- Google Gemini Skills: https://github.com/google-gemini/gemini-skills
- GitHub Spec Kit: https://github.com/github/spec-kit
- Superpowers skills overview: https://www.superpowers-skills.com/en-us/2026/01/24/step3-skills.html

## Recommended Project Layout

```text
repo/
  .specify/
    memory/
      constitution.md
  specs/
    001-feature-name/
      spec.md
      plan.md
      tasks.md
      research.md
      data-model.md
      quickstart.md
  .agents/
    skills/
      domain-skills...
  docs/
    decisions/
```

## Install Commands

Install Google skills:

```bash
npx skills add google/skills
npx skills add google-gemini/gemini-skills --skill gemini-api-dev --global
```

Install Spec Kit:

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
specify init
```

If the agent supports skills mode for Spec Kit, prefer skills mode over plain slash-command prompt files.

## Combined Phase Map

| Phase | Primary system | Supporting discipline | Domain skills |
| --- | --- | --- | --- |
| Intake | Superpowers | brainstorming | identify possible skills only |
| Constitution | Spec Kit | writing durable principles | none unless platform policy matters |
| Specify | Spec Kit | brainstorming | none unless requirements mention fixed platform behavior |
| Clarify | Spec Kit | brainstorming | use docs only for feasibility questions |
| Plan | Spec Kit | writing-plans | load relevant Google/Gemini skills |
| Tasks | Spec Kit | subagent planning, TDD | use skill constraints in task notes |
| Analyze | Spec Kit | verification thinking | verify unstable provider assumptions |
| Implement | Spec Kit | TDD, debugging, scoped edits | apply loaded skill rules |
| Verify | Superpowers | verification-before-completion | confirm SDK/API/auth assumptions |
| Review | Superpowers | requesting/receiving review | flag stale or risky provider usage |

## Google Skill Selection

Use `google/skills` when the task is about:

- Google Cloud architecture
- Cloud Run
- Firebase
- BigQuery
- GKE
- AlloyDB
- Cloud SQL
- Gemini API through Google Cloud Agent Platform
- Google Cloud Well-Architected security, reliability, or cost optimization

Use `google-gemini/gemini-skills` when the task is about:

- Gemini API app development
- Gemini SDK usage
- Gemini Live API
- Gemini Interactions API
- multimodal prompts
- function calling
- structured output
- embeddings
- model migration or deprecated SDK replacement

For unstable details, verify against official docs or an official documentation MCP rather than relying only on skill text.

## Quality Gates

Do not proceed from plan to tasks unless:

- requirements are traceable
- major technology choices are justified
- risky assumptions are stated
- the test strategy is explicit

Do not proceed from tasks to implementation unless:

- tasks are independently executable
- write scopes are clear
- verification is listed for each major task
- parallel work has non-overlapping ownership

Do not complete unless:

- relevant tests were run
- lint/typecheck/build were run when available
- acceptance scenarios were checked
- known unverified assumptions are disclosed

## Prompt Template

```text
Use agent-spec-superpowers-workflow.

Run this as a Spec Kit-led workflow:
1. Use Superpowers-style brainstorming for only blocking questions.
2. Produce or update the Spec Kit artifacts in order.
3. Load Google/Gemini/domain skills only when needed for planning or implementation.
4. Use TDD/systematic debugging during implementation.
5. Finish with verification-before-completion and a review checklist.

Task:
<describe the feature, bug, or refactor>
```

## Anti-Patterns

- Loading every skill at the start.
- Letting a Google/Gemini skill decide product behavior.
- Implementing from brainstorming notes without Spec Kit artifacts.
- Treating `/speckit.implement` as complete without independent verification.
- Running subagents on overlapping files without ownership boundaries.
- Skipping spec updates when implementation reveals changed requirements.

