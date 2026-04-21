# devcontainers

[![Build and Publish](https://github.com/warthurton/devcontainers/actions/workflows/build.yml/badge.svg)](https://github.com/warthurton/devcontainers/actions/workflows/build.yml)
[![devcontainer-python](https://img.shields.io/badge/ghcr.io%2Fwarthurton%2Fdevcontainer--python-published-brightgreen)](https://github.com/users/warthurton/packages/container/package/devcontainer-python)

Customized Dev Container images with automated build, publish, and doc generation.

## Repository Contents

Current structure:

```text
.
|- .github/
|  |- copilot-instructions.md
|  `- workflows/
|     `- build.yml
|- python/
|  `- devcontainer.json
`- README.md
```

## Containers

- `python/`: Python-based development container definition.

## CI/CD Pipeline

Workflow file: `.github/workflows/build.yml`

The workflow:

- Discovers all folders containing a `devcontainer.json`.
- Builds each container in a matrix using `devcontainers/ci`.
- Pushes images to GHCR on `main`.
- Generates container documentation from resolved config.
- Safely skips docs copy when no `docs-*` artifacts are present.
- Opens a PR when generated docs changed.

### Triggers

- `push` to `main` when container/workflow files changed.
- `pull_request` when container/workflow files changed.
- Weekly scheduled rebuild (`0 6 * * 1`).
- Manual run via `workflow_dispatch`.

### Image Naming

Published image pattern:

`ghcr.io/<owner>/devcontainer-<container-folder>`

Example for this repo:

`ghcr.io/warthurton/devcontainer-python`

Published package:

- `devcontainer-python`: https://github.com/users/warthurton/packages/container/package/devcontainer-python

## Adding New Containers

1. Create a new folder (for example, `node/`).
2. Add a `devcontainer.json` in that folder.
3. Commit and push.

No workflow edits are required for discovery/build.
