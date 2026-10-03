# AI skills (public example repo)

Distribute instructions and executable helpers together in a `username/skills` repository, using the [Agent Skills format](https://agentskills.io/specification).

## Package

Keep each skill self-contained:

```text
skills/<skill-name>/
+-- SKILL.md       # YAML name/description, usage instructions and examples
+-- agents/        # Optional OpenAI metadata (openai.yaml)
+-- scripts/       # Runnable helpers and importable code
+-- references/    # Optional API documentation
```

Since Codex is also supported, see OpenAI's [skill structure](https://learn.chatgpt.com/docs/build-skills) and [`agents/openai.yaml` reference](https://learn.chatgpt.com/docs/build-skills#optional-metadata) for appearance, invocation policy and tool dependencies.

`SKILL.md` explains how to run the helpers or import them into code the agent writes. Document required runtimes, dependencies and authentication; installing a skill does not install its dependencies.

## Install

Developers need Node.js/npm and Git access to the repository. Run inside the destination project:

```powershell
npx skills@latest add username/skills
```

Select the skills and target agents, then choose **Project** and **Symlink**. See the [installer documentation](https://github.com/vercel-labs/skills#usage).

## Local control

The installed instructions and code live in `.agents/skills/<skill-name>`, with links for selected agents such as Claude Code. Developers can inspect and edit these files, and agents can run the helpers or write code using them. Review upstream updates before applying them to locally modified skills.

Keep destination repositories private if they commit private skill content. Generate agent links on each machine rather than relying on Windows junctions travelling through Git.
