# PreIPO — Evidence-first IPO intelligence experiment

## Objective
Identify private companies showing verifiable signals of potential IPO preparation, without treating speculation as fact or implying that private shares are available to purchase.

## Signal categories
1. Official SEC registration and public filings (highest confidence; may already be publicly announced).
2. Company-confirmed IPO plans, leadership appointments, auditor and governance changes.
3. Credible reporting of confidential filing or underwriter selection (reported, not independently confirmed).
4. Funding, secondary transactions, investor exits, and changes in ownership.
5. Hiring, operational maturity, and financial reporting preparation (weak contextual evidence).

## Evidence record
Each record must contain: company, signal_type, event_date, observed_at, source_url, source_title, verbatim_short_excerpt, evidence_class (primary/secondary), confidence, contradictory_evidence, and review_status. Never infer an IPO filing from ordinary fundraising or hiring.

## MVP
- Collect 20 candidate companies using legal public sources and APIs.
- Store individual evidence records with source URLs and observation dates.
- Rank using transparent rules; display why each company scored as it did.
- Separate IPO probability from IPO timing and investability.
- Track predictions against subsequent confirmed outcomes; compare against a simple baseline.
- No paid subscriptions, automated trading, or claims of proprietary nonpublic access.

## Proposed folders
`collectors/`, `evidence/`, `scoring/`, `tests/`, `dashboard/`.

## Guardrails
Respect site terms and robots policies; do not bypass access controls. SEC confidential submissions are not publicly accessible before publication. A public signal is not proof of an upcoming IPO. Preserve dates and source provenance. Do not use employer-owned confidential information.
