# Oak ACW

Oak ACW (Oak Agentic Coding Workflow) is a small collection of agentic coding tools, agents, skills, prompts, and workflows for OpenCode. This repo is not a codebase; it is a shared, battle-tested setup for daily agentic coding.

## What is available

- **Skipper**: primary, planning-first orchestrator agent that designs detailed plans and delegates execution.
- **Deckhand**: generic execution subagent used by Skipper for exploration, implementation, and documentation tasks.

## How it works

Skipper acts as a plan-first orchestrator. For anything beyond trivial tasks, it:

1. Produces a detailed plan.
2. Delegates atomic tasks to Deckhand.
3. Reviews results and continues until the plan is complete.

Deckhand is a generalist worker. It follows Skipper's prompt, uses tools to execute, and reports back with results, file changes, and commands run.

## Install

You can install the agents either per-project or globally.

### Project (repo-local)

Copy the agent files into your project:

```
.opencode/agent/skipper.md
.opencode/agent/deckhand.md
```

### Global

Copy the agent files into your global config directory:

```
~/.config/opencode/agent/skipper.md
~/.config/opencode/agent/deckhand.md
```

Notes:

- If you only want Skipper, copy only `skipper.md`.
- If you want delegation to work out of the box, copy both.

## Usage

Select Skipper as your active agent in OpenCode, then describe the task. Skipper will plan and delegate work to Deckhand automatically. For very simple tasks, it may act directly.

## Repository layout

```
.opencode/
  agent/
    skipper.md
    deckhand.md
```
