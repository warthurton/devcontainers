# Copilot Instructions

Keep the repository documentation current whenever container or pipeline changes are made.

## README Update Requirements

When editing container definitions, workflows, or publishing behavior, update README.md in the same change set.

Keep these sections accurate:

- Repository Contents: include the current top-level structure and key files.
- Containers: list each container folder that has a devcontainer.json.
- CI/CD Pipeline: reflect workflow behavior, trigger conditions, and major action usage.
- Image Naming: include the current GHCR naming convention and concrete examples.
- Published Packages/Badges: include one badge/link per published container image.
- Adding New Containers: keep setup steps aligned with current auto-discovery behavior.

## Documentation Style

- Prefer concise operational docs over historical notes.
- Avoid stale references to actions or files no longer used.
- Keep links pointing to repo-local workflow files and current package URLs.
