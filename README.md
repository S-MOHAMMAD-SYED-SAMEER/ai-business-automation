# AI Business Automation Agency

Portfolio and flagship project monorepo. See [project-brief_3.md](./project-brief_3.md) for the full
plan and [CLAUDE.md](./CLAUDE.md) for the working rules that govern this repo.

## Status

All three flagship projects are complete.

- **Project 1 — Sales-Recovery Support Agent: live.** RAG, business tool-calling, SQLite memory,
  proactive-signal detection, guardrails and an evaluation harness. Demo:
  <https://sales-recovery-agent-j0mc.onrender.com>. See
  [sales-recovery-agent/README.md](./sales-recovery-agent/README.md) for how to run it and
  [sales-recovery-agent/PROJECT-1.md](./sales-recovery-agent/PROJECT-1.md) for the case-study
  write-up.
- **Project 2 — Inbox-to-CRM Agent: live.** Ingest → understand → resolve → decide → approve →
  execute, with a human approval gate on anything consequential and outbound sending disabled.
  Demo: <https://inbox-crm-agent.onrender.com>. See
  [inbox-crm-agent/README.md](./inbox-crm-agent/README.md).
- **Project 3 — Explainable ATS: built, not yet deployed.** Ranks candidates against a job spec
  from evidence quoted out of the CV and verified against it, with deterministic scoring. Runs
  locally; no hosted demo yet.

Both deployed demos run on free-tier hosting and sleep when idle, so the first request after a
quiet period is slow.

## Structure

```
portfolio/              React + TypeScript + Tailwind site (Welcome, About, Skills, Projects, Contact)
sales-recovery-agent/   Project 1 — Sales-Recovery Support Agent (Node + Express)
inbox-crm-agent/        Project 2 — Inbox-to-CRM Agent (Node + TypeScript + Express, React dashboard)
explainable-ats/        Project 3 — Explainable ATS (Node + TypeScript + Express, React dashboard)
docs/                   Specifications, audits and demo runbooks
```

## Portfolio — local development

```
cd portfolio
npm install
npm run dev
```

## Stack

- **Portfolio:** Vite, React, TypeScript, Tailwind CSS — deployed on Vercel.
- **Project 1 (Sales-Recovery Support Agent):** Node + Express, Gemini (dev-time default; Claude
  adapter also implemented) via a provider-agnostic abstraction, Chroma for RAG, SQLite for
  memory. Deployed on Render.
- **Project 2 (Inbox-to-CRM Agent):** Node + TypeScript + Express, Claude adapter (the demo replays
  recorded responses), SQLite/PostgreSQL behind one interface, React + Vite + Tailwind dashboard.
  Deployed on Render.
- **Project 3 (Explainable ATS):** Node 24 native TypeScript + Express 5, SQLite/PostgreSQL behind
  one interface, React + Vite + Tailwind dashboard. The current build reads CVs with a
  deterministic offline stand-in rather than a live model. Not yet deployed.
