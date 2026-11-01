# Corrections

Mistakes in publishing the track record are recorded here. Published scores are never changed.

## 1 Nov 2026 — late publication after a hosting outage

- **What happened:** the server that ran the nightly job was shut down by its hosting provider on 30–31 Oct 2026.
  The US scores and model-family views for **2026-10-30**, normally published around 01:45 UTC on 31 Oct, were
  published on **1 Nov 2026 at 05:26 UTC** (ledger `published_at`), after the data were collected again and the
  same, unchanged code was run on another machine.
- **Effect:** none on the record's fairness. Publication was still before the next US trading session (Monday
  2 Nov 2026), so no outcome was known when the scores were fixed. No trading day was skipped (31 Oct and 1 Nov
  were a weekend). India scores for 2026-10-30 were published on time.
- **Prevention:** the nightly job moved to a scheduled cloud runner (GitHub Actions) and the site to Cloudflare Pages.

## 19 Oct 2026 — model-family file overwritten by a new version

- **What happened:** on 19 Oct 2026 the model zoo moved from version `zoo-v1` (9 models) to `zoo-v2` (12 models).
  Its views for 2026-10-16 were published under the same file name as the `zoo-v1` file,
  `families/2026-10-16.csv`, and overwrote it. The ledger kept both fingerprints, so the check failed for `zoo-v1`.
- **Fix:** the original `zoo-v1` file and its OpenTimestamps proof were restored byte-for-byte from git history
  (commit made on 19 Oct 2026, 18:43 SGT). They match the ledger fingerprint again. The `zoo-v2` file was renamed to
  `families/2026-10-16_zoo-v2.csv`; its content and fingerprint are unchanged, and only its path in the ledger changed.
- **Timestamp:** the `zoo-v2` file had not been timestamped when it was published, so it was timestamped on
  19 Oct 2026 when this correction was made.
- **Prevention:** file names now include the version, and publishing refuses to overwrite any existing file.
- **Not affected:** the score files (`scores/`) and their proofs.
