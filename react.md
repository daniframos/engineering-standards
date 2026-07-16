# --- react.md ---
# Repository Guidelines

## Project Structure & Module Organization

Use the existing React project layout. Keep page components, visual components, hooks, services, and domain logic separated according to the repository pattern. Centralize HTTP calls in services, clients, or dedicated hooks.

## Build, Test, and Development Commands

Use the package manager already configured by the project. Common commands are `npm run dev`, `npm test`, `npm run lint`, and `npm run build`; only rely on them when they exist in `package.json`. Document any new script added to the project.

Test user behavior instead of internal implementation details. Use React Testing Library when the project already uses it. Cover critical flows, error states, empty states, and validation behavior when tests are requested or already expected by the project.

To verify whether a change worked, prefer using the project's LSP.

## Coding Style & Naming Conventions

Use TypeScript when the project is already typed. Avoid `any` or implicit `any` in catch blocks; prefer explicit types for props, return values, and domain objects.

Keep components small and focused. Separate visual components, page components, and business logic. Extract hooks for reusable logic and avoid duplicating complex JSX. Use clear, semantic names for components, props, and event handlers (e.g., `handleClick`, `onUserSelect`).

Avoid derived state when a value can be calculated from props or existing data. Avoid `useEffect` for logic that can be handled during render or in event handlers. If a `useEffect` is strictly necessary for subscriptions, event listeners, or websockets, always implement a cleanup function.

Avoid using the array `index` as a `key` prop when rendering lists (`.map`) if a unique entity identifier is available. Avoid deep vertical prop drilling (more than 3 levels); use component composition, state hoisting, or the project's state management tool when sharing state across deeply nested components.

## Agent-Specific Instructions

Preserve basic accessibility. Use semantic HTML, labels, alternative text, and keyboard navigation where applicable. Handle loading, error, and empty states. Do not hardcode URLs, tokens, or secrets. Normalize or validate received data when APIs may return inconsistent formats.