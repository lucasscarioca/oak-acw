# Oak ACW Agent Guide

This repository is a collection of OpenCode agents and workflow artifacts.
It is not an application codebase, so expect mostly Markdown and config.

## Scope and layout

- Primary agents live in `.opencode/agent/`.
- Skills live in `.opencode/skills/`.
- Repo docs live at the root (for example, `README.md`).
- Avoid editing `.opencode/node_modules/`.

## Available agents

- Core: planning-first orchestrator.
- Worker: generalist execution subagent.

## Build, lint, and test commands

There are currently no build, lint, or test scripts configured in this repo.
Do not invent commands. If you add tooling later, update this section.

## How agents should work here

- Treat this repo as a documentation and configuration store.
- Prefer small, focused edits to Markdown files.
- Keep agent definitions minimal and readable.
- If a request spans multiple files, summarize changes per file.

## Agent definition conventions

- Follow the OpenCode docuemntation.
- Files are Markdown with YAML frontmatter.
- Agent filenames are lowercase (for example, `core.md`).
- The H1 should match the agent name (Title Case).
- Use XML tags for structure inside the prompt body.
- Keep instructions explicit and action-oriented.
- Add only necessary comments; avoid clutter.

### YAML frontmatter

- Use `description`, `model`, and `mode` when relevant.
- Prefer explicit `permission` blocks only when needed.
- Keep indentation at two spaces.
- Do not include trailing spaces.

### Descriptions and modes

- Primary agents should have a concise, 3-word description.
- Subagents should include usage examples in the description block.
- Use `mode: primary` for user-facing agents.
- Use `mode: subagent` for task-only agents.

### Prompt structure

- Start with a clear role statement.
- Follow with instructions, workflow, and output format.
- Include persistence and tool-usage reminders when relevant.
- Avoid excessive verbosity; keep prompts direct.

## Formatting and Markdown

- Keep paragraphs short and focused (2-4 sentences max).
- Use lists for sequences or requirements.
- Use fenced code blocks for file paths or commands.
- Prefer ASCII unless a file already uses Unicode.

## Naming conventions

- Agent files: lowercase names, no spaces.
- Headings: Title Case for top-level sections.
- Section labels: concise, consistent phrasing.
- Example names: use realistic, short identifiers.

## Tooling and safety

- Prefer minimal changes over refactors.
- Do not edit files outside this repo without explicit request.
- Do not add new dependencies unless necessary.
- Document any new workflows in `README.md`.

## Updating this file

- Keep this document around 150 lines.
- Reflect new agents in the "Available agents" section.
