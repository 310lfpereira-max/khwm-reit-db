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

## 2. Annualization — quarterly actuals × 4

- The 12-month income statement is the **quarterly (T3) actuals multiplied by
  four**.
- This is the default treatment for every line item **except** where a specific
  rule below overrides it: rent and parking (Rule 5), management fee (Rule 3),
  utilities (Rule 6), and G&A (Rule 7).

## 3. Management fee — 5% of effective income

- Do **not** use the actual management fee expense recorded in the ledger.
- Management fee = **Effective income × 5.0%**.
- Applies in both columns: 5% of quarterly effective income in the T3 column,
  5% of annualized effective income in the 12-month column, so the fee scales
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
- Rationale: credit loss is already captured within the **vacancy allowance**,
  so carrying both would double count it.

---

## Line-item treatment summary

| Line item | T3 / Actual column | 12-month column |
|---|---|---|
| Rent | T3 actual (budget if held < 3 months) | Rent roll: contracted rent if a future contract exists, else in-place rent, × 12 |
| Parking | T3 actual (budget if held < 3 months) | Rent roll: contracted parking if a future contract exists, else in-place, × 12 |
| Vacancy allowance | Per underwriting (also absorbs credit loss — see Rule 9) | Per underwriting |
| Other income | T3 actual | T3 × 4 |
| Utility reimbursement income | Not shown separately — netted into Rule 6 | Not shown separately |
| **Effective income** | Basis for the management fee (Rule 3) | Basis for the management fee |
| Management fee | 5% of effective income | 5% of annualized effective income |
| Utilities | $261 / bedroom / year ÷ 4 | $261 × bedrooms |
| General & administrative | Budget | Budget |
| Repairs & maintenance | T3 actual, excluding any single repair > $2,500 | T3 (net of capital items) × 4 |
| All other operating expenses | T3 actual | T3 × 4 |
| Capital items (repairs > $2,500) | Excluded | Excluded |
| One-time costs (turnover, snow true-up, legal, marketing, bank fees) | Excluded | Excluded |
| Bad debt | Excluded | Excluded |

**Order of operations for the 12-month column:** strip exclusions first
(capital repairs, one-time costs, bad debt), then annualize the remainder ×4,
then overlay the rule-driven lines (rent/parking from the rent roll, utilities
per bedroom, G&A at budget), and compute the management fee last off the
resulting effective income.

---

## Open questions (to confirm as rules are added)

Flagged, not assumed — each of these moves the numbers:

1. **Effective income definition** — confirm it is gross potential rent less
   vacancy (and concessions), plus other income. Does "other income" belong in
   the 5% management fee base, or is the fee charged on rental income only?
2. **Repair threshold basis** — is the $2,500 test applied per **invoice**, per
   **work order**, or per **line item**? Current assumption: per invoice/charge.
3. **Which 3 months** — trailing 3 closed months, or a fixed calendar quarter?
   Current assumption: trailing 3 closed months.
4. **Rent roll as-of date** — which date drives "in place," and how far forward
   does a "future contract" count (any signed lease, or only those commencing
   within the next 12 months)?
5. **Vacancy allowance rate and source** — Rule 9 relies on it absorbing credit
   loss, so the rate needs to be stated: underwriting standard, actual, or
   market?
6. **Bedroom count source** — rent roll unit mix, and is it total bedrooms in
   the property regardless of occupancy?
7. **Utilities scope** — does $261/bedroom replace *all* utility accounts
   (water/sewer, gas, electric, trash), or only those the landlord pays
   directly, with any master-metered account handled separately?

---

## Change log

- Initial capture: rules 1–5.
- Added rules 6–9 (utilities per bedroom, G&A at budget, one-time cost
  exclusion, bad debt exclusion); management fee base refined from total income
  to **effective income**; annualization stated explicitly as its own rule.
