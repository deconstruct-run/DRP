# deconstruct.run // FIELD REPORT — The Apparatus

Self-contained preview build of the deconstruct.run magazine site. The entire
site is one file, `index.html`. No build step, no server, no dependencies to
install. Open it locally by double-clicking, or host it live on GitHub Pages
using the steps below.

The site uses hash routing (`#/route`), so every page works on a static host
with no server configuration. Deep links like `.../#/insight-04` load directly.

---

## Put it live on GitHub Pages

### Path A — browser only, no git (fastest)

1. Go to https://github.com/new and create a repository. Name it anything, for
   example `deconstruct-run-preview`. Set it to **Public** (GitHub Pages is free
   for public repos). Do not add a README; the repo can start empty.
2. On the new repo page, click **uploading an existing file**. Drag in both
   `index.html` and `.nojekyll` from this folder. Commit directly to the
   `main` branch.
3. Open **Settings → Pages**. Under **Build and deployment**, set **Source** to
   **Deploy from a branch**, choose branch **main** and folder **/ (root)**,
   then **Save**.
4. Wait about one minute, then reload the Pages settings screen. It shows the
   live URL, in the form `https://<your-username>.github.io/<repo-name>/`.
   That link is shareable on any device.

### Path B — git command line

```bash
# inside this folder
git init
git add index.html .nojekyll README.md
git commit -m "deconstruct.run preview build"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then follow step 3 above (Settings → Pages → Deploy from a branch → main →
/root).

---

## Updating the site

Replace `index.html` with a newer build and commit again (drag-and-drop a new
`index.html` over the old one in the web UI, or `git add`/`commit`/`push`).
GitHub Pages redeploys within a minute or two. A hard refresh (Cmd/Ctrl+Shift+R)
clears any cached copy on your device.

## The `.nojekyll` file

GitHub Pages runs Jekyll by default, which can skip files it does not
understand. The empty `.nojekyll` file turns Jekyll off so the site is served
exactly as-is. Keep it in the repo root.

## Custom domain (later)

When the launch domain is ready, add a `CNAME` file to the repo root containing
just the domain (for example `deconstruct.run`), then set that domain under
**Settings → Pages → Custom domain** and point the DNS at GitHub. Not needed for
device testing — the `github.io` URL is enough to share and review.

## Notes for reviewers

The one external dependency is the webfont load from `fonts.googleapis.com`,
which resolves automatically on any connected device. Everything else —
imagery, styles, scripts, the full report, the WIRE / INSIGHT / SYNTH module,
the glossary, and the sources — is embedded in the single file. Video and
motion elements are still in production and are not part of this preview.
