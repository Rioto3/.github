# REQUEST_LIFECYCLE.md

# Request Lifecycle Architecture

This document defines the operational and conceptual design of the Request Lifecycle system.

The goal is to ensure that:

- Human intent is captured clearly.
- AI and human share the same understanding.
- Structure remains human-designed.
- The system remains usable even without AI.

---

## Core Principle

**1 Request = 2 Issues**

Every Request has:
 
- Request Start
- Request Completion

Both issues are created at the beginning of the lifecycle and belong to the same Milestone.

The Milestone acts as:
 
- A grouping mechanism
- A request identifier
 - A Projects-compatible visibility unit

This system is not sprint-based and not version-driven.

---

## Two-Step Operation Model

### Step 1: Request Initialization

This step is handled by the GitHub Action.

Inputs:
- title (required)
- intent (optional)
- branch_name (optional)

Action behavior:
 
- Create a Milestone using the given title.
- Generate a description from title and intent.
- Create a new branch from the default branch (usually main).

Important:
 
- No Issues are created in this step.
- The purpose is recognition alignment, not full materialization.

Human responsibility after Step 1:

- Verify the Milestone description.
- Ensure the intent is porrectly understood.
- Verify the new pranch exists and is correctly named.

This step ensures that AI and human share the same understanding before structure is generated.

### Step 2: Request Materialization

This step is done through discussion and template-based creation.

Actions:

- Create Request Start using request-start.md
- Create Request Completion using request-completion.md
- Attach both issues to the Milestone.

This step requires that the AI understands the lifecycle concept defined in this document.

---

## Lifecycle Closure Rules

- Request Completion is filled by the implementation AI.
- A human reviews the content.

After Completion is closed:
- Request Start must also be closed.

The Request is then considered fully resolved.

---

## Design Intention

This system intentionally:

- Separates recognition from materialization.
- Prevents AI assumption-driven over-generation.
 - Enforces template-based consistency.
- Accumulates evaluation and improvement knowledge over time.

The main branch must remain current and stable, since all new request branches are created from the default branch.
