# My Claude Code Setup

A complete Claude Code workflow featuring **brainstorming**, **TDD-based planning**, and **parallel execution** with intelligent model selection.

## Overview

This setup provides a systematic approach to feature development:

1. **Brainstorm** (`/brainstorm`) - Refine vague ideas into clear requirements through conversation
2. **Plan** (`/create-plan`) - Create detailed implementation plans with atomic steps and TDD specs
3. **Execute** (`/execute-plan`) - Execute plans with parallel agents, following TDD

## Quick Start

### Installation

#### Via Marketplace (One-Command)

```bash
claude skill marketplace add ashishthomaschempolil/my-claude-code-setup
```

#### Manual Installation

```bash
# Clone the repository
git clone https://github.com/ashishthomaschempolil/my-claude-code-setup ~/.claude/skills/my-claude-code-setup

# Or copy to your skills directory
cp -r . ~/.claude/skills/my-claude-code-setup
```

### Usage

```bash
# Start the workflow
/brainstorm

# After brainstorming completes, create a plan
/create-plan

# Execute the plan
/execute-plan
```

## Components

### Skills

| Skill | Description | Model |
|-------|-------------|-------|
| **brainstorm** | Conversational refinement of ideas with targeted questions | Opus |
| **create-plan** | Creates atomic implementation steps with model selection | Sonnet |
| **execute-plan** | Executes plans with parallel agents + TDD | Sonnet |

### Agents

| Agent | Description |
|-------|-------------|
| **master-explorer** | Orchestrates codebase and library exploration |
| **code-explorer** | Deep analysis of codebase architecture |
| **library-explorer** | Research on external libraries and tools |

### Commands

| Command | Description |
|---------|-------------|
| **/envision** | Quick trigger for the full envision workflow |

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

- Claude Code >= 0.7.0
- Claude Pro subscription (for Skills feature)
- Tools: AskUserQuestion, Task, Glob, Grep, Read, Write, Edit, Bash, TodoWrite, WebSearch

## Contributing

This is a personal workflow setup. Feel free to fork and adapt for your own needs!

## License

MIT
