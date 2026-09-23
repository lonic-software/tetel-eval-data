# tetel-eval-data

Measurement data for [tetel](https://github.com/lonic-software/tetel)'s evaluations: model replies,
draws and hand labels. The scripts that produce and score it live in tetel; this repository holds
only what they read and write.

It is kept out of tetel's worktree on purpose (TET-97). The data quotes tetel's memo prose, so inside
the worktree it matched almost any common word in every census tetel took of its own source, and a
census that captured it shipped megabytes into a memo's evidence permanently.

## Layout

`verifier-eval/` is the data for tetel's `scripts/verifier-eval/`. A file tetel's scripts or memos
name as `scripts/verifier-eval/<rel>` is `verifier-eval/<rel>` here, byte for byte as tetel last
committed it:

- everything under `verifier-eval/` except the two run directories below was tracked in tetel up to
  tetel commit `612f59f`, the last commit to have it. That commit holds every file a tetel memo
  cites, e.g. `git show 612f59f:scripts/verifier-eval/fact_v1.json`. A memo's own pin may not,
  because some files were cited before they were committed;
- `verifier-eval/tet98/` and `verifier-eval/tet98-gpt6/` are TET-98's raw draws and the one-draw
  `gpt-6-luna` screen, which were never tracked in tetel (they sat in `../tetel-eval-runs/`).

## Using it

Check this repository out beside tetel, so that it is `../tetel-eval-data` from tetel's root; that is
where the scripts look by default. To keep it elsewhere, set `TETEL_EVAL_DATA` to this repository's
root. New draws are written here, and committed here, not in tetel.
