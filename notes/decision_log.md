# Decision Log

Rationale for program and infrastructure decisions. Newest first.

## 2026-06-19 — Website deploys from a separate repo (two-repo split)

**Context.** The live site `khalsascholars.org` is served by **GitHub Pages from a
different repo** than this one:

- **Source of truth (this repo):** `amar-saigal/khalsa-scholars-academy` — holds the
  full project: `website/` HTML, `current-families-copy.md`, prompts, config, notes.
- **Deploy repo (live site):** `khalsascholars/khalsascholars.github.io` — classic
  (`legacy`) GitHub Pages, branch `main`, path `/`, custom domain `khalsascholars.org`,
  HTTPS enforced. A push to its `main` auto-publishes in ~1 min (no CI/Actions).

The two repos are **not linked**. Historically the deploy repo received files via
manual "Add files via upload" through the GitHub web UI.

**Implication.** A website change requires **two steps**: (1) commit the edit here for
source-of-truth, then (2) copy the changed HTML into the deploy repo and push to publish.
Easy to update one and forget the other → drift.

**Current state (2026-06-19).** Both repos are consistent. The new unlisted
`current-families.html` (Current Families reference page; `noindex`, not linked from nav)
is live and committed in both.

**Open cleanup option (not done — bigger change).** Consolidate to a single repo: serve
Pages directly from `amar-saigal/khalsa-scholars-academy` (move HTML to repo root or a
`/docs` folder, enable Pages, and re-point the `khalsascholars.org` custom domain /
CNAME here). Eliminates the two-repo drift risk. Deferred — revisit when there's appetite
for the DNS/Pages reconfiguration.
