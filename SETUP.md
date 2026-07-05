# Setup

1. Create a new repo on GitHub (public, so it shows on your contribution graph
   and recruiters can see it), clone it locally.
2. Copy these files (ROADMAP.md, CLAUDE.md, DEVLOG.md, .github/workflows/daily-build.yml)
   into the repo root. Commit and push.
3. Easiest path to get the GitHub App + secret configured: install Claude Code
   locally (`npm install -g @anthropic-ai/claude-code`), run `claude` in the repo,
   then run `/install-github-app` and follow the prompts. It installs the app and
   walks you through adding the ANTHROPIC_API_KEY secret.
   - Manual alternative: repo Settings -> Secrets and variables -> Actions ->
     New repository secret -> name it `ANTHROPIC_API_KEY`.
4. Go to the Actions tab, find "Daily Build", and run it manually once
   (workflow_dispatch) to confirm it opens a PR before trusting the cron schedule.
5. Every morning: check the PR, read the diff (you should understand every line —
   you may get asked about this in interviews), merge if it's good, or comment
   with a follow-up instruction if it's not.

## Cost
Each run is one Claude Code session doing one small task — should be low-single-digit
cents per day on the API for tasks this size. Worth keeping an eye on your
Anthropic Console usage page for the first week.

## Why PRs instead of direct commits to main
Keeps you the reviewer and gatekeeper, which matters for two reasons: quality
(nothing broken lands on main unreviewed) and honesty (you need to be able to
explain anything in this repo in an interview — reviewing daily is what makes
that true).
