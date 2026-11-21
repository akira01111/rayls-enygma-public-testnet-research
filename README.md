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
- `datasets/` — processed, tabular data derived from `raw-data/`.
- `scripts/` — read-only audit and reproduction scripts.
- `contracts/` — ABIs, source references, and deployment configuration.
- `docs-review/` — notes on official docs, blog posts, and reference implementations.
- `experiments/` — experiment plans and records (testnet only, after approval).
- `findings/` — findings sorted by evidence label (see below).
- `tickets/` — questions sent to the Rayls team, and their responses.

## Evidence rules

Every finding is labelled as one of: verified fact, official claim, direct
observation, reconstruction, inference, or unknown. A documented claim is not
a verified fact until it is independently checked. Shielded activity that
cannot be observed is recorded as unobservable — never estimated silently,
and never double-counted.

## Status

Structure only (21 Nov 2026). No audit evidence, experiment results, or
article drafts have been uploaded yet.
