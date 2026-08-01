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

1. **Set the default branch to `main`** — Settings → Branches.

   There is no org-wide way to do this. Rulesets *target* `~DEFAULT_BRANCH`; no
   rule type *assigns* it, so `default-branch-protection` cannot help — it is in
   fact currently protecting `claude/adopt-org-harness`, because it follows the
   pointer. The org-level "repository default branch name" setting applies only
   to newly created repositories.

   The declarative alternative is a `github_branch_default` resource under
   `infra/github-admin/` — note `github_repository.default_branch` is deprecated
   in the `integrations/github ~> 6` provider, and this repository would have to
   be imported first: only `infra` is declared there today.

2. **Delete the stale `claude/adopt-org-harness` branch** once `main` is default.
   GitHub refuses to delete a repository's default branch, so step 1 comes first.
