# The Context Flywheel

A lightweight GitHub Copilot CLI plugin with one skill for capturing useful repository knowledge as development reveals it. It favors focused, incremental updates over exhaustive upfront documentation.

[Read the blog post: The Context Flywheel: A Pragmatic Approach to Context Engineering](https://dev.joesturge.com/p/the-context-flywheel-a-pragmatic-approach-to-context-engineering/)

## Install

Install the plugin from this repository's marketplace with the GitHub Copilot CLI:

```sh
gh copilot -- plugin marketplace add joesturge/context-flywheel
gh copilot -- plugin install context-flywheel@context-flywheel-marketplace
```

The `gh copilot` commands launch the Copilot CLI; its availability and plugin support are required.

<details>
<summary>Install the skill manually</summary>

Copy `skills/context-flywheel/SKILL.md` from this repository into your project at `.github/skills/context-flywheel/SKILL.md`. In an active Copilot CLI session, run `/skills reload` to reload it. [GitHub Copilot agent skills](https://docs.github.com/en/copilot/concepts/customizations/agent-skills) are also supported in the Copilot app, cloud agent, VS Code, Visual Studio, and JetBrains, subject to product versions. Check the target surface's instructions because skill locations and setup can differ.

</details>

## Use

In GitHub Copilot CLI, invoke the skill when finishing a task or when repository friction reveals a potentially useful pattern:

```text
/context-flywheel [optional additional context]
```

The skill checks whether the insight is durable and worth keeping, verifies it against relevant repository evidence where practical, and looks for conflicting or stale guidance. When justified, it edits the narrowest suitable existing documentation or AI guidance. It treats unverified claims as uncertain, avoids generic advice and one-off mistakes.

The marketplace commands and invocation shown here are for GitHub Copilot CLI. The technique can inform work with other AI tools, but compatible skill formats, file locations, discovery, and loading behavior vary; this repository does not promise the same plugin installation or invocation across tools.

## Developer control

The skill runs when invoked; it does not monitor work or capture context automatically. Any edits stay reviewable in the working tree. The developer decides whether to amend, keep, discard, or commit them; the skill does not stage, commit, or push changes. This is a low-maintenance practice, not a replacement for human review or occasional upkeep.
