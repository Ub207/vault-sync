# Bank Transactions Log
*Used by `audit_logic.py` for subscription audit and CEO briefing.*
*Last updated: 2026-03-16*

---

## How to Use

1. Add rows to the table below whenever you make/receive a payment.
2. Run `python audit_logic.py` to get a subscription audit report.
3. The CEO briefing auto-reads this file every Monday.

**Column guide:**
- **Type**: `debit` = money out, `credit` = money in
- **Amount**: PKR amount (no commas, just number)
- **Category**: auto-detected by audit_logic.py — leave blank if unsure

---

## March 2026

| Date       | Description                    | Amount (PKR) | Type   | Category        | Notes                  |
|------------|--------------------------------|--------------|--------|-----------------|------------------------|
| 2026-03-01 | Claude Pro Subscription        | 5500         | debit  | AI Tools        | Monthly AI tool        |
| 2026-03-01 | Internet Bill                  | 3500         | debit  | Utilities       | Home office internet   |
| 2026-03-05 | Client Payment — Project Alpha | 75000        | credit | Revenue         | Invoice #001 cleared   |
| 2026-03-10 | Canva Pro                      | 2800         | debit  | Design          | Monthly design tool    |
| 2026-03-12 | GitHub Copilot                 | 2200         | debit  | Dev Tools       | Monthly subscription   |
| 2026-03-15 | Zoom Pro                       | 2100         | debit  | Communication   | Monthly video calls    |
| —          | —                              | —            | —      | —               | —                      |

**MTD Debit:** PKR 16,100
**MTD Credit:** PKR 75,000
**Net:** PKR +58,900

---

## February 2026

| Date       | Description                    | Amount (PKR) | Type   | Category        | Notes                  |
|------------|--------------------------------|--------------|--------|-----------------|------------------------|
| 2026-02-01 | Claude Pro Subscription        | 5500         | debit  | AI Tools        | Monthly                |
| 2026-02-01 | Internet Bill                  | 3500         | debit  | Utilities       |                        |
| 2026-02-10 | Canva Pro                      | 2800         | debit  | Design          | Monthly                |
| 2026-02-15 | Zoom Pro                       | 2100         | debit  | Communication   | Monthly                |
| 2026-02-20 | Client Payment — Retainer      | 50000        | credit | Revenue         | Monthly retainer       |
| 2026-02-28 | GitHub Copilot                 | 2200         | debit  | Dev Tools       | Monthly                |
| —          | —                              | —            | —      | —               | —                      |

**MTD Debit:** PKR 16,100
**MTD Credit:** PKR 50,000
**Net:** PKR +33,900

---

## Subscription Audit Rules

Per `Business_Goals.md`:
- Flag if no usage in **30 days**
- Flag if cost increased **>20%**
- Flag if **duplicate functionality** with another tool

Run audit: `python audit_logic.py --file silver_tier/Accounting/Bank_Transactions.md`

---

## Recurring Subscriptions (Monthly)

| Service         | Cost (PKR) | Billing Date | Status | Last Reviewed  |
|-----------------|------------|--------------|--------|----------------|
| Claude Pro      | ~5,500     | 1st          | Active | 2026-03-16     |
| Internet        | 3,500      | 1st          | Active | 2026-03-16     |
| Canva Pro       | 2,800      | 10th         | Active | 2026-03-16     |
| GitHub Copilot  | 2,200      | 28th         | Active | 2026-03-16     |
| Zoom Pro        | 2,100      | 15th         | Active | 2026-03-16     |

**Total Monthly Subscriptions:** ~PKR 16,100

---
*Auto-audited by `audit_logic.py` — imported by `ceo_briefing_generator.py`*
