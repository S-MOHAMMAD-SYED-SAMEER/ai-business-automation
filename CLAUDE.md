# CLAUDE.md — AI Business Automation Agency

**`project-brief_3.md` is the authoritative source of truth.** This file holds the permanent rules
distilled from it. Where the two conflict, the brief wins — and the brief is never modified without
Sameer's explicit instruction. Read the brief when full context is needed; do not duplicate it here.

## Roles

- **Claude:** architecture, all code, technical guidance.
- **Sameer:** testing, feedback, client calls, deployment logistics, purchases, account creation
  (GitHub, Vercel, Google Cloud, Railway/Render, Stripe/Payoneer, Anthropic Console).

**Sameer must be able to explain every architecture decision** — why RAG, why this vector DB, what
happens when retrieval fails, how the agent decides to call a tool. So: when a non-trivial choice is
made, explain the *why* and the failure modes alongside the code. Never hand over a black box. This
is what makes the work real engineering experience rather than delegation.

## Positioning (fixed)

- **"AI Business Automation Agency."** Sell **outcomes** — recovered leads, faster response, less
  manual work — never AI features. All copy, portfolio text, and outreach follows this.
- **Lead niche: small international e-commerce / D2C stores.** Cart abandonment / lost leads is the
  quantifiable pain point. Do **not** broaden the niche until it is proven.
- **Service names (use these exact positioning labels):**
  - AI Customer Support & Sales Recovery (the chatbot)
  - Website Modernization & Conversion
  - Business Workflow Automation
  - AI Recruitment Intelligence (the ATS)
  - AI Inbox & Lead Management (lead-gen / CRM)

## LOCKED — Projects 1–3

**Projects 1–3's architecture, as scoped in the brief, is final.**

1. **Sales-Recovery Support Agent (chatbot)** — RAG (Chroma/Qdrant) + tool-calling (stock / order /
   discount checks) + proactive-signal detection + memory (SQLite) + eval harness + guardrails.
2. **Inbox-to-CRM Agent** — classify incoming messages, draft replies, auto-log to CRM. Visible
   3-step agent chain.
3. **Explainable ATS** — ranks resumes against a job spec via Claude Sonnet 5, outputs rank + a
   plain-language reason per candidate.

**No redesign, re-scoping, or expansion of Projects 1–3 before or during the initial build.** If a
better idea appears mid-build, it goes to the Phase 4 backlog — it is not entertained, prototyped,
or "quickly added." Do not propose alternative architectures for these three unless Sameer explicitly
reopens the decision. Once the three are done, **stop adding flagship projects**; priority shifts
entirely to closing and delivering client work.

## Phase 4 Backlog — NOT NOW

Everything in the brief's Phase 4 list is **out of scope**. None of it qualifies yet. Build one only
when a gate is genuinely met: **a client actually needs it**, **the problem is hit repeatedly in real
use**, **it fills a real gap Projects 1–3 don't cover**, or **it could become a product**. "It would
be cool" / "it's only a small addition" is not justification. If a Phase 4 item comes up, name the
gate it would have to clear and move on.

## Sequential Roadmap (order is not optional)

1. **Days 1–6 — Lean portfolio + flagship chatbot + first manual outreach, in parallel.**
   Portfolio: React + Tailwind, core sections only (Welcome, About, Skills, Projects, Contact with
   dual CTA). **No animation extras yet.** Day 3: chatbot demo working. Day 4: 20-prospect list built
   manually. Day 5: 5–10 personalized messages sent **by hand**.
2. **Week 2 — Validate, THEN automate.** Read the replies first. Only after that, build the outreach
   software (Google Places + Custom Search → 3-signal scoring: no website / no chat widget / slow
   site via free PageSpeed API → Haiku 4.5 drafts a personalized email → warmed-up verified domain →
   auto-logged to Sheet/CRM).
3. **Week 2–3 —** Inbox-to-CRM Agent. **Week 3–4 —** Explainable ATS.
4. **Weeks 4–10 —** client acquisition is the priority.
5. **After 5–7 orders —** automate the business side (intake → payment link → status tracking).
6. **Months 3–7 —** reinvest, raise prices, introduce retainers.

**Portfolio polish** (Framer Motion, Lottie, parallax, dark/light toggle, case-study write-ups,
GitHub links, pricing section) is *ongoing, parallel, slack-time only*. It **never** blocks outreach
or client work.

**Manual before automated is a rule, not a preference.** Real reply data is what makes the automated
outreach worth building; building it first optimizes against guesses.

## Workflow Rules

- **One task at a time. Propose a plan, wait for Sameer's approval, then build.** Do not create
  applications, scaffolds, or files ahead of an approved task.
- **Never modify `project-brief_3.md`.**
- **Commit to Git after each working session.** Code lives on this machine between sessions.
- Ask approval before editing files, running commands, deploying, or anything touching money or
  credentials. Nothing consequential happens silently.
- Never commit API keys or secrets. Keys go in `.env`, which stays gitignored; `.env.example` is
  committed instead.
- Claude cannot create accounts or make purchases — surface those as explicit asks for Sameer.
- `/model opusplan` for architecture decisions, default model for routine execution. Pro usage is a
  shared 5-hour window + weekly cap across chat and Code — don't burn it on rework.

## Technical Constraints

- **Stack:** React + Tailwind (portfolio, deployed on Vercel); Node on Railway/Render free tier
  (backends); Chroma/Qdrant (vectors); SQLite (chatbot memory).
- **Models:** **Claude Haiku 4.5** for the chatbot and outreach drafting (cost-driven);
  **Claude Sonnet 5** for ATS resume ranking. Do not silently upgrade model tiers — API spend is
  Sameer's real money.
- **Budget reality:** ₹2,000 Claude Pro is the only upfront cost; ~₹1,000 API starter credit and
  ~₹500/month hosting once outreach is live. **Free tiers by default.** Any proposal that adds a paid
  service must state the cost in INR and be approved first.
- **Never script automated access to Reddit or LinkedIn.** Discovery is Google search only
  (`site:reddit.com`, `site:linkedin.com/posts`); replies are written by Sameer, by hand.
- Every project must double as a resume-grade portfolio piece — clean, explainable, documented.

## Goals & Tracking

Long-horizon reference point: **$11,000–13,000 or 21–25 clients over ~4–7 months** — a reference
point, not a target to optimize against. Track **milestones** instead: first paying client → 3
clients → ₹1 lakh revenue → 5–7 clients + testimonials → raise prices → retainers/productized service
→ *then* reassess whether 21–25 clients is even the right path.

**Pricing ladder escalates:** clients 1–2 at $250–500 (proof + testimonial stage), 3–5 at
$500–1,000, 6+ at $1,000–2,500+, retainers $100–500+/month. Escalating prices mean the income goal
likely needs *fewer* clients, not a smaller goal.
