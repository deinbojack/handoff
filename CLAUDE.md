# Project guidelines for the agent

## What this project is
Handoff — a tool that converts a rough product idea into a structured,
engineering-ready spec. Read `ROADMAP.md` before doing anything.

## Rules for every run
1. Open `ROADMAP.md`. Find the first unchecked `- [ ]` item. That is your ONLY task
   this run. Do not jump ahead to other items, even if they look easy.
2. Implement it completely: working code, no TODOs/stubs left behind.
3. If the task involves UI, keep styling consistent with what already exists in the repo
   (check existing components before inventing new patterns).
4. Run `npm run lint` and `npm run build` before committing. Fix anything broken.
5. Check the box for the completed item in `ROADMAP.md` (`- [ ]` → `- [x]`).
6. Append a short entry to `DEVLOG.md` (see format at the top of that file).
7. Commit with a clear, specific message (not "update files").
8. Open a PR against `main`. Do not merge it yourself.

## Tech stack
Next.js 14 (App Router), TypeScript, Tailwind, Supabase (auth + Postgres),
Claude API for generation, deployed on Vercel.

## Things to never do
- Never commit secrets or `.env` files.
- Never force-push or rewrite history on `main`.
- Never mark more than one roadmap item complete in a single run.
- Never install a dependency not already needed for the current task without
  explaining why in the PR description.
