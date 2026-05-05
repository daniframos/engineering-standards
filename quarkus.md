# Repository Guidelines

## Project Structure & Module Organization

Use the existing Quarkus layout. Prefer Panache Active Record instead of Repository unless an exception is justified. Encapsulate relevant queries in the entity or service instead of spreading persistence logic across the codebase.

## Build, Test, and Development Commands

Use the build tool already configured by the project. Common commands are `./mvnw quarkus:dev`, `./mvnw test`, `./gradlew quarkusDev`, and `./gradlew test`; only rely on commands that exist in the repository. Keep commands suitable for CI execution.

## Coding Style & Naming Conventions

Avoid blocking operations on IO threads. Use `final` whenever practical. Use `@Slf4j` for logging instead of other logging structures when Lombok is available in the project.

Include useful context in errors and logs, but avoid excessive logging in loops or high-volume flows. Keep endpoint names, paths, and contracts clear.

## Testing Guidelines

Write tests only when explicitly requested or when the repository already requires them for the change. Use `@QuarkusTest` for integration tests. Cover critical endpoints, validation, and main integrations. Mock external integrations when the real service is not part of the test.

## Commit & Pull Request Guidelines

Follow the repository commit convention. If none exists, use Conventional Commits such as `feat: add payment endpoint` or `fix: handle invalid document id`. Pull requests should describe REST contract changes, OpenAPI changes, persistence changes, and verification performed.

## Agent-Specific Instructions

Keep OpenAPI aligned with real behavior. Operation descriptions must be useful for governance and internal consumers; avoid generic descriptions such as "executes operation." Validation errors must return clear, traceable messages.

Use explicit transactions when changing state. Do not load large collections without pagination and avoid N+1 queries.
