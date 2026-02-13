# PR-Centric Request Architecture

This document defines the PR-centric management model used in this repository.

It is intended for management-level AI systems that interact with GitHub. Implementation-focused AI only needs to fulfill the PR content.

---

## Current Operational Status

This repository is now operating under the PR-centric request model.

All new requests are initialized as structured Draft Pull Requests via GitHub Actions.

Legacy Issue/Milestone-based lifecycle mechanisms are decommissioned.

---

## 1. Core Principle

**PR = Request**

This repository does not use:

- Milestones
- Start/Completion Issues
- Lifecycle ceremony

 A draft Pull Request represents:

- Management intent (Background)
- Intended implementation strategy (Approach)

The PR is the single management unit.

---

## 2. Initialization Mechanism

Requests are initialized via:

`.github/actions/create-request`

as called by:

``.github/workflows/initialize-request.yml``

When triggered, the Action:

1. Creates a new branch from the default branch.
2. Adds a `.create-request` marker file containing the branch name.
3. Opens a structured Draft Pull Request.

By adding the marker file, a difference is guaranteed, allowing the PR to be created immediately.

---

## 3. Structured PR Format

Draft PR bodies are generated with the following structure:

```markdown
## Background

// management context

## Approach

// implementation strategy
```

Guidelines:

 - Inputs support Markdown.
- Use only `###` or smaller headings inside sections.
- Do not redefine ``## Background` or `## Approach` at the top level.

This structure is designed for management-level AI.

---

## 4. Completion Model

A request is considered complete when:

- The implementation is reviewed.
- The Pr is merged (squash merge recommended).

No additional closing artifacts exist.

---

## 5. Adoption in Another Repository

An AI with GitHub interface can adopt this model by:

- Copying `.github/actions/create-request` directory.
- Copying `.github/workflows/initialize-request.yml` file.
- Enabling `pull-requests: write` permissions for GitHub Actions.

Upon copy, the repository supports:

 - Structured request initialization
- PR-based management
- AI-aligned operation
