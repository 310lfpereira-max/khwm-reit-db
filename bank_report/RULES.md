# Bank Report — Calculation Rules

Working rule set for the lender/bank reporting package (property-level income
statement). Rules are added incrementally; each rule is numbered so it can be
referenced, amended, or superseded without renumbering the rest.

Status: **draft — rules 1–5 captured, more to come.**

---

## 1. Actual column — trailing 3 months (T3)

- The "Actual" column is built from **3 months of actual operating data** (T3).
- **Exception — short hold period:** if the property has been held for **less
  than 3 months**, use **budget** numbers instead of actuals for the periods not
  owned. Budget substitutes for the missing months so the column always
  represents a full 3-month period.

## 2. Management fee — formula, not actual

- Do **not** use the actual management fee expense recorded in the ledger.
- Management fee = **Total Income × 5.0%**.
- This applies in both the T3 actual column and the annualized 12-month column
  (in the annualized column the fee is 5% of annualized total income, so it
  scales consistently).

## 3. Repairs above $2,500 — capital, excluded

- Any repair **greater than $2,500** is treated as a **capital expense**.
- Capital items are **ignored** — excluded from operating expenses and therefore
  excluded from NOI.
- Repairs of $2,500 or less remain operating expenses (R&M).

## 4. 12-month (annualized) income statement — T3 × 4

- The 12-month income statement is the **T3 figures multiplied by 4**.
- This applies to all line items **except** those listed in Rule 5 (rent and
  parking), which are taken from the rent roll rather than annualized from
  actuals.

## 5. Rent and parking — from the rent roll, not annualized

Rent and parking are **not** derived by multiplying T3 by 4. Instead:

- **Rent** = **rent in place and contracted rent** per the rent roll.
  - If the rent roll shows a **future contract** for a unit, use the **future
    contracted rent** for that unit.
  - If there is no future contract, use the **existing (in-place) rent**.
  - Annualize the resulting monthly rent × 12.
- **Parking** = same treatment: future contracted parking rent where one exists,
  otherwise the in-place parking rent, annualized × 12.

---

## Line-item treatment summary

| Line item | T3 / Actual column | 12-month column |
|---|---|---|
| Rent | T3 actual (or budget if held < 3 months) | Rent roll: contracted rent if a future contract exists, else in-place rent, × 12 |
| Parking | T3 actual (or budget if held < 3 months) | Rent roll: contracted parking if a future contract exists, else in-place, × 12 |
| Other income | T3 actual | T3 × 4 |
| Management fee | 5% of total income | 5% of annualized total income |
| Repairs & maintenance | T3 actual, excluding any single repair > $2,500 | T3 (net of capital items) × 4 |
| All other operating expenses | T3 actual | T3 × 4 |
| Capital items (repairs > $2,500) | Excluded | Excluded |

---

## Open questions (to confirm as rules are added)

These are flagged, not assumed — they affect the numbers and should be settled
before the report is finalized:

1. **Repair threshold basis** — is the $2,500 test applied per **invoice**, per
   **work order**, or per **line item**? Current assumption: per invoice/charge.
2. **"Total income" for the management fee** — gross potential income, or actual
   total income collected (net of vacancy/concessions)? Current assumption:
   total income as reported on the statement (actual collected).
3. **Which 3 months** — trailing 3 months from the most recent closed month, or
   a fixed quarter? Current assumption: trailing 3 closed months.
4. **Rent roll as-of date** — which date drives "in place," and how far forward
   does a "future contract" count (any signed lease, or only those commencing
   within the next 12 months)?
5. **Vacancy / loss-to-lease** — is the rent-roll-based annual rent shown gross
   of vacancy, with a separate vacancy line, or net?

---

## Change log

- Initial capture: rules 1–5.
