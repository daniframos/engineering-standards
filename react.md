# Repository Guidelines

## Project Structure & Module Organization

Use the existing React project layout. Keep page components, visual components, hooks, services, and domain logic separated according to the repository pattern. Centralize HTTP calls in services, clients, or dedicated hooks.

## Build, Test, and Development Commands

Use the package manager already configured by the project. Common commands are `npm run dev`, `npm test`, `npm run lint`, and `npm run build`; only rely on them when they exist in `package.json`. Document any new script added to the project.

## Coding Style & Naming Conventions

Use TypeScript when the project is already typed. Avoid `any`; prefer explicit types for props, return values, and domain objects.

Keep components small and focused. Separate visual components, page components, and business logic. Extract hooks for reusable logic and avoid duplicating complex JSX. Use clear names for components, props, and handlers.

Avoid derived state when a value can be calculated from props or existing data. Avoid `useEffect` for logic that can be handled during render or in event handlers.

## Testing Guidelines

Test user behavior instead of internal implementation details. Use React Testing Library when the project already uses it. Cover critical flows, error states, empty states, and validation behavior when tests are requested or already expected by the project.

## Commit & Pull Request Guidelines

Follow the repository commit convention. If none exists, use Conventional Commits such as `feat: add account summary panel` or `fix: handle empty API response`. Pull requests should describe UI behavior changes and include screenshots when visual output changes.

## Agent-Specific Instructions

Preserve basic accessibility. Use labels, alternative text, and keyboard navigation where applicable. Handle loading, error, and empty states. Do not hardcode URLs, tokens, or secrets. Normalize or validate received data when APIs may return inconsistent formats.
