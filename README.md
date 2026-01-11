# Envision Workflow Plugin

A complete Claude Code plugin featuring **brainstorming**, **TDD-based planning**, and **parallel execution** with intelligent model selection.

## Overview

This plugin provides a systematic approach to feature development:

1. **Brainstorm** - Refine vague ideas into clear requirements through conversation
2. **Plan** - Create detailed implementation plans with atomic steps and TDD specs
3. **Execute** - Execute plans with parallel agents, following TDD

## Quick Start

### Installation

#### Via Marketplace

First, add the marketplace:
```bash
/plugin marketplace add ashishthomaschempolil/my-claude-setup
```

Then install the plugin:
```bash
/plugin install envision-workflow@my-claude-setup
```

#### Manual Installation

```bash
# Clone the repository
git clone https://github.com/ashishthomaschempolil/my-claude-setup

# Test locally with --plugin-dir flag
claude --plugin-dir ./my-claude-setup
```

### Usage

```bash
# Start the workflow with the envision command
/envision-workflow:envision Your feature idea here

# Or use the skills directly:
# - brainstorm skill for idea refinement
# - create-plan skill for planning
# - execute-plan skill for implementation
```

## Components

### Skills

| Skill | Description |
|-------|-------------|
| **brainstorm** | Conversational refinement of ideas with targeted questions |
| **create-plan** | Creates atomic implementation steps with model selection |
| **execute-plan** | Executes plans with parallel agents + TDD |

### Agents

| Agent | Description |
|-------|-------------|
| **master-explorer** | Orchestrates codebase and library exploration |
| **code-explorer** | Deep analysis of codebase architecture |
| **library-explorer** | Research on external libraries and tools |

### Commands

| Command | Description |
|---------|-------------|
| **/envision-workflow:envision** | Full envision workflow - brainstorm, plan, execute |

## How It Works

```
User Idea
    ↓
┌─────────────────────────────────────────┐
│  Brainstorm: Refine through questions   │
│  - Purpose & goals                      │
│  - Constraints & requirements           │
│  - Success criteria                     │
│  - Codebase exploration (if needed)     │
└─────────────────────────────────────────┘
    ↓
┌─────────────────────────────────────────┐
│  Create Plan: Break into atomic steps   │
│  - Model selection per step             │
│  - Dependency marking (parallel/seq)    │
│  - Embedded TDD specifications          │
└─────────────────────────────────────────┘
    ↓
┌─────────────────────────────────────────┐
│  Execute: Dispatch agents               │
│  - Parallel execution where possible    │
│  - Tests BEFORE code (TDD)              │
│  - Progress tracking with insights      │
└─────────────────────────────────────────┘
    ↓
  Working Feature + Tests
```

## TDD Integration

This workflow embeds Test-Driven Development directly into the planning process:

- **Complexity Assessment** during planning determines TDD approach (Light/Standard/Full)
- **Test Specifications** are written for each implementation step
- **Behavior-based tests** verify WHAT, not HOW — surviving refactoring
- **Tests-first** is enforced during execution (write tests → implement → verify)

## Requirements

- Claude Code >= 1.0.33 (for plugin support)

## Contributing

This is a personal workflow setup. Feel free to fork and adapt for your own needs!

## License

MIT
