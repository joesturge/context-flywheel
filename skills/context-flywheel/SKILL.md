---
name: context-flywheel
description: "Use when finishing a task or noticing repository friction, to assess and capture durable knowledge in the right project documentation or AI guidance."
---

# The Context Flywheel

Help maintain useful repository context incrementally as development reveals it. Do not pursue exhaustive upfront documentation or turn every observation into a permanent rule.

## Assess and verify

Consider an insight only when it is durable, non-obvious, repository-specific, and useful to future work. A recurring pattern can be a good signal, not a required threshold: capture an important finding sooner when justified. Ignore generic programming advice, standard technology facts, transient details, and one-off mistakes.

Before treating a finding as authoritative, check relevant source code, tests, configuration, and existing documentation where practical. Separate verified facts from assumptions, hypotheses, and open questions. If evidence is insufficient, state the uncertainty instead of presenting an inference as fact. Check for conflicting or stale guidance; correct it when the evidence makes the right outcome clear, otherwise report the conflict.

## Choose a destination

Inspect existing guidance and place useful knowledge in the narrowest suitable destination supported by the target tooling:

- Path-scoped instructions for rules limited to particular files or paths. Check that `applyTo` matches the intended files where practical.
- Global instructions only for concise rules that genuinely apply across the repository.
- Skills, prompts, or agents when their supported formats and discovery behavior suit the knowledge.
- Project documentation for information intended for human contributors.

Prefer updating or linking to an existing source of truth over duplicating guidance. Do not promote local implementation details into global instructions. Tooling formats, discovery, and loading differ; do not assume one tool will load another tool's customization files.

## Make and report changes

When the evidence and destination are clear and the change is low risk, edit the relevant workspace file directly. Preserve unrelated working-tree changes. Do not stage, commit, or push; an edit is a proposal in the working tree, not developer acceptance. Do not ask permission for every routine edit. For consequential ambiguity, such as establishing a broad architectural rule, explain the options and ask or propose before editing.

Report what changed, why it is useful, and where it was placed. Distinguish files edited from sources inspected and behavior actually tested; do not claim verification merely because text was changed. If no durable improvement is justified, leave files unchanged and say so.
