# PRD — Project Requirements Document

**Location:** `PRD.md` at the project root (next to `CLAUDE.md` — not inside `.claude/`)

**Purpose:** Comprehensive project specification. Claude reads this for context. Humans read this to understand scope.

---

## Project Overview

**AI Database Maintenance Co. (working name)**

A Texas-based service business that provides ongoing maintenance for the vector and traditional databases underlying AI applications.

It's for small-to-mid-sized businesses that have built a working AI product (RAG pipeline, AI search, chatbot, internal AI tool) but lack in-house database/DevOps staff to keep it healthy — leading to degraded search relevance, stale embeddings, missed backups, slow queries, and unplanned downtime if left unmanaged.

---

## Problem Statement

AI/ML products rely on vector databases (Pinecone, Weaviate, Milvus, pgvector) and the relational/NoSQL databases that feed them. Many small-to-mid-sized businesses build these systems but don't have the expertise or headcount to maintain them over time. This business provides expert, ongoing maintenance so clients can focus on their product instead of database upkeep.

---

## Target User / Customer

- **Who are they?** Small-to-mid-sized businesses in Texas running AI-powered products, without dedicated database/DevOps staff. Likely buyers are technical founders, engineering leads, or ops managers.
- **What do they need?** Someone reliably watching, backing up, and tuning their AI-related databases without hiring a full-time employee for it.
- **Current workflow:** Ad hoc — whoever built the system checks on it when they remember to, or not at all, until something breaks.

*(Assumption: this PRD assumes a B2B service/consulting business, not a software product. Please confirm.)*

---

## Core Features (3-5)

1. **Health checks & uptime monitoring** — Scheduled checks on vector/AI databases to catch problems before clients do.
2. **Backup & recovery** — Setup and periodic verification of backups for client databases.
3. **Performance tuning** — Index and embedding maintenance to keep query performance and search relevance from degrading.
4. **Incident response** — Manual, on-call-style response to database-related outages.
5. **Lead-gen website** — Marketing site describing services and pricing tiers, with a contact/booking form.

---

## Out of Scope

Features we're NOT building (yet):

- A full client-facing dashboard/reporting web app (candidate for v1.5 or v2)
- 24/7 automated monitoring/alerting infrastructure (v1 is manual/scheduled checks)
- Support for AI database platforms beyond the most common vector DB and general-purpose DB systems
- In-house AI model training, fine-tuning, or application development (this is infrastructure maintenance, not AI product development)
- Non-Texas clients (v1 focuses on establishing a regional foothold, even if delivery is remote)

---

## Success Metrics

- [ ] First paying client onboarded and retained for at least 3 consecutive months
- [ ] A defined, repeatable service package (scope + pricing) quotable to a new prospect in under a day
- [ ] Zero data-loss incidents caused by maintenance work performed
- [ ] Documentation/process clear enough that a contractor could be onboarded to help deliver the service without Mike explaining everything from scratch

---

## Tech Stack

Not yet decided — no code has been written for this project. A marketing website and/or client tooling may be needed later; revisit this section once that work starts.

- **Frontend**: TBD
- **Backend**: TBD
- **Database**: TBD
- **Authentication**: TBD
- **Hosting**: TBD
- **Package Manager**: TBD
- **Language/Runtime**: TBD (Mike's default stack is JavaScript/Node with ES modules — see global CLAUDE.md)

---

## Secure Coding Principles (MANDATORY)

Not yet applicable — no code exists yet. Once a website or client-tooling app is built (handling client database credentials, connection strings, or contact-form data), the standard rules apply and are non-negotiable:

- Never hardcode secrets, API keys, or credentials — use environment variables
- `.env` must be in `.gitignore` before the first commit
- Validate all inputs at system boundaries (e.g., contact/booking form)
- Never log PII (emails, names, tokens)
- Use parameterized queries — never string-concatenate user input into queries
- Treat all client database credentials/connection strings as secrets

---

## Key File Locations

N/A — no code yet.

---

## Build & Development Commands

N/A — no code yet.

---

## Critical Setup Steps

N/A — no code yet.

---

## Database Schema (Quick Reference)

N/A — no application database yet. (Client *maintenance targets* — e.g. Pinecone/Weaviate/pgvector instances — are the subject of the business, not something this project's own codebase owns.)

---

## Deployment

N/A — no code yet. Once a marketing site exists, revisit this section.

---

## Common Gotchas

- **Market risk** — Unclear how many Texas businesses have AI databases mature enough to need ongoing maintenance (vs. still building) → validate demand before investing heavily.
- **Trust/credibility risk** — As a new provider, gaining enough trust for businesses to hand over access to production data infrastructure may be slow → consider case studies, references, or a low-risk trial offering.
- **Scope creep risk** — "Maintenance" could easily expand into full DevOps/consulting engagements that dilute the focused service offering → keep service packages tightly scoped.
- **Delivery risk** — As a single-person (or small) operation, incident response commitments (e.g., uptime SLAs) may be hard to honor without backup coverage → don't over-promise SLAs early on.
- **Security risk** — Handling client database credentials/access requires careful, documented security practices from day one.

---

## Done When (Launch Checklist)

Project is complete (v1 launch) when ALL of these are true:

- [ ] Service packages (scope + pricing) defined and documented
- [ ] Marketing/lead-gen website live with contact/booking form
- [ ] Client onboarding process defined (even if manual/spreadsheet-based)
- [ ] Security practices for handling client credentials documented
- [ ] First paying client onboarded

---

## Team & Contacts

- **Product Lead**: Mike — mhearty1@gmail.com
- **Tech Lead**: Mike — mhearty1@gmail.com
- **Design Lead**: TBD
- **Slack Channel**: N/A

---

## Useful Links

- [Project Documentation](link)
- [Design System / Figma](link)
- [Issue Tracker](link)
- [Architecture Diagram](link)
- [API Documentation](link)
- [Deployment Dashboard](link)

---

**Last Updated**: 2026-08-12
**Maintained By**: Mike
**Status**: Planning

---

**Quick Reference**: Use this PRD when:
- You're unsure about what the project should do
- You need to understand scope boundaries
- You're evaluating whether something is in-scope or out-of-scope
- You want to know the success criteria

---

## Open Questions

*(Assumptions made to fill gaps in the original one-line idea — please confirm or correct any that are wrong.)*

- Assumed this is a **service business** (consulting/retainer), not a software product company
- Assumed target customers are **businesses already running AI systems** who need maintenance, not businesses looking to *build* AI systems from scratch
- Assumed "AI databases" means **vector databases and the traditional databases supporting AI/RAG pipelines**
- Assumed a **subscription/retainer pricing model** rather than one-off project pricing
- Assumed delivery is **remote-first**, with "Texas" referring to the target market/registration location rather than requiring on-site visits
- No specific pricing, competitor, or timeline information was provided — these will need to be defined before the site/offering goes live
- Whether a client-facing app/dashboard is wanted at all (even for v2) is unconfirmed — v1 above assumes it's not needed yet
