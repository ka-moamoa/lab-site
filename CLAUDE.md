# Ka Moamoa Lab website

Hugo static site using the [Blowfish](https://blowfish.page) theme, deployed to
**kamoamoa.com** via GitHub Pages. Migrated off Bluehost/manual-upload hosting
in August 2026 (see git log around that date for the full story).

## Deployment — how a change actually goes live

1. Push to `main` on **`public`** remote (`https://github.com/ka-moamoa/lab-site` —
   note the remote name is `public`, not `origin`; see "Remotes" below).
2. That push triggers `.github/workflows/deploy.yml`: installs Hugo, builds with
   `hugo --gc --minify`, deploys the `public/` output to GitHub Pages.
3. Pages serves it at `kamoamoa.com` (DNS: Squarespace registrar, nameservers
   pointed at Squarespace's own DNS, A/AAAA records pointed at GitHub's Pages
   IPs, HTTPS cert issued by GitHub). No Bluehost involvement anymore.

**Nothing deploys automatically from any other remote.** If you only push to
`origin` (see below), the live site does not change.

## Remotes — read this before pushing

```
public   https://github.com/ka-moamoa/lab-site.git        <- THIS is what deploys
origin   https://github.gatech.edu/Ka-Moamoa/lab-site.git  <- GT enterprise, private, does NOT deploy
```

This naming is backwards from convention (`origin` is usually the primary
remote) and easy to get wrong. `origin` is Georgia Tech's private Enterprise
GitHub — kept in sync for internal/institutional reasons, but its Pages
feature requires a GT login to view, so it can't host a public site (this was
tested and confirmed during the migration). **Push to `public` for anything
you want live.** Pushing to both keeps them in sync; pushing to only `origin`
silently does nothing for the live site.

Consider renaming these remotes (`git remote rename public origin` after
first renaming the old `origin` to something like `enterprise`) the next time
you're in here, so `git push` without arguments does the right thing by
default.

## Before you push: things that bit us once already

This repo has a history of files that render correctly on a local machine but
were **never actually committed to git**, so a fresh clone/CI build fails or
serves 404s even though everything "worked." Every one of these was traced
down the hard way once — don't repeat the exercise. Before pushing a content
or config change, run:

```bash
git status
```

...and treat every untracked file with suspicion, not just files you know
you edited. Specifically:

- `git ls-files config/_default/hugo.toml` should NOT be empty — this file
  sets `theme = "blowfish"`. Without it, the theme doesn't mount and every
  page fails with "template for shortcode X not found."
- `git ls-files hugo.toml` (root) should NOT be empty — sets `baseURL` and
  `markup.goldmark.renderer.unsafe = true`, which several pages (News, About)
  rely on for raw HTML blocks to render instead of getting escaped.
- Any raw `<img src="img/...">` HTML tag (as opposed to markdown `![]()`
  syntax) is served literally from `static/img/`, NOT processed through
  Hugo's asset pipeline. Check `git ls-files static/img/` isn't empty. This
  specifically bit the homepage's Partners/Funding logos and two video
  thumbnails — they worked locally (browser cache from earlier testing) and
  404'd on a fresh deploy.
- `go.mod`/`go.sum` are intentionally gitignored and NOT needed — see next
  section for why.

**The fastest way to catch this class of bug going forward:** clone the repo
fresh into a scratch directory and try to build there, rather than trusting
`hugo server` in this working directory (which has accumulated years of
untracked local state).

```bash
git clone --recursive public /tmp/lab-site-fresh-check
cd /tmp/lab-site-fresh-check && hugo --gc --minify
```

If that fails or looks wrong, something you rely on isn't actually committed.

## Theme setup — do not add back a Hugo Modules import

The theme is a **git submodule** at `themes/blowfish`, currently pinned to
`v2.98.0`. Clone with `--recursive`, or run
`git submodule update --init --recursive` after a plain clone.

`config/_default/module.toml` has `disable = true` for the Blowfish Hugo
Module import **on purpose**. At one point this repo had both a Hugo Module
import (pinned to a stale `v2.96.0`) and the submodule (`v2.98.0`) active at
once, and the stale module version silently won, causing an unstyled/
unreadable homepage (a real upstream Blowfish bug in that version, already
fixed in the submodule's newer version). If you ever run `hugo mod` commands
in this repo, double check `module.toml` afterward — don't let that import
get re-enabled.

## Hugo version

CI pins Hugo to **0.161.1 extended** (see `HUGO_VERSION` in
`.github/workflows/deploy.yml`). Use the same version locally
(`brew install hugo` currently installs this) to avoid "works for me"
surprises — Blowfish has shown real behavioral differences across Hugo
versions in this repo already.

## Homepage config, and why it's set the way it is

In `config/_default/params.toml`:

- `homepage.layout = "page"` — **not** `"hero"`, `"profile"`, or
  `"background"`. Those three all render `Author.name` / `Site.Title` (a
  short label — "Ka Moamoa") instead of the homepage content's own title
  ("Hale Ao o Ka Moamoa"), and none of them are full-width. `page` is the
  only one of Blowfish's homepage widgets that shows the page's own title.
- `homepage.showRecent = false` — every homepage widget unconditionally
  injects a "Recent Articles" section if this is `true`. It was `true` at
  one point and nobody wanted that section on the homepage.

## Known open work (as of this writing — check `git log`/`git status` for current state)

- `content/research/education/index.md` has **unresolved git conflict
  markers** sitting in it (`<<<<<<<` / `=======` / `>>>>>>>`), from a
  collaborator's small link fix colliding with a much larger local rewrite.
  Needs a human to pick/merge content, not a mechanical resolution.
- Several research pages (`carbon`, `cyber-infrastructure`, `health/_index.md`,
  `intermittent`, `play`, `robots`, `team/_index.md`) have substantial
  uncommitted local rewrites (new sections, restructured content, new
  images in untracked `img/`/`media/` subdirectories) that are intentionally
  **not yet committed** pending review of the content itself.

If you're picking this up fresh after a while away: **run `git status`
first** and read any diffs before assuming the working tree matches what's
deployed. The gap between "what's on disk" and "what's committed" is exactly
what caused most of the debugging in this repo's history so far.
