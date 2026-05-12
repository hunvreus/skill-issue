# Agent Rules

## Communication
- Keep responses concise, technical, and MECE.
- Avoid filler or praise language.
- If scope is partial, state exactly what is not implemented.

## Naming
- Prefer short names (ideally one word) for tables, columns, symbols, and files.
- Use longer names only when clarity requires it.

## Architecture
- Keep route handlers thin; move validation, permissions, and DB logic into server services.
- Keep reusable UI in `src/components`, client API helpers in `src/lib`, and server behavior in `src/server`.
- Back models with Drizzle schemas and migrations.
- Prefer small, function-first modules with clear ownership of orchestration vs side effects.

## UI Components
- Add UI primitives through shadcn registry (`pnpm dlx shadcn@latest add ...`) instead of hand-rolled copies.
- Prefer standard shadcn composition patterns.

## Code Style
- Keep control flow explicit; prefer readable loops/state transitions over clever abstractions.
- Prefer simple deterministic structures (`Map`, arrays, plain objects).
- Use practical error handling and logging with explicit failure paths.

## TypeScript
- Keep strict types at boundaries: explicit public API types, typed imports, narrow interfaces.
- Avoid `any`; if unavoidable, keep scope narrow and document why.
- Verify dependency typings before inferring external API shapes.
- Use top-level type imports (no inline/dynamic type imports).
- Do not change behavior just to silence dependency type errors; fix or upgrade the dependency path.

## Change Management
- Do not preserve backward compatibility unless requested.
- Ask before removing behavior that appears intentional.
- Keep user-facing bindings/config controls data-driven, not hardcoded.
- After large changes/removals, prune dead code and simplify touched dependencies.

## Docs and Comments
- Prefer self-explanatory code; comment only non-obvious intent, invariants, edge cases, and tradeoffs.
- Public modules/functions need short contract docs (inputs, outputs, side effects, failures).
- Keep docs/snippets in sync with behavior; remove stale docs/comments during refactors.
- Keep technical prose concise and actionable.

