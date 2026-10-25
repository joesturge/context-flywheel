---
name: context-flywheel
description: "Use when finishing a task or noticing repository friction, to assess and capture durable knowledge in the right project documentation or AI guidance."
---

# The Context Flywheel

Help maintain useful repository context incrementally as development reveals it. Do not pursue exhaustive upfront documentation or turn every observation into a permanent rule.

## Assess and verify

Consider retaining insights that are durable, non-obvious, repository-specific, and useful to future work. Recurrence is a useful signal, not a threshold; ignore generic advice, transient details, and one-off mistakes.

Check relevant code, tests, configuration, and guidance where practical. Distinguish verified facts from uncertainty; resolve stale or conflicting guidance when evidence is clear, otherwise report the conflict.

## Choose a destination and format

Choose based on audience, timing, scope, existing sources of truth, and target-tool support:

- Use project documentation for human contributors; use AI guidance when an agent needs the information during relevant work.
- Scope guidance to matching files when possible; use global instructions only for rules that apply across the repository. Use on-demand resources when their discovery and loading fit better.
- Prefer the narrowest supported destination. Update or link to an existing source of truth only if the intended audience or agent can reliably discover and access it when needed; otherwise, capture the minimum necessary information in an appropriate, supported location.
- Optimize useful guidance per token: keep automatically loaded instructions lean and place additional detail in on-demand resources when supported.

Validate the actual target tool's format, schema, scope syntax, and discovery behavior before relying on them. Support varies by tool, host, and version; do not assume a field such as `applyTo` has one universal type or syntax.

## Make and report changes

When the evidence and destination are clear and the change is low risk, edit the relevant workspace file directly without asking permission for routine edits. For consequential ambiguity, explain the options and ask or propose before editing.

Preserve unrelated working-tree changes. Edits are proposals for developer review: do not stage, commit, or push. Inspect the diff and perform proportionate validation. Report what changed, where it was placed, and what was actually inspected or verified; do not imply format validation or tool loading was tested unless it was. If no worthwhile improvement is justified, leave files unchanged and say so.
