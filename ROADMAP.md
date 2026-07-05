# Handoff — Roadmap

Handoff turns a rough product idea into an engineering-ready spec: user stories,
acceptance criteria, edge cases, and an effort estimate. Built for PMs and founders
who need to hand something real to an eng team fast.

## How this file works
This is the daily agent's backlog. Each run, the agent finds the **first unchecked
box**, implements just that item, checks it off, and opens a PR. Keep items small
(one PR-sized chunk of work each). Reorder freely — the agent always takes the top
unchecked item, so put whatever's most important next at the top.

---

## Phase 0 — Foundation
- [ ] Init Next.js 14 (App Router) + TypeScript + Tailwind project
- [ ] Add `.env.example` with `ANTHROPIC_API_KEY`, set up env validation
- [ ] Wire a minimal `/api/generate` route that calls the Claude API and returns raw text
- [ ] Add ESLint + Prettier config, a basic CI workflow that runs `lint` + `build`

## Phase 1 — Core generation engine
- [ ] Design the structured output schema (problem statement, user stories,
      acceptance criteria, edge cases, technical tasks, effort estimate, open questions)
- [ ] Write the system prompt that turns a rough idea into that schema (JSON mode)
- [ ] Build the input form (single textarea + "Generate" button, loading state)
- [ ] Render the generated spec in a clean, readable layout (not just raw JSON)
- [ ] Add error handling for malformed model output (retry once, then show a friendly error)

## Phase 2 — Persistence & history
- [ ] Add Supabase project + `specs` table (id, input, output_json, created_at, user_id)
- [ ] Wire Supabase auth (magic link, no password)
- [ ] Save each generated spec to the DB
- [ ] Build a history/dashboard page listing past specs
- [ ] Build a spec detail page (view a saved spec, allow inline edits to any section)

## Phase 3 — Export & share
- [ ] Markdown export (downloadable .md matching the on-screen spec)
- [ ] Public shareable read-only link per spec (`/s/[id]`)
- [ ] PDF export (reuse the docx/pdf skill patterns — clean single-page layout)

## Phase 4 — Integrations
- [ ] Linear API export: turn "technical tasks" section into real Linear issues
- [ ] Jira API export (same idea, Jira's REST API)
- [ ] "Copy as Jira-formatted text" fallback for users without an integration set up

## Phase 5 — Polish
- [ ] Landing page (problem/solution, 3 example specs, CTA)
- [ ] Rate limiting on `/api/generate` (avoid runaway API costs)
- [ ] Mobile responsive pass
- [ ] Empty states, loading skeletons, toast notifications for all async actions
- [ ] Deploy to Vercel, connect custom domain if you have one

## Phase 6 — Stretch
- [ ] Voice input (record a rambling idea, transcribe, then generate)
- [ ] "Refine" button — give feedback on a generated spec, regenerate with that context
- [ ] Comment threads on individual spec sections (for actual PM/eng back-and-forth)
