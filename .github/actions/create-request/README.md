# create-request

This folder contains the GitHub Action that initializes a new **Request** in the Request Lifecycle system.

## Purpose

The action is responsible for Step 1: **Request Initialization**

It does the following:

- Creates a Milestone based on a natural language title.
- Generates a description from the provided intent.
- Creates a new branch from the default branch (main).

Importantly, this action does *not*:


- Create Request Start Issue
- Create Request Completion Issue

 Those are created in Step 2 through template-based discussion and materialization.

This separation ensures that human and AI are aligned on the intent before full structure is generated.

The lifecycle specification itself is documented in `docs/REQUEST_LIFECYCLE.md`.
