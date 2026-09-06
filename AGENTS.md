# Global Project Guidelines

## Workflow

- Before editing, inspect the project's documentation, configuration, scripts, tests, and Git status when present. Follow existing conventions, preserve user changes, and avoid unrelated refactors, upgrades, or dependency changes.
- Keep temporary, generated, and auxiliary files inside the project and clean them up. Choose verification proportional to the change, prioritizing focused checks over low-value tests. Do not add tests for reversible, low-impact changes that merely restate the implementation unless their risk warrants it.

## Communication and Decisions

- When an uncovered issue could affect scope or results, explain its importance, assumptions, and options before asking for a decision. Otherwise, use reasonable defaults and proceed with in-scope changes.

## Dependencies and Environments

- Prefer `pnpm` for new JavaScript/TypeScript projects; use `uv`, `pyproject.toml`, `uv.lock`, and a project-local `.venv` following `.python-version` for new Python projects.
- Preserve existing package-manager, dependency, lockfile, and virtual-environment conventions. Do not migrate tooling or refresh lockfiles without a clear reason, and do not manually edit generated files or virtual environments. Ask before installing global tools.

## Directories, Files, and Naming

- Separate source, scripts, tests, documentation, generated artifacts, and configuration by responsibility. Keep only required entry points and configuration at the project root.
- Place new files in the directory that owns their responsibility, and distinguish development, test, and production variants clearly.
- Follow existing naming conventions for case, separators, suffixes, and abbreviations. Use names that state responsibility.

## Frontend

- Keep interfaces simple, reusable, and consistent. Follow existing design conventions; search for and reuse existing components, utilities, and dependencies before adding new ones. Avoid duplicate implementations and one-off visual rules.
- Maintain semantics, accessibility, layout, and copy; cover relevant loading, empty, error, interaction, and responsive states. Drive rendering from explicit state and centralize state changes.
- Keep styles, events, and layering predictable, especially around overlays and responsive layouts. Keep animations purposeful and restrained, and respect reduced-motion preferences.

## Backend

- Prefer platform capabilities and existing dependencies according to project scale; keep service boundaries clear and avoid unnecessary dependencies.
- For external inputs and exposed resources, use allowlists where appropriate, normalize and validate values, and provide safe fallbacks for unrecognized input.
- Use asynchronous I/O where appropriate. For network interfaces, return accurate status codes, content types, caching behavior, and CORS settings.
- Record enough server-side context to diagnose failures without exposing internal details. Keep development and test entry points separate from production.

## Documentation and Format

- Keep user, contributor, deployment, and maintenance documentation accurate and task-oriented.
- Use one H1 and a clear Markdown hierarchy. Label code blocks and use inline code for commands, paths, configuration keys, and API fields.
- Use descriptive links and consistent terminology. Keep examples current and copyable, and do not include temporary conversation or implementation history.

## Git and GitHub

- By default, only modify and verify the worktree; commit only when explicitly requested, combine complete logical changes into one Conventional Commit, and write the text after the colon in Chinese.
- Require explicit authorization for pushing, merging, releasing, remote changes, or history rewriting (`reset`, `rebase`, `squash`, `amend`, force-push); inspect diffs, verification, and scope first. `gh` is optional; prefer GitHub Actions when appropriate.

## Security and Network

- Never commit credentials, tokens, databases, logs, or machine-specific state.
- When a network request fails, try `http://127.0.0.1:7897` as an HTTP/HTTPS proxy when appropriate; it is not a global default.
