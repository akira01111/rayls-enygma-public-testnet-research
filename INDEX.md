# INDEX — Rayls Enygma Public Testnet research archive

Complete index of this repository: what is here, where it came from, its
size and SHA-256, and its status. One canonical home per file — other places
link here or to the package, never duplicate content.

Repository: `rayls-enygma-public-testnet-research` (public). HEAD `1676829`
(structure READMEs only). **Nothing is committed or pushed yet** (Anara's
rule — commit only after her final review).

**Git status (22 Nov 2026; nothing staged, nothing committed):**
- Modified tracked files (9; `git diff --stat`: 97 insertions, 2 deletions):
  `README.md`, `contracts/abis/README.md`, `contracts/addresses/README.md`,
  `contracts/verified-source/README.md`, `experiments/README.md`,
  `experiments/transactions/README.md`, `findings/README.md`,
  `raw-data/videos/README.md`, `scripts/README.md`.
- New untracked files (working tree only): `.gitignore`,
  `01-no-overwrite-fix-report.md`, `INDEX.md`, `RESEARCH-TRAIL.md`,
  `REPRODUCE.md`, `audit-reports/`, `contracts/addresses/addresses.json`,
  `experiments/g1-g6-decision-table.md`,
  `experiments/testnet-journeys/week2-private-payment/`,
  `experiments/transactions/tx-09edab2b/`,
  `raw-data/screenshots/chk-21-public.jpg`,
  `raw-data/screenshots/chk-22-public.jpg`, `raw-data/screenshots/chk-23.jpg`,
  `runs/`, `scripts/01_network_identity.py`,
  `scripts/decode_tx_09edab2b.py`, `scripts/tx_audit_09edab2b.py`,
  `scripts/verify_tx_audit_09edab2b.py`.
  (`raw-data/videos/` footage + VO mp3 are no longer untracked: excluded
  by `.gitignore` as local-only, 22 Nov 2026 — see §5. The ticket draft
  (`tickets/rayls-team-questions-draft-2026-11-22.md`) is also no longer
  in the public batch: local draft, excluded 22 Nov 2026 — see §8. The
  original final videos + `chk-21.jpg`/`chk-22.jpg` are gitignored as
  sanitization originals — see §5.)
- Excluded local files (gitignored, never to be committed): `pdf/` (10 review
  PDFs + 138 validation PNGs + 19 build-source files = 167 files),
  `experiments/transactions/tx-09edab2b/.src/validate/` (155 PNGs),
  the Week 2 video inputs in `raw-data/videos/` (source footage
  24,777,960 B + VO mp3 2,953,936 B; exact-path rules in `.gitignore`,
  hashes kept in the journey manifest), and the sanitization originals
  (22 Nov 2026): the original final videos
  (`enygma-week2-private-payment-final.mp4`,
  `enygma-week2-private-payment-final-1080p.mp4`) + `chk-21.jpg` /
  `chk-22.jpg`, which still show truncated Enygma Spend/View key
  fragments (public sanitized versions committed instead; hashes kept in
  the journey manifest). `.gitignore` enforces this.

Start here: `README.md` (purpose + structure) → `RESEARCH-TRAIL.md`
(chronological trail) → `REPRODUCE.md` (how to re-run everything).

## 1. Entry points

| path | bytes | SHA-256 (first 16) | status |
|---|---|---|---|
| `README.md` | — | — | Overview; Status section lists Module 01 + TX audit + video journey (tracked file, modified 22 Nov 2026) |
| `RESEARCH-TRAIL.md` | 31,322 | `302b23ef8befdacc` | Chronological trail, 21–22 Nov 2026 (untracked, new) |
| `REPRODUCE.md` | 56,343 | `4f4e13ed95cf20d3` | Reproduction guide (untracked, new) |
| `INDEX.md` | — | — | This file (untracked, new; its own hash is not listed — self-reference) |
| `audit-reports/ENYGMA-TESTNET-AUDIT-REPORT.md` | 64,787 | `1d2ab730a6df4abc` | Initial audit, verbatim copy (see §3) |
| `audit-reports/README.md` | 1,753 | `08c596e3fc7b4400` | Provenance of the audit copy |

