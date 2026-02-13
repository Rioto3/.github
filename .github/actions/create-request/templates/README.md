# Request Lifecycle Templates

This directory defines the canonical lifecycle structure for a single **Request**.

Request represents one human intention – a desire, problem, improvement, or change.

This system intentionally avoids labels such as "bug", "feature", or "development".
Everything begins as a **Request**.

---

## Core Principle

**1 Request = 2 Issues**

Every Request must always generate:

- **Request Start**
- **Request Completion**

Both issues are created at the beginning of the lifecycle and belong to the same Milestone.

The Milestone acts only as:
- A grouping mechanism
- A request identifier
 - A Projects-compatible unit of visibility

It is not necessarily tied to a release or version.

---

## 1. Request Start

Perpose:
- Define the intention
- Document background and discussion
- Capture investigation notes
- Define the exit condition
- Track subtasks if necessary

This issue remains open during the entire lifecycle.

It is the management layer of the Request.

Subtasks may be attached to this issue if needed.

---

## 2. Request Completion

Perpose:
 - Record what was done
 - Provide verification details
- Capture evaluation and improvement ideas

This issue functions as:
- The execution report
- The AI handoff interface
- The historical record

It is completed by the implementation AI (or human implementer) and must be reviewed by a human before closing.

When **Request Completion** is closed,
**Request Start** must also be closed.

---

## Lifecycle Flow

 1. Human expresses intent.
 2. Milestone is created (natural language title).
 3. Request Start is created.
 4. Request Completion is created.
 5. Investigation and implementation occur.
 6. Completion is filled and reviewed.
 7. Completion is closed.
 8. Start is closed.

The Request is now fully resolved.

---

## Design Philosophy

- Structure is human-designed.
- AI operates within the structure.
- The system must remain usable even without AI.
 - Evaluation and Improvement sections exist to accumulate learning.
 - The goal is clarity and continuity, not automation for its own sake.

---

## Non-Goals

- This system is not sprint-based.
- It is not version-driven.
- Tag creation is optional.
 - Releases are separate from Request lifecycle unless explicitly linked.

---

## Minimum UX Goal (v0.1.0)

The system should enable:

> A human expressing an intention 
 > A structured Request lifecycle being created 
> An implementation AI being able to start work using the Completion template  
 > A human reviewing and closing the lifecycle

This is the foundational layer for future expansion.

---

## Supervising AI

Supervising AI URL:
https://chatgpt.com/g/g-67f108960d8881918a6feaf1e143d982-githubcao-zuo-heruha-vshing-dai-xing-turu/c/698e69ae-4134-83a4-accd-f621f83d1a0a
