---
type: whatsapp_reply
original_file: WA_TEST_1.md
from: Rahul Sharma
priority: high
status: awaiting_approval
created: 2026-03-04 00:00:01
plan: PLAN_wa_rahul_sharma_20260304_000001.md
flags: URGENT, INVOICE, FINANCIAL_FLAG, REPLY_NEEDED
financial_flag: true
---

## Original Message

**From:** Rahul Sharma
**Received:** 2026-03-03 10:15:00
**Raw text:** "bhai urgent hai — invoice still pending from last month, please check asap"

---

## Classification Analysis

| Flag | Detected | Trigger Words |
|------|----------|---------------|
| URGENT | YES | "urgent", "asap" |
| INVOICE | YES | "invoice" |
| FINANCIAL_FLAG | YES | Invoice amount unknown — flagged by default |
| REPLY_NEEDED | YES | Active request for action |

---

> ⚠️  **FINANCIAL FLAG ACTIVE**
> This message references an outstanding invoice. Amount is not specified in the message.
> Per Company Handbook: Confirm amount is < PKR 10,000 before sending a payment-related reply.
> **If the invoice amount is ≥ PKR 10,000 — secondary approval required.**

---

## Reply Options

**Option A — Professional:**
> Hi Rahul, thank you for following up. I've noted the pending invoice from last month and will look into it right away. I'll get back to you with an update by [TODAY 5PM].

**Option B — Friendly (Recommended for repeat client):**
> Bhai, got your message! Sorry for the delay on the invoice — I'm on it now. Will sort this out and send you an update by [TODAY 5PM].

**Option C — Defer (if you need time to verify):**
> Hi Rahul, received your message. I'm currently in the middle of something but the invoice is on my radar. Will follow up with you by [TIME] today — thanks for your patience.

**Option D — Escalation / Info Request (Recommended if amount unknown):**
> Bhai, noted! Can you send me the invoice number so I can pull it up quickly? Will sort it out today once I have the details.

---

💡 **Recommendation: Option D** — Ask for invoice number first. This buys time to verify the amount, avoids committing to a resolution timeline blind, and keeps the tone friendly and action-oriented. Replace with B once you have the invoice details.

---

## Approval

- [ ] Approved reply:  D
- [ ] Financial flag confirmed: amount is < PKR 10,000 (check before approving B or C)
- [ ] Placeholders replaced: [TODAY 5PM] / [TIME] filled in

**Custom reply (optional — paste your text below):**
>

---

## Next Steps After Approval
1. Run `/approval-checker send WA_REPLY_WA_TEST_1.md`
2. This will trigger `/whatsapp-sender-mcp` to open WhatsApp Web and pre-fill the reply
3. Review the pre-filled text in the browser and press Enter to send
4. The file will be moved to `/Done` automatically
