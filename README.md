# rayls-enygma-public-testnet-research

Research and evidence repository for Rayls Enygma Public Testnet.

## Purpose

Independent research on the Rayls Enygma Public Testnet: architecture, deployment
configuration, observable on-chain activity, and hands-on testnet experiments.
The goal is to help the community understand what Enygma is, how it works,
and what can actually be verified — nothing more.

## Structure

- `raw-data/` — raw evidence exactly as captured (RPC responses, explorer exports,
  bundle files). Never modified.
- `audit-reports/` — verbatim copies of audit reports, never edited after copying.
- `datasets/` — processed, tabular data derived from `raw-data/`.
- `scripts/` — read-only audit and reproduction scripts.
- `contracts/` — ABIs, source references, and deployment configuration.
- `docs-review/` — notes on official docs, blog posts, and reference implementations.
- `experiments/` — experiment plans and records (testnet only, after approval).
- `findings/` — findings sorted by evidence label (see below).
- `tickets/` — draft questions for the Rayls team (DRAFT, not sent; excluded from the current public batch — local draft for separate revision).

## Evidence rules

Every finding is labelled as one of: verified fact, official claim, direct
observation, reconstruction, inference, or unknown. A documented claim is not
a verified fact until it is independently checked. Shielded activity that
cannot be observed is recorded as unobservable — never estimated silently,
and never double-counted.

## Status

- **Module 01 — Network Identity Audit (21 Nov 2026):** PASS 9/9 (v1.0.0)
  and PASS 13/13 (v1.0.1, two runs). Evidence in `runs/`, script in
  `scripts/01_network_identity.py`, change report
  `01-no-overwrite-fix-report.md`. Not committed yet — commit only after
  Anara's final review. Review PDFs in `pdf/` are local only, never committed.
- **Week 2 TX audit — `0x09edab2b…` (21–22 Nov 2026):** transferV2 payment
  audit, verified with an independent script (23/23 checks). Evidence package:
  `experiments/transactions/tx-09edab2b/` (raw JSON, decoded JSON, manifest,
  report, gaps, TODO, addendum). Receiver @kittynim → `0x680d…0efc`
  (on-chain verified + owner-confirmed 22 Nov 2026).
- **Re-fetch verification — stage 1 CLOSED (22 Nov 2026):** comparator
  v2.1.1 CERTIFIED 12:33 WIB (regression test 8/8 PASS, real run 9/9 PASS,
  15 integrated negative tests rejected as expected, dynamic-only PASS).
  Scope: the certification covers ONLY comparator v2.1.1 and the recorded
  test scope — NOT the whole repo and NOT all Rayls audit claims.
- **Initial audit report (21 Nov 2026):** verbatim copy in `audit-reports/`
  (SHA-256 `1d2ab730a6df4abc99af830ac1ef4e3a7d8845b3b78ee51c9a7dcda51c50c711`).
- **Week 2 video journey:** `experiments/testnet-journeys/week2-private-payment/`
  (finals, inputs, manifest).
- **Index / trail / reproduce:** `INDEX.md`, `RESEARCH-TRAIL.md`, `REPRODUCE.md`.
- No article drafts yet. No ticket has been sent to the Rayls team yet.
