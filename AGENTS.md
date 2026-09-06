# Global Project Guidelines

## Workflow

- Before editing, inspect docs, manifests, lockfiles, scripts, tests, and Git status; follow project conventions, preserve user changes, and avoid unrelated refactors, upgrades, or lockfile refreshes.
- Keep temporary, generated, and auxiliary files inside the project and clean them up; choose targeted checks or full tests/builds by risk, and avoid low-value tests.

## Communication and Decisions

- If a plan involves an uncovered matter that affects the goal, scope, or result, explain its importance, options, and impact before asking; use reasonable defaults for details that do not affect the goal.
- Apply explicit in-scope changes or objections directly; when important assumptions, risks, or conflicts arise, explain the basis and ask the user to decide.

## Dependencies and Environments

- Prefer `pnpm` for new JavaScript/TypeScript projects; use `uv`, `pyproject.toml`, `uv.lock`, and a project-local `.venv` following `.python-version` for new Python projects.
- Do not migrate existing npm, pip, or `requirements.txt` projects without reason; do not maintain multiple lockfiles or manually edit generated files or virtual environments. Ask before installing global tools.

## Directories, Files, and Naming

- Separate source, scripts, tests, docs, and generated artifacts by responsibility; keep only entry points and required configuration at the root, place new files in the matching directory, and distinguish development, test, and production variants by suffix or directory.
- Follow ecosystem and existing naming conventions; keep case, separators, and suffixes consistent at each level, use names that state responsibility, and avoid vague abbreviations.

## Frontend

- Keep interfaces simple and components reusable; maintain consistent semantics, accessibility, layout, and copy, and cover loading, empty, error, hover, focus, and mobile states.
- Drive rendering from explicit state and centralize state changes; isolate styles, events, and layering for embedded, floating, or plugin UI, considering viewport, scrollbars, and window changes.
- Use standard icon-library assets selected by meaning, not hand-drawn approximations. When applicable, prefer `transform` and `opacity` for animation; match timing, curves, and direction to interaction semantics, avoid meaningless bounce or overshoot, and support `prefers-reduced-motion`.

## Backend

- Prefer platform capabilities and existing dependencies according to project scale; keep service boundaries clear and avoid dependencies for simple features.
- Use allowlists for routes, files, and resources; normalize and validate inputs and upstream metadata, limit access, and provide safe, predictable fallback when data is unrecognized.
- Default to asynchronous server I/O, adjusting for runtime characteristics when necessary; set accurate status codes, content types, caching, and CORS by interface need, and keep responses consistent.
- Record sufficient server-side error context without exposing internal details to clients; isolate development, hot-reload, and test entry points from production and remove temporary entries after verification.

## Documentation and Format

- Aim README and API docs at users, contributors, deployers, and maintainers; objectively cover purpose, installation, configuration, usage, testing, and deployment.
- Use one H1 and clear Markdown hierarchy; label code blocks, use inline code for commands, paths, configuration keys, and API fields, and keep examples copyable and current.
- Use descriptive link text and consistent terminology, language, and heading style; do not copy temporary conversation, negative feedback, or implementation history.

## Git and GitHub

- By default, only modify and verify the worktree; commit only when explicitly requested, combine complete logical changes into one Conventional Commit, and write the text after the colon in Chinese.
- Require explicit authorization for pushing, merging, releasing, remote changes, or history rewriting (`reset`, `rebase`, `squash`, `amend`, force-push); inspect diffs, verification, and scope first. `gh` is optional; prefer GitHub Actions when appropriate.

## Security and Network

- Never commit credentials, tokens, databases, logs, or machine-specific state.
- When a network request fails, try `http://127.0.0.1:7897` as an HTTP/HTTPS proxy when appropriate; it is not a global default.
