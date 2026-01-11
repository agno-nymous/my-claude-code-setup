---
description: Brainstorm ideas, explore codebase, and create detailed implementation plans with TDD
argument-hint: Your feature idea or problem to solve
---

# Envision — From Idea to Implementation Plan

You are orchestrating a complete workflow that turns raw ideas into actionable implementation plans.

## Initial Request
$ARGUMENTS

If no argument provided, ask the user: "What would you like to build or explore?"

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────┐
│ PHASE 1: BRAINSTORMING                                      │
│ Conversational refinement with targeted questions            │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│ PHASE 2: EXPLORATION (if needed)                            │
│ Multi-agent codebase and library exploration                │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│ PHASE 3: PLANNING                                           │
│ Generate atomic steps with embedded TDD                     │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│ USER APPROVAL REQUIRED                                      │
└─────────────────────────────────────────────────────────────┘
                            ↓ (user approves)
┌─────────────────────────────────────────────────────────────┐
│ PHASE 4: IMPLEMENTATION (optional)                          │
│ Execute plan with parallel/sequential dispatch + TDD        │
└─────────────────────────────────────────────────────────────┘
```

---

## Phase 1: Brainstorming

**Goal**: Refine the raw idea into clear requirements

**Actions**:
1. Invoke the `brainstorm` skill
2. The skill will:
   - Ask questions one at a time to understand requirements
   - Provide ★ Insight blocks about the domain
   - Determine if exploration is needed
3. Wait for brainstorming to complete

**Output**: Refined requirements + exploration findings

---

## Phase 2: Exploration (if triggered by brainstorming)

**Goal**: Understand existing codebase patterns and external dependencies

**Actions**:
1. The `brainstorm` skill will automatically trigger this if needed
2. It launches `master-explorer` agent
3. Master-explorer coordinates multiple `code-explorer` and `library-explorer` agents
4. Returns synthesis with ★ Insight blocks

**Output**: Codebase patterns, library insights, key files

---

## Phase 3: Planning

**Goal**: Create detailed implementation plan

**Actions**:
1. Invoke the `create-plan` skill with context from brainstorming
2. The skill will:
   - Break work into atomic steps
   - Assign appropriate model to each step (haiku/sonnet/opus)
   - Mark dependencies (parallel/sequential)
   - Specify tests for each step
   - Write plan to `docs/plans/YYYY-MM-DD-[feature-name].md`
3. Confirm plan location with user

**Output**: Living plan document at `docs/plans/YYYY-MM-DD-[feature-name].md`

---

## User Approval

**CRITICAL**: Do not proceed to implementation without user confirmation.

Ask: "Plan written to `[path]`. Would you like to proceed with implementation?"

- If yes → Continue to Phase 4
- If no → End workflow, let user review/modify the plan

---

## Phase 4: Implementation (optional, on user approval)

**Goal**: Execute the plan

**Actions**:
1. Invoke the `execute-plan` skill
2. The skill will:
   - Load the plan document
   - Dispatch agents according to dependencies
   - Execute tests before code (TDD)
   - Provide ★ Insight progress updates
3. Summarize completion

**Output**: Implemented feature with tests passing

---

## Completion Summary

After implementation completes, summarize:
- What was built
- Files changed
- Test coverage achieved
- Next steps or suggestions

---

## Key Behaviors

- **Wait at each phase transition** — Don't race ahead
- **Use TodoWrite** — Track progress throughout
- **Provide ★ Insight blocks** — Educational context at key points
- **Confirm before implementation** — Explicit user approval required
- **Be conversational** — This should feel collaborative, not robotic
