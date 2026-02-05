# Oak ACW

Oak ACW (Oak Agentic Coding Workflow) is a small collection of agentic coding tools, agents, skills, prompts, and workflows for OpenCode. This repo is not a codebase; it is a shared, battle-tested setup for daily agentic coding.

## What is available

- **Core**: primary, planning-first orchestrator agent that designs detailed plans and delegates execution.
- **Worker**: generic execution subagent used by Core for exploration, implementation, and documentation tasks.

## How it works

Core acts as a plan-first orchestrator. For anything beyond trivial tasks, it:

1. Produces an Overview Plan for user approval.
2. Derives an Execution Plan per atomic task.
3. Delegates each task to Worker.
4. Reviews results and continues until the plan is complete.

Worker is a generalist worker. It follows Core's prompt, uses tools to execute, and reports back with results, file changes, and commands run.

## Install

You can install the agents either per-project or globally.

### Project (repo-local)

Fetch the agent files into your project:

```bash
OAK_ACW_RAW="https://raw.githubusercontent.com/lucasscarioca/oak-acw/main"
mkdir -p .opencode/agent
curl -L "$OAK_ACW_RAW/.opencode/agent/core.md" -o .opencode/agent/core.md
curl -L "$OAK_ACW_RAW/.opencode/agent/worker.md" -o .opencode/agent/worker.md
```

### Global

Fetch the agent files into your global config directory:

```bash
OAK_ACW_RAW="https://raw.githubusercontent.com/lucasscarioca/oak-acw/main"
mkdir -p ~/.config/opencode/agent
curl -L "$OAK_ACW_RAW/.opencode/agent/core.md" -o ~/.config/opencode/agent/core.md
curl -L "$OAK_ACW_RAW/.opencode/agent/worker.md" -o ~/.config/opencode/agent/worker.md
```

Notes:

- If you only want Core, copy only `core.md`.
- If you want delegation to work out of the box, copy both.

## Usage

Select Core as your active agent in OpenCode, then describe the task. Core will draft an Overview Plan for approval, then delegate Execution Plan tasks to Worker. For very simple tasks, it may act directly.

## Repository layout

```
.opencode/
  agent/
    core.md
    worker.md
```
