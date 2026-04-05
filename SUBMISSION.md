# Hackathon Submission — Personal AI Employee

## Tier Declaration: **PLATINUM**

> Personal AI Employee Hackathon 0: Building Autonomous FTEs in 2026

---

## Project Summary

A fully autonomous Digital FTE (Full-Time Equivalent) that manages personal and business affairs 24/7 using a Cloud + Local dual-agent architecture synchronized via a Git-backed Obsidian vault.

**Key Stats:**
- 10 MCP servers integrated
- 20+ agent skills
- 2 orchestrators (cloud + local) with domain ownership
- 38,000+ emails processed and triaged
- 7,000+ tasks completed autonomously
- Full human-in-the-loop approval workflow

---

## Architecture

```
┌─────────────────────────────────────────┐
│           CLOUD VM (24/7)               │
│                                         │
│  cloud_orchestrator.py                  │
│    ✓ Gmail triage (no WhatsApp)         │
│    ✓ Draft email replies (3 options)    │
│    ✓ Draft social posts                 │
│    ✓ Draft Odoo invoices                │
│    ✓ Writes CLOUD_draft_*.md            │
│    ✓ Pushes vault via Git               │
│                                         │
│  cloud_health_monitor.py (Slack alerts) │
│  cloud_sync_worker.py (Git sync 5min)   │
└──────────────┬──────────────────────────┘
               │
         Git Vault Sync
    (markdown only — secrets NEVER sync)
               │
┌──────────────┴──────────────────────────┐
│           LOCAL MACHINE                 │
│                                         │
│  platinum_orchestrator.py               │
│    ✓ Pulls vault from cloud             │
│    ✓ Merges Updates/ → Dashboard.md     │
│    ✓ Runs approval_executor             │
│                                         │
│  local_executor.py                      │
│    ✓ Processes Approved/ items          │
│    ✓ Calls email/social/Odoo MCPs       │
│    ✓ Moves to Done/ + audit log         │
│                                         │
│  whatsapp_watcher.py (LOCAL ONLY)       │
│  workflow_runner.py                     │
└─────────────────────────────────────────┘
```

---

## Platinum Requirements — Completion Status

| Requirement | Status | Evidence |
|-------------|--------|---------|
| Cloud VM 24/7 agent | ✅ Complete | `cloud_orchestrator.py`, `deploy_cloud.sh` |
| Work-zone specialization | ✅ Complete | Cloud=drafts, Local=approvals+sends |
| Claim-by-move conflict prevention | ✅ Complete | `domain_claim_handler.py`, `In_Progress/cloud/`, `In_Progress/local/` |
| Single-writer Dashboard rule | ✅ Complete | Cloud writes to `Updates/`, Local merges |
| Git vault sync | ✅ Complete | `cloud_sync_worker.py`, `vault_sync.py`, GitHub: `Ub207/vault-sync` |
| Secrets never sync | ✅ Complete | `.gitignore` enforces: `.env`, sessions, tokens, banking creds |
| Odoo Community (draft-only on cloud) | ✅ Complete | `odoo_mcp.py` with `ODOO_AGENT_MODE=cloud` → draft-only |
| Platinum demo (minimum passing gate) | ✅ Complete | `platinum_demo.py`, `platinum_orchestrator.py --demo` |
| Health monitoring + Slack alerts | ✅ Complete | `cloud_health_monitor.py` |
| Vault conflict resolution | ✅ Complete | `vault_conflict_resolver.py` |

---

## Gold Requirements — All Met

| Requirement | Status | Evidence |
|-------------|--------|---------|
| Odoo ERP integration | ✅ | `odoo_mcp.py` — 13 tools |
| Facebook + Instagram | ✅ | `facebook_instagram_mcp.py` |
| Twitter/X | ✅ | `twitter_mcp.py` |
| Multiple MCP servers | ✅ | 10 MCP servers total |
| CEO Briefing (Monday 7AM) | ✅ | `ceo_briefing_generator.py`, `Briefings/` |
| Audit logging | ✅ | `audit_logger.py` → `Logs/YYYY-MM-DD.json` |
| Error recovery + retry | ✅ | `error_handler.py` — exponential backoff |
| Ralph Wiggum stop hook | ✅ | `.claude/hooks/stop.py` |
| All AI as Agent Skills | ✅ | `.claude/skills/` — 20+ skills |

---

