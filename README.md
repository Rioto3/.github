# .github (Canonical Index)

This repository contains the canonical definitions, automation, and operating models for repositories under this account.

It serves as the central source of truth for cross-repository engineering standards.

---

## 1. Purpose

This `.github` repository:

- Defines the Engineering Operating Model
- Hosts canonical GitHub Actions
- Hosts canonical workflow definitions
- Enables AI-first cross-repository operations

---

## 2. Core Documents

- [OPERATING_MODEL.md](./OPERATING_MODEL.md)
    Engineering Operating Model (AI-First, Tag-Driven Trunk Model)

- [actions/create-sprint/README.md](./actions/create-sprint/README.md)
    Sprint initialization system

---

## 3. Canonical Workflows

- [workflows/create-sprint.yml](./workflows/create-sprint.yml)
    Manual dispatch entrypoint for sprint initialization.

    This file should be copied into target repositories to enable sprint automation.

---

## 4. AI-Oriented Design

Documentation in this repository is intentionally structured so that:

- An AI assistant can read it
- Reconstruct repository configuration
- Apply standards across multiple projects

---

## 5. How to Use in a New Repository

1. Read `OPERATING_MODEL.md` for the overall model.
2. Copy required workflows (e.g. create-sprint.yml).
3. Trigger workflow_dispatch to initialize a sprint.

---

## 6. Authority Statement

The latest version of documents and workflows in this repository is considered authoritative.

 Individual repositories may adapt when necessary, but this repository remains the canonical baseline.
