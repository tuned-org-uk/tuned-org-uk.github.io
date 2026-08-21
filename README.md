# tuned-org-uk.github.io

Organisation landing page for [tuned-org-uk](https://github.com/tuned-org-uk), served at <https://tuned-org-uk.github.io>.

Zero-build static site: plain HTML + CSS, no JavaScript, no framework. `.nojekyll` disables Jekyll processing so the site deploys as-is from `main` / root.

## Layout

- `index.html` — single page: hero, ArrowSpace flagship, Latent Sound Diffusion (+ Zenodo paper DOI 10.5281/zenodo.21950475), SmartCore, research grid.
- `style.css` — design tokens and layout. Dark theme, one amber accent, system font stack.

All asset paths are relative on purpose: the page can be reverse-proxied under a subpath (e.g. `tuned.org.uk/github`) without changes.

## Update checklist

Star counts and section copy are static. Refresh after releases or star milestones.