## Silver Requirements — All Met

| Requirement | Status |
|-------------|--------|
| Gmail watcher | ✅ `gmail_oauth_watcher.py` |
| WhatsApp watcher | ✅ `whatsapp_watcher.py` (Playwright) |
| LinkedIn auto-post | ✅ `linkedin_personal_mcp.py` + `linkedin_company_mcp.py` |
| Plan.md reasoning loop | ✅ `inbox_planner.py` → `Plans/` |
| Email MCP | ✅ `email_mcp.py` |
| HITL approval workflow | ✅ `Pending_Approval/` → `Approved/` → `Done/` |
| Scheduling | ✅ PM2 via `ecosystem.platinum.config.js` |

---

## MCP Servers (10 total)

| Server | Script | Key Tools |
|--------|--------|-----------|
| email | `email_mcp.py` | send, read, search, draft, mark_read |
| linkedin | `linkedin_personal_mcp.py` | post, check_limit |
| linkedin-company | `linkedin_company_mcp.py` | post with image |
| twitter | `twitter_mcp.py` | tweet_post, timeline, search |
| facebook-instagram | `facebook_instagram_mcp.py` | fb_post, ig_post, summary |
| odoo | `odoo_mcp.py` | 13 tools (draft-only on cloud) |
| filesystem | `filesystem_mcp.py` | read, write, move, search vault |
| browser | `browser_mcp.py` | navigate, click, fill_form |
| calendar | `calendar_mcp.py` | list, create, update, delete, find_slots |
| slack | `slack_mcp.py` | send, get, search, upload, set_status |

---

## Platinum Demo — Minimum Passing Gate

**Scenario:** Email arrives while Local is offline.

```
Email arrives (Local offline)
      ↓
Cloud detects → drafts reply → writes Pending_Approval/CLOUD_draft_*.md
      ↓
Cloud pushes vault to GitHub (Ub207/vault-sync)
      ↓
Local comes back online → pulls vault via Git
      ↓
User sees CLOUD_draft_*.md in Obsidian → reviews → moves to Approved/
      ↓
local_executor.py calls email MCP → sends email
      ↓
audit_logger.py logs → file moves to Done/
      ↓
Dashboard.md updated
```

**Run the demo:**
```bash
python platinum_orchestrator.py --demo
# or step-by-step:
python platinum_demo.py --step 1   # simulate incoming email
python platinum_demo.py --step 2   # cloud drafts reply
python platinum_demo.py --step 3   # simulate approval
python platinum_demo.py --step 4   # local executes send
```

---

## Security Architecture

| Layer | Implementation |
|-------|---------------|
| Secrets | `.env` never committed, `.gitignore` enforced |
| Sessions | WhatsApp/LinkedIn sessions excluded from Git sync |
| HITL | All outbound actions require human approval |
| Payments | Secondary approval > PKR 10,000 |
| Audit | Every action logged to `Logs/YYYY-MM-DD.json` |
| Rate limits | Max 2 LinkedIn posts/week, max 10 emails/hour |
| Cloud isolation | Cloud never holds WhatsApp session or banking creds |

---

## GitHub Repository

**Vault:** https://github.com/Ub207/vault-sync
**Code:** `D:/platinum-tier/platinum-tier/` (local)

---

## Setup Instructions

### Local Machine
```bash
# 1. Install dependencies
pip install -r requirements.txt  # or use uv

# 2. Configure credentials
cp .env.example .env
# Edit .env with your API keys

# 3. Initialize vault structure
python setup_platinum_vault.py

# 4. Start all local processes
AGENT_ROLE=local pm2 start ecosystem.platinum.config.js

# 5. Or run directly without PM2
python platinum_orchestrator.py
```

### Cloud VM
```bash
# 1. Run deployment script
chmod +x deploy_cloud.sh
./deploy_cloud.sh --vault-git-url https://github.com/Ub207/vault-sync.git

# 2. Configure cloud .env separately (secrets never in Git)
nano /app/platinum-tier/.env

# 3. Start cloud processes
AGENT_ROLE=cloud pm2 start /app/platinum-tier/ecosystem.platinum.config.js
pm2 save
pm2 startup
```

---

*Built for: Personal AI Employee Hackathon 0 — Platinum Tier*
*Stack: Claude Code + Obsidian + Python + 10 MCP servers*
*Submitted: 2026-04-05*