## 2. Module 01 — Network Identity Audit (21 Nov 2026)

Script: `scripts/01_network_identity.py` v2.0.1, 35,650 bytes,
SHA-256 `5ff78700346b2ebd0c1a1e14c2f615b3fd4d422bb7cbbec489b3d48743260ae0`.
Change report: `01-no-overwrite-fix-report.md`, 15,329 bytes,
SHA-256 `435c75d289b172a69…`. Runs guide: `runs/README.md`, 7,705 bytes,
SHA-256 `4e8fa10506a679d4a…`.

| run | script | result | evidence |
|---|---|---|---|
| `runs/20261121T054711Z/` | v1.0.0 | PASS 9/9 | raw `2131d690…`, CSV `156c0b71…`, metadata `8d4e6011…`, checksums file `7b730708…`, verification report `aa544d47…`, combined report `bc7692ef…`, script copy `39caa42b…` (v1 manifest uses bare filenames — verify individually, see `runs/README.md`) |
| `runs/20261121T063234Z/` | v2.0.1 (build `c09d88eb…`, short check names) | PASS 13/13 | manifest 5/5 OK via `sha256sum -c` from the run dir |
| `runs/20261121T063327Z/` | v2.0.1 (build `5ff78700…`, long check names) | PASS 13/13 | manifest 5/5 OK via `sha256sum -c` from the run dir; final run |

Each run dir holds: `runs/<run_id>/raw-data/rpc-responses/01_network_identity_raw.json`,
`runs/<run_id>/datasets/` (CSV + metadata + checksums manifest),
`runs/<run_id>/findings/verified-facts/`
(verification report; run 1 also has the combined reading-copy report),
`runs/<run_id>/scripts/01_network_identity.py` (byte copy of the script that ran).

## 3. Initial audit report (21 Nov 2026)

- `audit-reports/ENYGMA-TESTNET-AUDIT-REPORT.md` — 64,787 bytes, 617 lines,
  SHA-256 `1d2ab730a6df4abc99af830ac1ef4e3a7d8845b3b78ee51c9a7dcda51c50c711`.
  Verbatim copy of `~/workspace/rayls-enygma-audit/ENYGMA-TESTNET-AUDIT-REPORT.md`
  (same hash; `cmp` byte-identical). Provenance in `audit-reports/README.md`.
- Coverage: contract map (§C), observable activity (§D), volume (§E),
  privacy limits (§F), experiment plan G.1–G.6 (§G), repo structure (§H),
  source/address/hash register (§I). Its conclusion (selective auditing not
  independently verifiable) STANDS unless new evidence appears.

## 4. Week 2 TX audit package (21–22 Nov 2026)

`experiments/transactions/tx-09edab2b/` — TX
`0x09edab2bb8914aea3c905608ea9fcd09c056a470a5e150df03e0b324eff525bb`,
block 24825928. 20 manifest files + combined review PDF + `.src/` build
artifacts. Manifest: `manifest.json`, 9,351 bytes,
SHA-256 `58e68862de4c6825…` (covers all 20 files; the manifest itself and
the PDF are not listed in it). Updated 22 Nov 2026 for the stage-1
close-out (TODO.md entry only); all other entries unchanged and
re-verified against disk; verifier 23/23 PASS.

