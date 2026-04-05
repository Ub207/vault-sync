---
type: approval_request
channel: odoo
source: EMAIL_DEMO_20260322_114655.md
created: 2026-03-22T11:46:57.484722+00:00
status: approved
agent_origin: cloud
needs_secondary_approval: true
partner: TechStartup Pvt Ltd
amount: 75000
currency: PKR
demo: true
---

## Cloud-Drafted Odoo Invoice (DRAFT ONLY)

> PKR 75,000 >= PKR 10,000 threshold — SECONDARY APPROVAL REQUIRED

### Invoice Details
| Field | Value |
|-------|-------|
| Partner | TechStartup Pvt Ltd |
| Amount | PKR 75,000 |
| Description | AI Automation Consulting — March 2026 |
| Due in | 30 days |
| Currency | PKR |

## Approval Checklist
- [ ] Verify partner exists in Odoo: `TechStartup Pvt Ltd`
- [ ] Confirm amount: PKR 75,000
- [ ] **Secondary approval required** (PKR >= 10,000)
- [ ] Move to `/Approved` — Local calls odoo_mcp.create_invoice (DRAFT)

> Local creates a DRAFT invoice in Odoo. You still click Confirm inside Odoo.
