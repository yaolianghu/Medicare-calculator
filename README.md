# Medicare Cost Calculator

A single-file web app that estimates monthly Medicare costs at retirement, by state.
Open `index.html` in any browser — no build step, no server needed. It can also be added to a phone home screen.

## What it does

- **Standard assumptions (v1):** 40+ work credits, so Part A premium is $0.
- **Pick a state** (50 states + DC) and one of four coverage combinations:
  1. Original Medicare + Part D + Medigap
  2. Original Medicare + Part D
  3. Medicare Advantage (Part C)
  4. Original Medicare only
- Shows the monthly and annual total for each part, with deductibles listed for reference.
- **IRMAA (2026):** enter filing status (single / MFJ / MFS) and MAGI, and Part B shows the
  income-tier total premium while the Part D surcharge is added wherever drug coverage applies.
  Brackets are cliffs based on MAGI from two years prior (CMS 2026 table).
- **Bilingual UI** — a dropdown at the top switches the entire interface between 中文 and English.
- **Inflation projection:** pick a target year (default 2047) and an annual growth rate
  (default 5%) to project every premium line of the selected combination forward from the
  2026 base prices — a simplified single-rate projection, not a forecast.
- **Social Security estimate:** enter the estimated monthly benefit at full retirement age (PIA)
  and see the amount for every claiming age 62–70 (statutory early-claim reductions and
  delayed-retirement credits; FRA 67 for those born in 1960 or later).
- **"Switching plans without underwriting" reference section:** which states let you change
  Medigap plans with no health questions — year-round guaranteed-issue states (NY, CT, MA, ME, WA),
  states with annual guaranteed-issue windows (RI, DE, MN), birthday-rule states, the federal
  Part C / Part D enrollment windows (AEP Oct 15–Dec 7, MA OEP Jan 1–Mar 31), and Part A/B
  enrollment timing and late penalties.

## Data sources

- Part A / Part B 2026 national figures: CMS fact sheet (2026 Medicare Parts A & B premiums and deductibles)
- Average Part D premiums by state: KFF (2024, enrollment-weighted PDP averages)
- Average Medicare Advantage premiums by state: MedicareFAQ (2026)
- Medigap (Plan G / state equivalents) by state: MedicareCoverGuide (2026 estimates for a 65-year-old)
- Switching rules: KFF, *Medigap Guaranteed Issue Requirements*; Medicare.gov; state insurance departments

State averages are estimates for comparison only — not quotes. Medigap figures for MA/MN/WI are
closest-equivalent estimates (those states don't use standard letter plans). Switching rules were
verified in November 2026 and change frequently; confirm with your state insurance department or SHIP.

## Files

- `index.html` — the complete app (data + logic + styles in one file)
