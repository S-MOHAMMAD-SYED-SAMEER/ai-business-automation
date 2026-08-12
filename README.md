# AI Business Automation Agency

Portfolio and flagship project monorepo. See [project-brief_3.md](./project-brief_3.md) for the full
plan and [CLAUDE.md](./CLAUDE.md) for the working rules that govern this repo.

## Status

Lean portfolio foundation (Task 1) — in progress. Project 1 (Sales-Recovery Support Agent) — M1
skeleton done, see [sales-recovery-agent/README.md](./sales-recovery-agent/README.md). Projects 2–3
(Inbox-to-CRM Agent, Explainable ATS) have not started.

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
- **Flagship projects (not yet started):** Node on Railway/Render, Claude API (Haiku 4.5 / Sonnet 5),
  Chroma or Qdrant, SQLite.
