<p align="center">
  <img src="https://img.shields.io/badge/Status-Production-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Tier-Platinum-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Uptime-24%2F7-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Python-3.9+-yellow?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Claude-Opus_4-orange?style=for-the-badge&logo=anthropic&logoColor=white" />
</p>

<h1 align="center">Personal AI Employee - Platinum Tier</h1>

<p align="center">
  <strong>A Digital Full-Time Equivalent (FTE) that proactively manages personal and business affairs 24/7.</strong>
</p>

<p align="center">
  <em>Cloud VM runs autonomously. Local machine approves and executes. Both sync via this vault.</em>
</p>

---

## What Is This?

This is the **operational vault** for an AI-powered digital employee — a system that replaces 10+ hours/week of manual admin work for solo founders and small agencies.

Unlike a chatbot that waits for commands, this AI Employee:
- **Monitors** emails, messages, and social media autonomously
- **Drafts** replies, invoices, and social posts
- **Routes** sensitive actions for human approval
- **Executes** approved actions via API integrations
- **Reports** with weekly CEO briefings

---

## Architecture

```
                    +------------------------+
                    |    Oracle Cloud VM     |
                    |    (Always-On 24/7)    |
                    |                        |
                    |  cloud_orchestrator.py |
                    |  - Email triage        |
                    |  - Social media drafts |
                    |  - Invoice drafts      |
                    |  - Health monitoring   |
                    +-----------+------------+
                                |
                          Git Vault Sync
                          (this repo)
                                |
                    +-----------+------------+
                    |    Local Machine       |
                    |    (User's Desktop)    |
                    |                        |
                    | platinum_orchestrator  |
                    |  - Gmail watcher       |
                    |  - WhatsApp watcher    |
                    |  - Approval executor   |
                    |  - Dashboard updates   |
                    +-----------+------------+
                                |
                         Obsidian GUI
                     (Human reviews here)
```

---

## Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Brain** | Claude Code (Opus 4) | Decision-making, drafting, planning |
| **Memory / GUI** | Obsidian Vault | File-based state, human review interface |
| **Senses** | Python Watchers | Gmail, WhatsApp, social media monitoring |
| **Hands** | 10 MCP Servers | Email, LinkedIn, Twitter, Facebook, Odoo, Calendar, Slack |
| **Cloud** | Oracle Cloud VM | 24/7 autonomous operation |
| **Sync** | Git (this repo) | Bi-directional vault synchronization |
| **ERP** | Odoo 17 (Docker) | Invoicing, accounting, CRM |

---

## Capabilities

### Communication Automation
| Channel | Monitor | Draft | Send | Status |
|---------|---------|-------|------|--------|
| Gmail | Automated | AI-drafted | Human approves | **Live** |
| WhatsApp | Automated | AI-drafted | Human approves | **Live** |
| Slack | Automated | AI-drafted | Human approves | **Live** |

### Social Media Management
| Platform | Draft | Schedule | Post | Status |
|----------|-------|----------|------|--------|
| LinkedIn (Personal) | AI-drafted | Planned | Human approves | **Live** |
| LinkedIn (Company) | AI-drafted | Planned | Human approves | **Live** |
| Twitter/X | AI-drafted | Planned | Human approves | **Live** |
| Facebook | AI-drafted | Planned | Human approves | **Live** |
| Instagram | AI-drafted | Planned | Human approves | **Live** |

### Business Operations
| Function | Capability | Status |
|----------|-----------|--------|
| Invoicing | Auto-draft invoices in Odoo | **Live** |
| Payment Tracking | Overdue follow-ups | **Live** |
| CEO Briefing | Weekly auto-generated report | **Live** |
| Calendar | Event management & free slots | **Live** |
| Accounting | Revenue summaries, bank reconciliation | **Live** |

---

## Vault Structure

