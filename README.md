# Zaper AI team: an AI leadership team for a construction-tech company

> The source code and the client's materials are private. This page explains what I built and what it connects to.

[Zaper AI](https://zaper.ai) makes a voice-first AI project manager for construction, MEP, HVAC, facility-management and fit-out teams. I built Zaper an internal **AI leadership team**: an orchestrator and specialist agents that the Zaper team talks to through one chat, plus an HQ dashboard where they can see and steer all of it.

## The team

| Role | Job |
|---|---|
| Orchestrator | Reads every chat message, voice note, photo and file, writes a work card, routes it to the right leader, asks for approval before risky actions, and replies |
| COO | Customers and projects: customer tracker and project manager |
| CMO | Market research, content, channels and social, and AI visibility (getting the company named when people ask AI tools) |
| CSO | Account qualification, finding verified business contacts, and drafting first pitches. Pitches are never sent without approval |
| Company brain | Learns the business from documents and conversations the team chooses, and answers questions with the source |

## How a request flows

1. Someone posts in the chat: text, a voice note, a photo or a file.
2. The orchestrator turns it into text. Voice is transcribed, photos are described, and text is extracted from files.
3. It looks up the customer, project or deal in the database and shared memory.
4. It writes a work card and routes it to the COO, CMO or CSO, who passes it to a specialist.
5. Anything risky, like emailing a customer or changing a promised date, waits in **Approvals**.
6. The answer goes back to the chat, and the result is saved to memory.

## HQ dashboard

- Run All, Run selected and Pause for the agents.
- Every run has a hard ceiling, and only one cycle runs at a time.
- Approvals, saved outputs and PDF reports, chat, and the docs and plan in one place.
- Role-based access: each team member sees their own conversations, and only the owner sees everyone's.

## Built with

| Area | Tools |
|---|---|
| Agents | Claude (Anthropic) through local workers; OpenAI Codex as a fallback runner; LangGraph for multi-step workflows |
| Data and memory | Supabase (Postgres, auth, storage, row-level security), with migrations for every feature |
| Dashboard | Next.js and React, deployed on Cloudflare (OpenNext) |
| Research | Web and LinkedIn research connectors, and PDF reports |
| Email | Resend and Gmail |
| Ops | A Cloudflare Worker that keeps the database awake; tests for each agent and for the database |

---
Built by Rasthm with Claude Code. © 2026 Rasthm. Zaper and the Zaper name belong to Zaper AI.
