# Project

Node.js + TypeScript API with PostgreSQL.

## Commands

- `npm test` - run tests
- `npm run typecheck` - typecheck
- `npm run lint` - lint
- `npm run dev` - start development server

## Development rules

- Use TypeScript.
- Prefer simple solutions over abstractions.
- Do not introduce dependencies without a reason.
- Write tests for new behavior.
- Run relevant tests after changes.
- Run typecheck before considering a task complete.
- Do not modify SPEC.md unless explicitly asked.

## Architecture

Keep business logic separate from HTTP handling and database access.

## Database

PostgreSQL is the source of truth.
Database schema changes must use migrations.
