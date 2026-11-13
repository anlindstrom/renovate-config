# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for the anlindstrom organisation's repositories. Renovate's onboarding
picks up `default.json` here by itself (`local>anlindstrom/renovate-config`), so a repository's own
`renovate.json` is one line:

```json
{ "extends": ["local>anlindstrom/renovate-config"] }
```

What it does: checks weekly (Monday, Stockholm time), waits 14 days after a release, groups minor and patch
updates into one PR per repository, opens majors one by one, and never automerges. Security fixes come at
once. The overseer reviews Renovate's PRs and lands them with `land-branch` (merge commit, then deploy);
automerge waits for a post-deploy watch with rollback.

The Renovate GitHub app must have access to this repository, or the preset cannot be read.

This is a copy of `anders-lindstrom/renovate-config`, for the repositories in this organisation: Renovate's
installation here cannot read the private preset on the personal account. Change both together.
