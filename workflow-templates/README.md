# workflow-templates

This directory contains workflow templates intended to be added to repositories in the `Rioto3-org` organization.

## Initialize Request

`initialize-request.yml` is the workflow template distributed to each target repository.

The copied workflow does not contain the full request initialization logic by itself. At runtime, it calls the centralized Action in this repository:

`Rioto3/.github/.github/actions/create-request@main`

That Action is responsible for the Request Lifecycle initialization defined in `.github/actions/create-request/REQUEST_LIFECYCLE.md`, including:

- creating a `request/<name>` branch from the default branch
- creating an empty commit so a PR can be opened immediately
- creating a structured Draft Pull Request with `## Background` and `## Approach`

## properties.json

`initialize-request.properties.json` is metadata for the GitHub workflow template UI.

It defines display information such as the template name, description, icon, category, and the workflow file pattern. It does not contain execution logic and does not control whether templates may be copied.

## Operating Model

This template is intended to be copied into another repository, while the execution logic remains centralized in this repository's `create-request` Action.

In practice, that means:

- the workflow file is added to each target repository
- the runtime behavior is shared from this repository
- changes to `create-request` can affect all repositories using the template

If a repository needs a fully self-contained implementation, the Action logic would also need to be copied or versioned separately rather than referenced from this repository.
