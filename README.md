# Patryk Sylwerski

Accounting office by day, automation and integrations the rest of the time. Based in Żory, Poland.
Computer Science student (AI specialisation, WSB Merito University). English C1.

Most of my code lives in **private repositories**: it either runs on client accounting data or belongs to small businesses I build for.
This page describes what each project does and how it is built. I am happy to walk through any of them on a call.

---

## SmartKsięgi: automation for an accounting office · C# / .NET 8 · private

A desktop app (WPF, single `.exe`) for the tax and accounting office where I work. The office runs on **InsERT nexo**, a Polish
accounting/ERP suite, with a separate database per client. A large part of the job was retyping the same data between systems.

- Modules for cash reports from PDF (OCR), purchase and sales invoices from **KSeF** (Poland's national e-invoicing system),
  timesheets from spreadsheets, client invoicing, and Allegro marketplace statements.
- Everything that writes to the books goes through nexo's **official API (Sfera)**, so the same validations apply as for manual work.
- **The app proposes, a person approves.** Every module has a dry-run mode that runs documents through the ERP engine
  and shows the result without saving anything.
- Result I measured: monthly client invoicing at the office went from about **12 hours to 2.5–3 hours**.

## Self-hosted mail automation · n8n · private

My own Gmail, handled by a self-hosted **n8n** instance on Windows.

- Sorts incoming mail into existing labels, sends a daily digest and prepares draft replies for me to review. Nothing is sent automatically.
- Google OAuth, secrets kept in a local `.env`, starts with Windows and checks that the service is up before launching a second copy.

## Offerly: job-application tracker · Python, FastAPI, Supabase · private

A tracker that reads the job-board emails you forward to it, so you do not have to keep a spreadsheet.

- Ingest by **email forwarding** instead of asking for full inbox access (OAuth) — less data, less trust needed.
- **Supabase Postgres with row-level security**: every user sees only their own rows, enforced in the database.
- Dashboard of what needs attention, saved answers for application forms, salary range next to the amount you declared.
- Tests with `pytest`, linting with `ruff`, CI on GitHub Actions.

## Client portal and internal CRM for a small web studio · Next.js, Supabase · private

Two connected apps for a two-person studio that builds websites for local businesses.

- **CRM**: companies, pipeline stages, tasks and outreach waves; meetings come from the Calendly API.
- **Client portal**: clients log in to see their project, documents and contract acceptance.
- Shared Supabase database with **row-level security**; staff data is available only to sessions with **MFA (TOTP)**.
- Deployed on **Vercel** and **Railway**, domains and DNS on **Cloudflare**.

---

## How I work

- **AI-assisted development every day** — Claude Code, skills and agents for prototypes, scripts, debugging and documentation.
  I review and test what comes out; I do not ship what I cannot explain.
- **Problem first.** Every project above started with a concrete, annoying, repeated task.
- **Documented and handed over.** I write step-by-step guides for the people who use what I build.

**Stack:** C# (.NET 8) · Python · JavaScript/TypeScript · n8n · REST APIs and webhooks · Supabase/Postgres · Git · Cloudflare, Vercel, Railway

[LinkedIn](https://www.linkedin.com/in/patryk-sylwerski)
