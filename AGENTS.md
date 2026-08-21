# AGENTS.md — tuned-org-uk.github.io

Guidance for any agent or human editing this repository.

## What this repo is

Landing page for [tuned-org-uk](https://github.com/tuned-org-uk), served at <https://tuned-org-uk.github.io>.

Zero-build static site: plain HTML + CSS, no JavaScript, no framework, no external fonts. GitHub Pages deploys automatically from `main`, root path. `.nojekyll` disables Jekyll processing. Do not add build tooling.

All asset paths must stay **relative**: the same page is reverse-proxied under `tuned.org.uk/github` on the origin server, and absolute paths break there.

## Hard content rules

1. **Org-authored repos only.** List a repository only if org members authored it or own it. Never list third-party forks: a repo with `fork == true` whose `parent` is outside the org is excluded (past offenders: `titans-pytorch` → lucidrains, `infera` → CogitatorTech). Internal derivatives of org-owned parents are allowed (`latent-sound-diffusion` forks the org's own `arrowspace-latent-diffusion`).
2. **Never link private repositories.** Verify visibility before adding any repo link:

   ```sh
   curl -s -o /dev/null -w '%{http_code}' https://api.github.com/repos/tuned-org-uk/NAME
   ```

   `404` means private or missing — do not link it. If the artefact matters and the repo is private, link its publication instead of the repo (done for `LSD-studio`).
3. **Papers go in their home section.** ArrowSpace papers in the `#papers` strip inside the ArrowSpace section; sound/diffusion papers in the LSD section; per-repo papers inside that repo's card. Always link DOIs through `https://doi.org/<doi>`, never raw `zenodo.org/records/...` URLs.
4. **Check before you claim.** Fetch real metadata (GitHub API / Zenodo API) for descriptions, titles, authors, dates. Never invent a DOI, star count, or description.

## Known publications

| Work | Link |
|---|---|
| The ArrowSpace Algorithm: From Graph Wiring to τ-Mode Spectral Search | DOI 10.5281/zenodo.21679021 |
| Topological Indexing of Vector Spaces (JOSS) | DOI 10.21105/joss.09002 |
| Energy-dispersion networks | arXiv:2606.21535 |
| Spectral Composition (behind Latent Sound Diffusion) | DOI 10.5281/zenodo.21950475 |
| Vibrational Deduction Transformer (VDT) | DOI 10.5281/zenodo.20816835 |

## Style rules

- Design tokens live at the top of `style.css`. Dark theme, single amber accent `#ffb454`. No purple gradients, no stock hero art, no shadow-heavy cards.
- WCAG AA: amber is a fill colour with dark ink `#17110a`, never text on light backgrounds.
- Copy: Simplified Technical English — short sentences, active voice, factual tone. No superlatives, no marketing filler.
- No comments in code. No emoji unless asked.

## Update checklist

- Star counts and copy are static; refresh after releases or milestones.
- Before push: grep `index.html` for names of removed or private repos — expect zero matches.
- After push: confirm deployment with `curl -s https://tuned-org-uk.github.io/` plus a content check.

## Commits

Conventional-commit style messages (`feat(nav): …`, `Remove forks from research grid`). Commit author: `Mec-iS <3146196+Mec-iS@users.noreply.github.com>`.
