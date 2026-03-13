# workflows

This directory contains workflows that run in this `.github` repository itself.

## initialize-request.yml

`initialize-request.yml` is intentionally kept here even though the same workflow template also exists in `workflow-templates/initialize-request.yml`.

The copy in `workflow-templates/` exists so repositories in the `Rioto3-org` organization can add the workflow through GitHub's workflow template UI.

The copy in `.github/workflows/` exists so this repository can also execute the workflow directly from its own Actions tab.

This duplication is intentional.

## Why both copies exist

- `workflow-templates/initialize-request.yml` is the distributable template
- `.github/workflows/initialize-request.yml` is the runnable workflow for this repository
- both call the centralized Action in `.github/actions/create-request`

The runtime logic is not duplicated in the workflow files themselves. The request initialization behavior remains centralized in the `create-request` Action.
