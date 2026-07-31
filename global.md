# Repository Guidelines

## Project Structure & Module Organization

Respect the existing project architecture. Keep source code, tests, assets, and documentation in the directories already used by the repository. Do not introduce large cross-cutting structure changes unless they are necessary for the requested work.

## Build, Test, and Development Commands

Use the commands already documented by the project. Preserve CI/CD compatibility and avoid adding local-only commands. When introducing a new tool, document how to run it and explain why it is needed.

## Coding Style & Naming Conventions

Always write code in Brazilian Portuguese.

Avoid `var` unless the language or framework convention clearly prefers it. Keep functions between 4 and 20 lines when practical, and split files before they exceed 500 lines or mix responsibilities.

Use one responsibility per function and module. Prefer explicit types; do not use `any`, `Dict`, or untyped functions where stronger types are available. Use specific, unique names and avoid generic names such as `data`, `handler`, or `Manager`.

Prefer early returns over nested `if` blocks, with no more than two indentation levels. Remove duplication by extracting shared logic into a function or module. Exception messages must include the offending value and the expected shape.

Prefer idiomatic code over personal preference. Generated code must follow the dominant conventions already present in the repository for the target language, framework, and architectural style, except when the user explicitly requests a different approach or convention.

## Testing Guidelines

Do not add tests unless explicitly requested. When tests are requested, cover the behavior being changed and include negative cases for validation or error handling.

Do not run smoke tests. All tests will be performed manually.

## Commit & Pull Request Guidelines

Do not create commits unless explicitly requested by the user.

Even when the user explicitly requests a commit, create commits only for the specific changes requested. Do not create automatic, broad, or unrelated commits.

Follow Conventional Commits:

- `feat:` for new features.
- `fix:` for bug fixes.
- `docs:` for documentation.
- `refactor:` for refactoring.
- `test:` for tests.
- `chore:` for maintenance.

Write commit messages and pull request descriptions in Brazilian Portuguese unless the repository specifies another language.

## Agent-Specific Instructions

Always write generated user-facing text in Brazilian Portuguese unless the user asks for another language. Keep existing comments during refactoring because they may carry intent and context. Write comments that explain why, not what, and reference issue numbers or commit SHAs when a line exists due to a specific bug or upstream constraint.

Do not add fallbacks unless explicitly requested. Do not expose secrets, tokens, passwords, or sensitive URLs in code or logs.

If the project has a file named openapi.yaml, lsp.yaml, simple ignore-it.