```
vault/
├── Dashboard.md                 # Real-time system status
├── Company_Handbook.md          # Rules of engagement
├── Business_Goals.md            # Quarterly targets & KPIs
│
├── Needs_Action/                # Incoming items to process
│   ├── cloud/                   # Cloud agent's queue
│   └── local/                   # Local agent's queue
│
├── Plans/                       # Action plans (created before execution)
├── Pending_Approval/            # Awaiting human decision
├── Approved/                    # Green-lit for execution
├── Rejected/                    # Declined with reason
├── Done/                        # Completed & archived
├── In_Progress/                 # Currently being worked on
│
├── Updates/                     # Cloud -> Local signals
├── Signals/                     # Health & status heartbeats
├── Briefings/                   # Weekly CEO briefings
├── Invoices/                    # Generated invoices
├── Accounting/                  # Financial records
├── LinkedIn_Drafts/             # Social media content
└── Logs/                        # JSON audit trail
```

---

## Safety & Governance

> **Human-in-the-loop by design.** No message is sent, no payment is made, and no post goes live without explicit human approval.

### Golden Rules
1. **Plan First** — Every action requires a plan before execution
2. **Human Approves** — Sensitive actions always need human sign-off
3. **Draft Only** — All accounting entries created as DRAFT
4. **Never Auto-Send** — Human always clicks the final Send/Post
5. **Full Audit Trail** — Every action logged with timestamp and context
6. **Rate Limited** — Max 2 LinkedIn posts/week, max 10 emails/hour

### Approval Matrix
| Action | Approval Required |
|--------|------------------|
| Send email/WhatsApp | Always |
| Social media post | Always |
| Create invoice | Always |
| Payment > PKR 10,000 | Secondary approval |
| New contact outreach | Always |

---

## MCP Integrations (10 Servers)

```
  linkedin ──── Personal & Company posts
  email ─────── Gmail (OAuth2) send/read/draft
  twitter ───── Tweet, timeline, search
  facebook ──── FB + Instagram posts
  odoo ──────── 13 ERP tools (invoices, payments, partners)
  filesystem ── Vault read/write/search
  browser ───── Web automation (navigate, click, fill)
  calendar ──── Google Calendar CRUD
  slack ──────── Messages, channels, status
```

---

## Performance Metrics

| Metric | Target | Current |
|--------|--------|---------|
| Email response time | < 2 hours (business hours) | Automated draft in < 5 min |
| Weekly time saved | 10+ hours | ~12 hours |
| Social posts/week | 4 (2 personal + 2 company) | On schedule |
| System uptime | 99%+ | Cloud VM 24/7 |
| Approval turnaround | Same day | Via Obsidian GUI |

---

## Workflow

```
Event detected (email / message / scheduled task)
        |
        v
Watcher creates item in Needs_Action/
        |
        v
AI creates PLAN_*.md in Plans/
        |
        v
AI drafts response -> Pending_Approval/
        |
        v
Human reviews in Obsidian
        |
   +---------+---------+
   |                   |
   v                   v
Approved/           Rejected/
   |                (with reason)
   v
Executor sends via MCP
   |
   v
Audit log + Done/
   |
   v
Dashboard.md updated
```

---

## Getting Started

### Prerequisites
- Python 3.9+
- Obsidian (for vault GUI)
- Docker (for Odoo ERP)
- Oracle Cloud account (for 24/7 VM)

### Quick Start
```bash
# Clone this vault
git clone https://github.com/Ub207/vault-sync.git

# The vault is the shared state between cloud and local agents.
# See the main project repo for orchestrator scripts and setup.
```

---

## Security

- All secrets stored in `.env` (never committed)
- WhatsApp/LinkedIn sessions excluded from sync
- OAuth2 tokens excluded from sync
- Banking credentials excluded from sync
- Git hooks enforce secret scanning

---

## License

Private repository. All rights reserved.

---

<p align="center">
  <strong>Built by <a href="https://github.com/Ub207">Ubaid ur Rahman</a></strong><br/>
  AI Automation Consulting for Solo Founders & Small Agencies
</p>