| group | files |
|---|---|
| raw (chmod 444) | `transaction.json`, `receipt.json`, `logs.json`, `block.json`, `contracts.json`, `explorer.json`, `explorer-relayer-txlist.json`, `registry-usernames.json`, `related-tx-0xacc7d175.json` (9 files: 5 script-generated + 4 manual — see REPRODUCE.md §2) |
| decoded | `decoded_events.json`, `audit_summary.json`, `bundle-abi-extract.json`, `lookups-4byte.json` |
| docs | `TX-AUDIT-REPORT.md` (16,604 B), `gaps.md` (5,004 B), `TODO.md` (3,765 B; re-fetch box checked at stage-1 close-out, 22 Nov 2026), `ADDENDUM-2026-11-22.md` (2,650 B; @kittynim owner-confirmed + integration note) |
| scripts | `scripts/tx_audit_09edab2b.py` v1.1.0, `scripts/decode_tx_09edab2b.py` v1.0.0, `scripts/verify_tx_audit_09edab2b.py` v1.0.1 |
| review copy | `01_tx_audit_complete_history.pdf`, 904,036 bytes, 155 pp, SHA-256 `b449fd80633393f9…` (derivative only, not in the manifest) |

Verification: independent verifier 23/23 PASS (re-run 22 Nov 2026,
exit 0). Key results: transferV2 proven, direct to SharedVaultProxy,
7 logs (1 Nullifier / 3 Commitment / 3 EncryptedNote), integer
4.416 × 10¹⁸ in calldata statement[8] (the RLS unit is an
interpretation from the app display and the "total fee" meaning is an
inference — see the article audit r3 §3.2), chain gas 0.063168048
native units (token identity disputed: RLS vs USDr — r3 §3.3), and a
separate ERC-20 transfer() call with arguments (`0x71af…`, 0.576 RLS)
4 blocks later (recipient identity and purpose unknown — r3 §7.5
claim 5). Receiver @kittynim → `0x680d90983da58bcb7d127e3421193274e84e0efc`
(on-chain verified + owner-confirmed 22 Nov 2026).

## 5. Week 2 video journey (21 Nov 2026)

`experiments/testnet-journeys/week2-private-payment/` — 9 files in the
manifest + README + manifest itself + article audit (r1/r2/r3/addendum).
Manifest `manifest.json`, 8,827 bytes, SHA-256 `0b4ba448d8517b2c…`, covers
16 files incl. inputs in `raw-data/`.

- Public finals (sanitized, 22 Nov 2026 — committed):
  `enygma-week2-private-payment-final-720p-public.mp4` (720p, 10,041,261 B,
  `b5c91ee1…`); `enygma-week2-private-payment-final-1080p-public.mp4`
  (upscale, 20,153,708 B, `e1e7a339…`). Truncated Enygma Spend/View key
  fragments are blurred at t 20–24, 82–88, 109–115, 138–144, 176–185.533 s;
  otherwise the same content as the originals (see the journey README and
  the article audit addendum §C.6).
- Original finals (`enygma-week2-private-payment-final.mp4`,
  `enygma-week2-private-payment-final-1080p.mp4`) are **LOCAL-ONLY,
  excluded from the public repository by `.gitignore`** (22 Nov 2026):
  they still show the key fragments. Hashes kept in the journey manifest
  for provenance.
- `subs.ass` (44 cues, `f9aa42fa…`), `build_subs.py`, `build_video_v2.py`,
  `EDIT-PLAN.md`, `QA-REPORT-V2.md`.
- Article audit (current): `ARTICLE-AUDIT-2026-11-22-r3.md` (59,742 B,
  `6a1be437…`) + `ARTICLE-AUDIT-2026-11-22-addendum-f17.md` (F17 split
  F17a/F17b + pre-commit checks). Revisions r1/r2 are superseded, local
  record only, NOT committed.
- Inputs in `raw-data/videos/`: source footage (24,777,960 B,
  `610a5cd30d…` — filename is its content hash) + VO mp3 (2,953,936 B,
  `ebb2fdda…`). **Both are LOCAL-ONLY, excluded from the public
  repository by `.gitignore` (22 Nov 2026); hashes kept in the journey
  manifest for provenance.**
- Spelling-check frames in `raw-data/screenshots/`: `chk-21-public.jpg`,
  `chk-22-public.jpg` (public sanitized versions, key line blurred),
  `chk-23.jpg` (all read "Enygma"). Originals `chk-21.jpg`/`chk-22.jpg`
  are LOCAL-ONLY (see above).
