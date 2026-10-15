# PreRFQ V003.9.8 — Staging gate register (2026-10-15)

Status: **HOLD — Gate 1B**. This is a readiness register, **not** an approved migration or a deployed implementation.

## Verified environment
- Supabase project: `prerfq-staging` (`zduosfmjmydcjkbwsewc`), PostgreSQL 17.
- `prerfq_staging` exists and contains **zero application tables** as inspected on 2026-10-15.
- Schema USAGE for `anon`, `authenticated`, and `service_role`: **false** (verified via read-only SQL).
- A migration-history version exists (`20261014165605`), but this does **not** establish V003 deployment.
- Production compatibility requirement: PostgreSQL 16.x.

## Unresolved Gate 1B blockers
1. **Input ingestion boundary** — prove replay cannot inject or substitute unverified evidence.
2. **Independent verifier separation** — independently authenticated verifier must be distinct from evidence writer and sealing authority; verify role escalation and SECURITY DEFINER paths.
3. **Regulatory denial binding** — verify structured authority/reference and associated evidence before allowing a denial decree to influence results.
4. **Manifest canonicalization** — deterministic canonical payload and independently recomputable digest; preserve initiating SESSION_USER separately from privileged CURRENT_USER.
5. **Seal cutoff** — prove that evidence accepted after the as-of cutoff cannot influence a sealed prediction.
6. **Lineage** — enforce evidence/claim/project/effective-date consistency; prevent cross-project substitution.

## Required tests before deployment
- Positive-path evidence ingest, independent verification, seal, and historical replay.
- Negative tests: forged verification, mismatched digest, bogus disclosed fact, late evidence, wrong project, denial without valid authority, privilege escalation, role spoofing.
- Audit evidence of exact SQL, expected/actual outcomes, role identities, and PostgreSQL 16 compatibility.
- Security review of grants, default EXECUTE, SECURITY DEFINER search_path, and RLS where exposed.
- Approval only after tests pass; never treat a SQL script as proof of execution.

## Planned subsequent work (not yet deployed)
- Immutable source/evidence ledger, SEC vs Radar observation timestamps, positivity/confidence/momentum scores, outcome history, and source-preserving object storage.
- PreIPO remains a logically separate consumer of verified shared evidence.
- No trading, paid services, or client-facing claims implied by this register.
