# Oak ACW

Oak ACW (Oak Agentic Coding Workflow) is a small collection of agentic coding tools, agents, skills, prompts, and workflows for OpenCode. This repo is not a codebase; it is a shared, battle-tested setup for daily agentic coding.

## What is available

- **Skipper**: primary, planning-first orchestrator agent that designs detailed plans and delegates execution.
- **Deckhand**: generic execution subagent used by Skipper for exploration, implementation, and documentation tasks.

## How it works

Skipper acts as a plan-first orchestrator. For anything beyond trivial tasks, it:

1. Produces an Overview Plan for user approval.
2. Derives an Execution Plan per atomic task.
3. Delegates each task to Deckhand.
4. Reviews results and continues until the plan is complete.

Deckhand is a generalist worker. It follows Skipper's prompt, uses tools to execute, and reports back with results, file changes, and commands run.

## Install

You can install the agents either per-project or globally.

### Project (repo-local)

Fetch the agent files into your project:

```bash
OAK_ACW_RAW="https://raw.githubusercontent.com/lucasscarioca/oak-acw/main"
mkdir -p .opencode/agent
curl -L "$OAK_ACW_RAW/.opencode/agent/skipper.md" -o .opencode/agent/skipper.md
curl -L "$OAK_ACW_RAW/.opencode/agent/deckhand.md" -o .opencode/agent/deckhand.md
```

### Global

Fetch the agent files into your global config directory:

```bash
OAK_ACW_RAW="https://raw.githubusercontent.com/lucasscarioca/oak-acw/main"
mkdir -p ~/.config/opencode/agent
curl -L "$OAK_ACW_RAW/.opencode/agent/skipper.md" -o ~/.config/opencode/agent/skipper.md
curl -L "$OAK_ACW_RAW/.opencode/agent/deckhand.md" -o ~/.config/opencode/agent/deckhand.md
```

Notes:

- If you only want Skipper, copy only `skipper.md`.
- If you want delegation to work out of the box, copy both.

## Usage

Select Skipper as your active agent in OpenCode, then describe the task. Skipper will draft an Overview Plan for approval, then delegate Execution Plan tasks to Deckhand. For very simple tasks, it may act directly.

## Repository layout

```
.opencode/
  agent/
    skipper.md
    deckhand.md
```
