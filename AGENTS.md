# Global Project Guidelines

## Workflow

- Inspect the project's README, manifests, lockfiles, scripts, tests, and Git state before changing it.
- Follow project-specific conventions and preserve existing user changes.
- Keep edits focused; avoid unrelated refactors, upgrades, or lockfile refreshes.
- Keep temporary, generated, and auxiliary files within the current project; clean them up after use and do not leave files elsewhere unless explicitly required.
- Verify according to risk: targeted checks for small changes, full tests or builds for broader changes; do not overdesign tests with little behavioral value.

## Dependencies and Environments

- Prefer `pnpm` for new JavaScript/TypeScript projects and `uv` with `pyproject.toml`/`uv.lock` for new Python projects.
- Use a project-local `.venv` for Python and follow `.python-version`; avoid polluting the global environment.
- For existing npm, pip, or `requirements.txt` projects, evaluate migration during dependency or environment work, but keep the current tool when migration has a concrete cost.
- Do not maintain multiple lockfiles without a project-specific reason or edit generated lockfiles and virtual environments by hand.
- Ask the user before installing any necessary global tool.

## Frontend

- Keep interfaces simple and restrained; reuse components.
- Maintain semantic structure, accessibility, and consistency across component responsibilities, spacing, typography, color, states, and copy.
- Choose the concrete implementation from the project's goals, existing design system, and usage context.

## Documentation

- Write README and API documentation for users, contributors, deployers, and maintainers, not only for the current user.
- Prefer objective, durable, audience-oriented explanations of purpose, setup, configuration, usage, testing, and deployment.
- Do not copy temporary conversation requirements, negative feedback, or implementation history directly into documentation.

## Git and GitHub

- Prefer small commits representing complete logical changes and use Conventional Commits. Example: `chore: 首次提交`.
- Inspect diffs and verification results before committing; confirm scope before destructive operations, pushes, migrations, merges, or releases.
- GitHub CLI (`gh`) is a recommended, not mandatory, helper for GitHub project management.
- Prefer GitHub Actions for GitHub-hosted CI, build, and deployment automation when it fits the project.

## Security and Network

- Never commit credentials, tokens, databases, logs, or machine-specific state.
- When a network request fails, first try `http://127.0.0.1:7897` as an HTTP/HTTPS proxy when appropriate. This is not guaranteed to work and is not a project-wide default.
