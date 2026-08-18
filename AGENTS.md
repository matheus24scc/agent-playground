# AGENTS.md

Guidance for automated agents working in this repository.

## Stack
TypeScript monorepo (npm workspaces). Node >= 20 required.
- `apps/api` — Express.js API, run with `tsx src/index.ts` (script: `dev`).
- `apps/web` — Next.js 14 App Router frontend (script: `dev`).
- `packages/db` — Prisma schema + client (PostgreSQL).
- `packages/ui` — shared UI TypeScript package (no build step yet).

## Install & verify
- Install: `npm ci` (a `package-lock.json` is committed for reproducible installs).
- Lint: `npm run lint` (delegates to workspaces; `apps/web` uses `next lint` with `eslint-config-next`).
- Test: `npm test` (delegates to workspaces; tests are placeholders in this scaffold).
- Audit: `npm audit` / `npm audit --omit=dev` (production only).

## Notes for agents
- This is the `agent-playground` repo and runs a public bug-bounty-style program.
  See `CONTRIBUTING.md` and `SECURITY.md` for eligibility and scope before submitting.
- Do not run long-lived dev servers in CI/checkup contexts; build/lint/test only.
- Keep changes minimal and safe; open PRs against a feature/checkup branch, never `main` directly.
