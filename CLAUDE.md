# CLAUDE.md

This repo is the user's **ideas board**: `ideas/index.html` (single page, Hebrew, RTL). Workflow details: `ideas/README.md`.

## When the user proposes an idea (in any wording, in any conversation)
Add it to the board right away. Don't ask whether to add it.
1. Add a new object to the `IDEAS` array in `ideas/index.html`. Use the next running id (`001`, `002`…), `status: 'feedback'`, and today's date in `created` and `updated`.
2. Fill in: `summary`, `goal`, `steps` (each with `who`), `owners`, `inScope`, `outScope`, `risks`, `questions`, `mockup` (illustrative HTML using the `.phone` / `.desk` / `m-*` kit) plus `mockNote`. Add `sources` and `notes` when they help.
3. Log the user's words and your summary in `feedback`, oldest first.
4. Render-check the page with Playwright (no page errors, no horizontal scroll at 390px). Then commit and push to this repo's default branch.
5. Republish the private page the user opens on their phone: use the Artifact tool, publish `ideas/index.html` with
   `url: https://claude.ai/artifact/5CZHNumZucewK7rt88LN2y`, and read it first if this conversation hasn't yet. Always keep this URL; never create a new artifact for the board.
6. Reply in Hebrew with a short summary of the plan and the open questions (the most important first).

## When the user gives feedback on an idea
Update that idea, add both sides to `feedback`, and bump `updated`. Then commit, push and republish the page (steps 4–5 above). Remove questions that have been answered. Move `status` to `decide` once nothing blocks a decision.

## Hard rule: nothing leaves the board until the user says so
- Do not implement, scaffold, create branches, or change code in any other repository (e.g. `tycoonster/aura-monday`) for an idea until the user explicitly says to proceed with it. A status of `decide` is not approval.
- Reading other repositories to make a plan accurate is fine. Writing to them is not.
- Once approved: set `status: 'go'`, then write a detailed spec before any code.

## Context
- Owner: Or, Aura Creative (advertising agency). The office system is work.aura-c.co.il (repo `tycoonster/aura-monday`: React + TypeScript, Vite, Tailwind, Supabase on the free plan, Netlify, Resend, Cloudflare Email Worker, GitHub on the free plan). Environments: `aura-dev`, `aura-prod`.
- The user prefers zero-cost solutions, or minimal cost if there is no other way.
- Mockups must say they are illustrative. Mark any made-up names or numbers as made up.
