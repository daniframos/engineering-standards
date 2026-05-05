# Repository Guidelines

## Project Structure & Module Organization

Use the existing .NET solution layout. Keep API endpoints or controllers focused on transport concerns, application services focused on use cases, domain code focused on business rules, and infrastructure code focused on persistence or external integrations.

## Build, Test, and Development Commands

Use the commands supported by the solution. Common commands are `dotnet restore`, `dotnet build`, `dotnet test`, and `dotnet run --project <ProjectName>`; only rely on projects and solution files that exist in the repository. Keep command examples runnable from the repository root.

## Coding Style & Naming Conventions

Follow the repository `.editorconfig` when present. Use explicit, domain-specific names for classes, methods, DTOs, commands, and handlers. Avoid generic suffixes such as `Manager` unless they match an established project pattern.

Prefer dependency injection through constructors. Keep methods small and focused, avoid deep nesting, and prefer early returns for guard clauses. Use nullable reference types consistently when enabled.

## Testing Guidelines

Use the test framework already configured by the solution, commonly xUnit, NUnit, or MSTest. Name tests after the behavior they verify, such as `CreateOrder_ReturnsValidationError_WhenCustomerIsMissing`. Mock external integrations unless the test intentionally covers a real integration boundary.

## Commit & Pull Request Guidelines

Follow the repository commit convention. If none exists, use Conventional Commits such as `feat: add order validation` or `fix: return not found for missing customer`. Pull requests should describe API changes, database migrations, configuration changes, and verification performed.

## Agent-Specific Instructions

Do not hardcode secrets, connection strings, or sensitive URLs. Use configuration providers, environment variables, user secrets for local development, or the platform secret store. Keep exception messages useful and avoid exposing stack traces or internal details to API consumers.
