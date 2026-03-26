# Dashboard
*Auto-updated by Claude Code -- last refresh: 2026-03-25 19:30 IST*
*Local Agent is sole writer of this file. Cloud Agent writes to Updates/ only.*

---

## System Health
| MCP Server | Status |
|------------|--------|
| Slack | Working |
| Gmail | Working |
| Calendar | Working |
| Filesystem | Working |
| Browser | Working |
| Facebook | Bug fixed, restart needed |
| Instagram | No USER_ID configured |
| Twitter | API keys expired |
| Odoo | Admin password incorrect |

---

## Vault Status
| Queue | Count | Notes |
|-------|-------|-------|
| Needs_Action/cloud | 0 | Cleared - 509 stale emails archived |
| Needs_Action/local | 0 | Cleared - 26 stale WA messages archived |
| Pending_Approval | 1 | 1 LinkedIn post awaiting review |
| Approved (ready) | 2 | 2 LinkedIn posts ready to post |
| In_Progress | 0 | No active claims |
| Done (archive) | 7,123 | Includes today's cleanup |
| LinkedIn_Drafts | 25 | Drafts pool |
| Plans | 23 | Cloud plans |

---

## Pending Approvals
| File | Type | Action |
|------|------|--------|
| LI_PERSONAL_20260325_0840_one_founder_saved_12_hours.md | LinkedIn Personal | Review and approve |

---

## Approved (Ready to Execute)
| File | Type | Action |
|------|------|--------|
| LI_PERSONAL_20260323_1845_ai_employee_499_emails.md | LinkedIn Personal | Post when ready |
| LI_PERSONAL_20260325_0840_one_founder_saved_12_hours.md | LinkedIn Personal | Post when ready |

---

## LinkedIn Posts This Week (W13)
| Post | Status | Characters |
|------|--------|------------|
| 499 emails case study | Approved | 952 |
| 12 hours saved founder | Approved | 987 |
| *Rate limit: max 2/week personal* | | |

---

## Cleanup Log (2026-03-25)
- Archived 509 stale cloud emails (Mar 9-22) to Done/
- Archived 26 stale WhatsApp messages (Mar 6) to Done/
- Archived 3 demo drafts from Pending_Approval to Done/
- Archived 2 stale Needs_Action root items to Done/
- Archived 74 stale Updates/ signals to Done/
- Trimmed Approval_Log.md: 229,366 to 508 lines (old archived)
- Fixed Facebook/Instagram MCP .env loading bug
- Fixed Gmail OAuth scopes (added readonly + compose + calendar)

---

## Business Context
- **Target:** AI automation consulting for solo founders
- **Currency:** PKR | **Hours:** 10am-7pm IST
- **WA response target:** < 2 hours during business hours
- **LinkedIn limit:** Max 2 posts/week per profile

---

*Run `python platinum_orchestrator.py` to refresh automatically.*
