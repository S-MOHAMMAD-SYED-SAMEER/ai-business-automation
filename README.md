# AI Business Automation Agency

Portfolio and flagship project monorepo. See [project-brief_3.md](./project-brief_3.md) for the full
plan and [CLAUDE.md](./CLAUDE.md) for the working rules that govern this repo.

## Status

Lean portfolio foundation (Task 1) — in progress. **Project 1 (Sales-Recovery Support Agent) is
complete** — RAG, business tool-calling, SQLite memory, proactive-signal detection, guardrails, and
an evaluation harness, all locally runnable and tested. See
[sales-recovery-agent/README.md](./sales-recovery-agent/README.md) for how to run it and
[sales-recovery-agent/PROJECT-1.md](./sales-recovery-agent/PROJECT-1.md) for the case-study
write-up. Not deployed. Projects 2–3 (Inbox-to-CRM Agent, Explainable ATS) have not started.

## Structure

```
portfolio/              React + TypeScript + Tailwind site (Welcome, About, Skills, Projects, Contact)
sales-recovery-agent/   Project 1 — Sales-Recovery Support Agent (Node + Express + Claude API)
```

## Portfolio — local development

```
cd portfolio
npm install
npm run dev
```

## Stack

- **Portfolio:** Vite, React 18, TypeScript, Tailwind CSS — deployed on Vercel.
- **Project 1 (Sales-Recovery Support Agent):** Node + Express, Gemini (dev-time default; Claude
  adapter also implemented) via a provider-agnostic abstraction, Chroma (local) for RAG, SQLite
  for memory. Not yet deployed — local dev only.
- **Projects 2–3 (not yet started):** Node on Railway/Render, Claude API (Haiku 4.5 / Sonnet 5).
