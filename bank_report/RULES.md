# Bank Report — Calculation Rules

Working rule set for the lender/bank reporting package (property-level income
statement). Rules are added incrementally; each rule is numbered so it can be
referenced, amended, or superseded without renumbering the rest.

Status: **draft — rules 1–10 captured, more to come.**

---

## 1. Actual column — trailing 3 months (T3)

- The "Actual" column is built from **3 months of actual operating data** (T3).
- **Exception — short hold period:** if the property has been held for **less
  than 3 months**, use **budget** numbers instead of actuals for the periods not
  owned. Budget substitutes for the missing months so the column always
  represents a full 3-month period.

## 2. Annualization — build the 3-month column first, then × 4

The two columns are derived in sequence, not independently:

1. **Build the 3-month column** by applying every T3 rule — exclude capital
   repairs (Rule 4), one-time costs (Rule 8), and bad debt (Rule 9) at this
   stage, so the quarter is already clean.
2. **Multiply the resulting 3-month figures by four** to get the 12-month
   column.

Two categories override the ×4 default:

- **Lines with their own 12-month treatment:** rent and parking (Rule 5,
  from the rent roll), utilities (Rule 6, per bedroom), G&A (Rule 7, at
  budget), and the management fee (Rule 3, recomputed — see below).
- **Additional 12-month-only exclusions (Rule 10):** anything that survives
  the quarter but should still come out of the annualized bucket.

**The management fee is recomputed, never annualized.** Because rent and
parking differ between the two columns, 12-month total income is not simply the
quarter × 4 — so take 5% of *each* column's own total income rather than
multiplying the 3-month fee by four.

## 3. Management fee — 5% of total income

- Do **not** use the actual management fee expense recorded in the ledger.
- Management fee = **Total income × 5.0%**.
- The base is the **total income line** — rent (per the rent roll), parking,
  and other income. Every income dollar on the statement is in the fee base;
  nothing is carved out.
- Applies in both columns: 5% of quarterly total income in the T3 column, 5% of
  annualized total income in the 12-month column, so the fee scales
  consistently with income.

## 4. Repairs above $2,500 — capital, excluded

- Any repair **greater than $2,500** is treated as a **capital expense**.
- Capital items are **ignored** — excluded from operating expenses and therefore
  excluded from NOI.
- Repairs of $2,500 or less remain operating expenses (R&M).

## 5. Rent and parking — from the rent roll, not annualized

Rent and parking are **not** derived by multiplying the quarter by four.
Instead:

- **Rent** = **rent in place and contracted rent** per the rent roll.
  - If the rent roll shows a **future contract** for a unit, use the **future
    contracted rent** for that unit.
  - If there is no future contract, use the **existing (in-place) rent**.
  - Annualize the resulting monthly rent × 12.
- **Parking** = same treatment: future contracted parking rent where one exists,
  otherwise the in-place parking rent, annualized × 12.

## 6. Utilities — $261 per bedroom per year (net landlord cost)

- Utilities are **not** taken from actuals and **not** annualized from the
  quarter. They are underwritten at a fixed rate.
- **Net landlord utility cost = $261 per bedroom per year.**
- Basis: on properties where tenant utility reimbursements are billed back,
  reimbursements recover approximately **45% of total utility expense**; the
  $261/bedroom figure is the residual landlord share net of that recovery.
- Because the figure is already **net**, tenant utility reimbursement income is
  **not** shown separately as income — do not both credit reimbursements and
  apply the net rate (that would double count the recovery).

## 7. General & administrative — held at budget

- G&A is carried at the **budgeted amount**, not at annualized actuals.
- Rationale: a single quarter of actual G&A may not be representative of a
  stabilized run rate.

## 8. One-time costs — excluded

- Non-recurring items are **excluded** from the operating statement, as they do
  not represent a stabilized run rate. These include:
  - unit turnover costs
  - snow true-ups
  - legal
  - marketing
  - bank fees
- Excluding them before annualization matters: a one-time charge left in the
  quarter would otherwise be multiplied by four.

## 9. Bad debt — excluded

