# Colour Experience Study — Audit Trail

This repository is the **immutable append-only log** of every submission to the Colour Experience Study form at <https://shs-hum-epfl.github.io/shs-form/>.

Each file under `submissions/` represents exactly one participant's response. File name encodes its ISO timestamp, so `git log --oneline` gives the chronological order.

## How to audit

For any row *N* in the linked Google Sheet, there must exist a corresponding commit in this repo whose JSON content matches that row. A mismatch indicates either a Sheet edit that was not reflected in the audit log, or a GitHub commit that never made it to the Sheet. Both cases are immediately visible.

## Integrity properties

1. **Append-only** — new submissions are new files; nothing is ever rewritten.
2. **Cryptographic chaining** — every commit is a SHA of the previous commit plus the new content. Any tampering breaks the chain.
3. **GitHub-timestamped** — commit timestamps are set server-side by GitHub, not by the submitter.

## Contact

Research team: HUM 403 Experimental Cognitive Psychology, EPFL / UNIL — see the main form repo.
