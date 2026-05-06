# Repository Guidelines

## Project Structure & Module Organization

Use the existing Angular project layout. Keep page components, visual components, services, routes, guards, interceptors, state, and domain logic separated according to the repository pattern. Centralize HTTP calls in services, clients, or dedicated data-access layers.

## Build, Test, and Development Commands

Use the package manager already configured by the project. Common commands are `npm start`, `npm test`, `npm run lint`, and `npm run build`; only rely on them when they exist in `package.json`. Document any new script added to the project.

## Coding Style & Naming Conventions

Use TypeScript with strict type checking when the project already supports it. Avoid `any`; use `unknown` when the type is uncertain and narrow it before use. Prefer explicit types for inputs, outputs, return values, service contracts, and domain objects.

Prefer type inference when the type is obvious. Keep components, directives, pipes, and services small and focused. Use clear names for components, inputs, outputs, signals, services, methods, and handlers.

Use standalone components instead of NgModules. Do not set `standalone: true` inside Angular decorators when using Angular v20 or newer, because it is the default.

Use `input()` and `output()` functions instead of decorators. Use `inject()` instead of constructor injection. Set `changeDetection: ChangeDetectionStrategy.OnPush` in component decorators.

Use signals for local state and `computed()` for derived state. Avoid derived state when a value can be calculated from existing signals, inputs, or observable data. Do not use `mutate` on signals; use `set` or `update`.

Prefer Reactive Forms instead of Template-driven Forms. Prefer inline templates for small components. When using external templates or styles, use paths relative to the component TypeScript file.

Do not use `@HostBinding` or `@HostListener`; declare host bindings inside the `host` object of the `@Component` or `@Directive` decorator.

Do not use `ngClass`; use `class` bindings instead. Do not use `ngStyle`; use `style` bindings instead.

## Template Guidelines

Keep templates simple and avoid complex logic. Use native control flow with `@if`, `@for`, and `@switch` instead of `*ngIf`, `*ngFor`, and `*ngSwitch`.

Use the `async` pipe to handle observables. Do not assume globals such as `new Date()` are available in templates.

Use `NgOptimizedImage` for static images. Do not use `NgOptimizedImage` for inline base64 images.

## Services & State Management

Design services around a single responsibility. Use `providedIn: 'root'` for singleton services.

Keep state transformations pure and predictable. Normalize or validate received data when APIs may return inconsistent formats.

## Testing Guidelines

Test user behavior instead of internal implementation details. Use the Angular testing utilities already configured by the project. Cover critical flows, error states, empty states, validation behavior, and accessibility-sensitive behavior when tests are requested or already expected by the project.

## Commit & Pull Request Guidelines

Follow the repository commit convention. If none exists, use Conventional Commits such as `feat: adicionar painel de resumo da conta` or `fix: tratar resposta vazia da API`. Pull requests should describe UI behavior changes and include screenshots when visual output changes.

## Agent-Specific Instructions

Preserve basic accessibility. The UI must follow WCAG AA minimums, including labels, alternative text, keyboard navigation, focus management, color contrast, and ARIA attributes where applicable.

Handle loading, error, and empty states. Do not hardcode URLs, tokens, credentials, or secrets.
