# gh-action-node-uniqueness

Node.js identity-key uniqueness gate — no identity key may repeat in any data cut.

## Status: not implemented

This repository is a **placeholder**. The description above states the intent; no
working code exists here yet.

It had **no commits and no default branch** until 2026-08-01, when the org Claude
harness rollout ([.github-private#226](https://github.com/bounded-systems/.github-private/issues/226))
wrote the first ones. That rollout opens a draft PR per repo, which requires a
base branch — with none present, its working branch `claude/adopt-org-harness`
became this repository's default branch instead, and PR creation failed.

`main` and this file exist to give the repository a real default branch. The
harness baseline (`.claude/`) is carried here too, so the repository is adopted
in the same shape as the rest of the org.

## Follow-up

Two things still need a hand, neither doable through the session proxy (writes to
the repository-settings API are blocked there):

1. Set the default branch to `main` — Settings → Branches, or declare
   `default_branch = "main"` in `infra/github-admin/repositories.tf` and apply
   through `repo-admin-apply.yml`.
2. Delete the stale `claude/adopt-org-harness` branch once `main` is default.
   GitHub refuses to delete a repository's default branch, so step 1 comes first.
