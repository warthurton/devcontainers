# devcontainers
My customized dev-container base images

## GitHub Actions starting point

A good upstream pattern to start from is the official Dev Containers workflows:

- Scheduled rebuild/push example: https://github.com/devcontainers/images/blob/main/.github/workflows/push-dev.yml
- Publish + docs automation example: https://github.com/devcontainers/template-starter/blob/main/.github/workflows/release.yaml
- Action used by both: https://github.com/devcontainers/action

For this repo, the simplest starting point is usually:
1. `workflow_dispatch` + weekly `schedule` trigger
2. build/publish with `devcontainers/action`
3. optional PR creation for generated documentation updates
