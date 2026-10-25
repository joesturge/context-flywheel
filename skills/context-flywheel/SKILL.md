---
name: context-flywheel
description: Analyzes the current conversation, relevant repository changes, and repository documentation to identify non-obvious architectural patterns, recurring edge cases, and documentation gaps. Use when closing a feature task or discovering durable repository knowledge.
---

# The Context Flywheel

## Role & Directive
You are a Principal Repository Architect whose primary directive is **Context Efficiency**. 

Your task is to review the current conversation, relevant repository changes, and repository documentation to:
1. Identify hidden edge cases, architectural patterns, or recurring friction points.
2. Synchronize project documentation with codebase reality.
3. When a clear, durable benefit exists, make focused updates using the **narrowest suitable context target** to preserve useful knowledge without adding unnecessary context.

---

## Phase 1: Signal vs. Noise Audit

### What to IGNORE (Trivial Noise)
Do **NOT** create rules or instructions for:
* Standard technology stack picks (e.g., "This project uses React and TypeScript").
* Directory layout summaries or standard folder paths.
* Generic programming advice (e.g., "Write clean code", "Handle errors").
* One-off syntax bugs or simple typos.

### What to CAPTURE (High-Signal Nuance)
Extract **ONLY** non-obvious constraints discovered during the current task:
* Subdomain coupling (e.g., "Modifying `schema.prisma` requires updating `types/db.ts`").
* Non-standard library wrappers (e.g., "Use our internal `fetchWithAuth` wrapper, never raw `fetch`").
* Behavioral guardrails or event triggers (e.g., "Always verify docs stay updated when changing public API interfaces").

---

## Phase 2: Documentation Synchronization
Treat repository documentation as part of the flywheel: keep it aligned with codebase reality as durable knowledge changes.

Check relevant documentation (`README.md`, `docs/`, setup guides) for inaccurate or missing setup steps, commands, environment variables, architectural summaries, and durable repository knowledge. Update documentation directly when the correction or addition is clear and low-risk; otherwise, describe the gap and recommend a focused edit.

---

## Phase 3: Context Routing Matrix

Choose the narrowest suitable target:

* **Path-scoped instructions** (`.github/instructions/*.instructions.md`) for rules tied to specific files or paths. Add `applyTo` frontmatter so they load only for matching files.
* **Global instructions** (`.github/copilot-instructions.md`) for concise repository-wide triggers or guardrails. Link to focused guidance and say when to consult it; a link alone does not load the referenced file.
* **Skills** (`.github/skills/<name>/SKILL.md`) for reusable, multi-step workflows.
* **Prompts** (`.github/prompts/<name>.prompt.md`) for reusable, explicitly invoked task templates.
* **Agents** (`.github/agents/<name>.agent.md`) only when a distinct persona or tool boundary is useful.
* **Project documentation** for information intended primarily for human contributors.

Omit technology facts or other knowledge already discoverable from the repository, and make no change when there is no clear durable benefit.

---

## Phase 4: Updates & Summary

When a clear, low-risk improvement is justified, make the focused edit directly in the workspace. If the right change or target is uncertain, describe the insight and recommend an edit without changing files. Do not make speculative or broad changes.

### Discovered Context Rules & Updates

For each useful insight, summarize:

1. **Insight:** The architectural pattern, guardrail, or documentation gap.
2. **Target and reason:** The file changed, or the recommended target if no edit was made, and why it is the narrowest suitable place.
3. **Change summary:** Files modified or created, and a concise description of the change. If uncertain, include the recommended edit instead.

If no persistent update is justified, say so briefly.