- Bad debt / credit loss is **excluded** as a separate expense line.
- Rationale: credit loss is already captured within the vacancy inherent in the
  rent roll, so carrying both would double count it.
- Note: there is **no separate vacancy allowance line**. Rent is taken from the
  rent roll as in-place and contracted rent (Rule 5), so a vacant unit with no
  contract contributes zero — vacancy is captured by the rent roll itself, not
  by a deduction.

## 10. Additional 12-month-only exclusions

- Beyond the exclusions already applied in the quarter (Rules 4, 8, 9), the
  12-month bucket may carry **further exclusions of its own** — items that
  legitimately belong in the trailing quarter but should not be carried into
  the annualized run rate.
- Any such item is removed **after** the ×4 step, from the 12-month column
  only; the 3-month actual column keeps it.

**To be populated.** No 12-month-only exclusions are defined yet — list them
here as they are identified, and the ×4 result stands unadjusted until then.

---

## Line-item treatment summary

| Line item | T3 / Actual column | 12-month column |
|---|---|---|
| Rent | T3 actual (budget if held < 3 months) | Rent roll: contracted rent if a future contract exists, else in-place rent, × 12 |
| Parking | T3 actual (budget if held < 3 months) | Rent roll: contracted parking if a future contract exists, else in-place, × 12 |
| Other income | T3 actual | T3 × 4 |
| Utility reimbursement income | Not shown separately — netted into Rule 6 | Not shown separately |
| **Total income** | Rent + parking + other income; basis for the fee (Rule 3) | Same |
| Management fee | 5% of total income | 5% of annualized total income |
| Utilities | $261 / bedroom / year ÷ 4 | $261 × bedrooms |
| General & administrative | Budget | Budget |
| Repairs & maintenance | T3 actual, excluding any single repair > $2,500 | T3 (net of capital items) × 4 |
| All other operating expenses | T3 actual | T3 × 4 |
| Capital items (repairs > $2,500) | Excluded | Excluded |
| One-time costs (turnover, snow true-up, legal, marketing, bank fees) | Excluded | Excluded |
| Bad debt | Excluded | Excluded |

**Order of operations:**

1. Strip exclusions from the quarter — capital repairs, one-time costs, bad
   debt (Rules 4, 8, 9). This produces the **3-month column**.
2. Multiply that clean quarter **× 4**.
3. Overlay the lines that have their own 12-month treatment — rent and parking
   from the rent roll, utilities at $261/bedroom, G&A at budget.
4. Remove any **12-month-only exclusions** (Rule 10).
5. Compute the **management fee last**, at 5% of the resulting total income,
   separately in each column.

---

## Open questions (to confirm as rules are added)

Flagged, not assumed — each of these moves the numbers:

1. **Repair threshold basis** — is the $2,500 test applied per **invoice**, per
   **work order**, or per **line item**? Current assumption: per invoice/charge.
2. **Which 3 months** — trailing 3 closed months, or a fixed calendar quarter?
   Current assumption: trailing 3 closed months.
3. **Rent roll as-of date** — which date drives "in place," and how far forward
   does a "future contract" count (any signed lease, or only those commencing
   within the next 12 months)?
4. **Bedroom count source** — rent roll unit mix, and is it total bedrooms in
   the property regardless of occupancy?
5. **Utilities scope** — does $261/bedroom replace *all* utility accounts
   (water/sewer, gas, electric, trash), or only those the landlord pays
   directly, with any master-metered account handled separately?

---

## Change log

- Initial capture: rules 1–5.
- Added rules 6–9 (utilities per bedroom, G&A at budget, one-time cost
  exclusion, bad debt exclusion); management fee base refined from total income
  to **effective income**; annualization stated explicitly as its own rule.
- Management fee base confirmed as the **total income line** (rent + parking +
  other income), with no vacancy deduction.
- Removed an incorrectly added vacancy allowance line: there is no vacancy
  deduction, as the rent roll's in-place and contracted rent already reflects
  which units are occupied.
- Confirmed the derivation order: apply the 3-month rules first, then × 4 for
  the 12-month column. Added Rule 10 as a placeholder for 12-month-only
  exclusions, and clarified that the management fee is recomputed per column
  rather than annualized.
