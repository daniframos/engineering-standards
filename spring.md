# Repository Guidelines

## Project Structure & Module Organization

Use the existing Spring Boot layout. Keep Controllers focused on HTTP input and contract adaptation, Services focused on business rules, and Repositories focused on data access. Use DTOs for API input and output when exposing REST endpoints.

## Build, Test, and Development Commands

Use the build tool already configured by the project. Common commands are `./mvnw test`, `./mvnw spring-boot:run`, `./gradlew test`, and `./gradlew bootRun`; only rely on commands that exist in the repository. Keep CI-compatible command behavior.

## Coding Style & Naming Conventions

Use SLF4J for logging and avoid `System.out.println`. Prefer constructor injection and avoid field injection with `@Autowired`. Use `final` whenever practical. Avoid `var` unless the instantiated type is explicit and improves readability.

Do not place business logic in JPA entities, Controllers, or Repositories. Keep REST paths, method names, DTO names, and service names clear and domain-specific.

## Testing Guidelines

Use unit tests for business rules. Use `@SpringBootTest` only when the full application context is required. Prefer slice tests such as `@WebMvcTest` and `@DataJpaTest` when they fit the behavior under test. Mock external integrations in automated tests.

Always try to compile the project. Analyze the project and use the appropriate JDK version. The JDK is available in C:\ferramentas\openjdk, C:\Users\ramos\OneDrive\software\openjdk or C:\Ferramentas VM\openjdk.

## Commit & Pull Request Guidelines

Follow the repository commit convention. If none exists, use Conventional Commits such as `feat: add customer validation` or `fix: prevent duplicate records`. Pull requests should describe API contract changes, persistence changes, and verification performed.

## Agent-Specific Instructions

Use Bean Validation for simple input validation and keep domain validation in services. Return standardized errors with clear messages and never expose stack traces in HTTP responses.

Use `@Transactional` for write operations. Avoid N+1 queries, use pagination for potentially large result sets, and do not expose JPA entities directly when that couples the API to the database. Keep secrets out of `application.yml` and `application.properties`; use environment variables, Secrets, or the platform equivalent.