- Full file list with hashes: the journey `manifest.json`.

## 6. Contracts

- `contracts/addresses/addresses.json` — 9,202 bytes,
  SHA-256 `f78f012886035836…`. Machine-readable contract map extracted
  verbatim from the initial audit (§C.2/C.3): yx + bx deployments, EIP-1967
  implementation slots, auditor/relayer/Multicall3/forwarder/EnygmaDvp,
  unknown-provenance `0xd908…`. All 35 addresses verified present in the
  audit report. The bx mismatch is recorded in the file's notes.
- `contracts/abis/README.md` — points to the TX package's
  `experiments/transactions/tx-09edab2b/decoded/bundle-abi-extract.json` (canonical home; not duplicated).
- `contracts/verified-source/README.md` — states plainly: **no verified
  contract source exists** for the deployed vault/registry implementations.

## 7. Scripts (no on-chain writes or signing; some scripts write local artifacts)

| script | version | bytes | SHA-256 (first 16) | role |
|---|---|---|---|---|
| `scripts/01_network_identity.py` | v2.0.1 | 35,650 | `5ff78700346b2ebd` | Module 01 fetch + checks |
| `scripts/tx_audit_09edab2b.py` | v1.1.0 | 17,448 | `6bee0b827faa24c0` | TX audit raw fetch (curl) |
| `scripts/decode_tx_09edab2b.py` | v1.0.0 | 37,807 | `e1dca19041676bed` | TX audit decode + summary |
| `scripts/verify_tx_audit_09edab2b.py` | v1.0.1 | 10,734 | `e081c3c22cbcceaa` | TX audit independent verifier |

## 8. Gaps and TODO (open)

- TX package: `experiments/transactions/tx-09edab2b/gaps.md` (7 gap groups)
  and `TODO.md` (ticket, experiments G.1–G.6, fee-settlement pattern
  check, Module 02 blocked, commit/push). The re-fetch check is CLOSED
  (stage 1, 22 Nov 2026; comparator v2.1.1 CERTIFIED).
- Consolidated standing unknowns: `RESEARCH-TRAIL.md` (last section).
- Ticket to the Rayls team: draft written 22 Nov 2026
  (`tickets/rayls-team-questions-draft-2026-11-22.md`, 10 questions,
  taxonomy-labelled), NOT SENT, and **excluded from the current public
  batch** (22 Nov 2026 decision — its classifications predate r3; local
  draft for separate revision).

## 9. Explicit exclusions (not in this repo, by decision)

- **Old research repo** `~/workspace/rayls-enygma-research/` (19 files,
  13–15 Nov + inventory review): referenced, never copied, never mixed in.
  Its `technical-evidence.md` and the baseline PDF
  (`~/workspace/your_files/rayls-enygma-technical-evidence/rayls-enygma-technical-evidence.pdf`,
  23 pp, 494,423 B, SHA-256 `2193d48b61715809b4a045eccf13663675d032cd92b24ce5bcc2ad4b4ce3d3ee`,
  created 15 Nov 2026) stay outside this repo.
- **`pdf/`** (10 review PDFs + 138 validation PNGs + 19 build-source files
  = 167 files, counted 22 Nov 2026): local-only review archive, never to be
  committed.
- **Superseded video versions** (`*-v720-backup.mp4`, `subs-v2-backup.ass`,
  `...-1080p-v2.mp4` byte-duplicate) and video working intermediates
  (`video_only*.mp4`, `segments_v2/`, `frames/`, `qa/`, `transcript/`, …):
  retained in `~/workspace/enygma-week2-video/`, not copied here.
- **Other 21 Nov workstreams** (Groq connector, PocketPal, video-generation
  audit, Raka animation, Marivale game): different projects, not Rayls
  research — not in this repo.
- **The 12:30 WIB inventory review (21 Nov):** delivered in chat only; no
  file exists. Recorded as a gap in `RESEARCH-TRAIL.md`, not reconstructed.
