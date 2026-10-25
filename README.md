# The Context Flywheel

A lightweight GitHub Copilot plugin with one skill for capturing durable repository knowledge and keeping documentation and AI guidance focused and up to date.

[Read the blog post: The Context Flywheel — A Cheap and Simple Technique for Pragmatic AI Development](https://dev.joesturge.com/p/the-context-flywheel-a-cheap-and-simple-technique-for-pragmatic-ai-development/)

## Install

```sh
gh copilot -- plugin marketplace add joesturge/context-flywheel
gh copilot -- plugin install context-flywheel@context-flywheel-marketplace
```

<details>
<summary>Install the skill manually without the plugin</summary>

Copy `skills/context-flywheel/SKILL.md` into your repository at `.github/skills/context-flywheel/SKILL.md`.

</details>

## How it works

Invoke the **Context Flywheel** skill when wrapping up a task or when a non-obvious repository pattern, recurring edge case, or documentation gap becomes clear. The skill reviews the current conversation, relevant repository changes, and existing documentation.

### Usage

In Copilot Chat, you can invoke the skill using the following:

```text
/context-flywheel [optional additional information]
```

It filters out generic advice, standard technology facts, and one-off fixes. For durable knowledge, it chooses the narrowest suitable home: path-scoped instructions, concise global Copilot instructions, another skill, a prompt, an agent when a distinct persona or tool boundary is useful, or project documentation for human contributors. It also checks whether relevant documentation is inaccurate or missing useful knowledge.

When an update is clear and low-risk, the skill edits the relevant workspace files and summarizes what changed and why. If the right update or destination is uncertain, it describes the insight and recommends an edit instead.

## You stay in control

The skill helps identify and place useful knowledge; it does not decide what deserves to become a permanent rule. Review its workspace changes, keep what adds value, and revise or discard anything that does not. Commit useful documentation and guidance alongside the related work.

The Rule of Three can be a useful personal signal for deciding when a pattern is worth capturing, but it is not a threshold enforced by the skill. Use your judgement: some knowledge is worth recording immediately, while other observations may never need a permanent change.
