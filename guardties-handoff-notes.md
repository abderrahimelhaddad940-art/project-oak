# GuardTies — Handoff Notes for Claude Code

## What this is
A landing/sales page for an estate-planning document package, currently drafted under the placeholder name "EstateReady" (file: `guardties-draft.html`). Rebrand to **GuardTies** and build out into a complete site.

## Rebrand scope (confirmed)
Same product, same offer — just rename throughout:
- Brand name: EstateReady → GuardTies
- Logo icon, `<title>`, meta tags (og:title, og:description, twitter:*), nav logo, hero background watermark text, all body copy references, footer brand
- Keep: 57 documents, $499 flat price, "download in 2 hours" delivery promise, 30-day guarantee, all section content (Why It Matters, Myths, How It Works, What You Receive, Comparison, Who It's For, Pricing, FAQs, Reviews, Close, Founder strip, Footer) — unless the user changes these later

## Repo / deployment plan (decided in prior chat, not yet executed)
- **GitHub repo name:** `project-oak` (deliberately not matching the brand name, for privacy since repo will be public)
- **Hosting:** GitHub Pages, custom domain `guardties.com`
- Repo should be created empty (no README/gitignore) on GitHub, public visibility (required for free Pages)
- A previously-issued fine-grained PAT was shared in chat but should be **revoked** (github.com/settings/tokens) since deployment is moving to Claude Code running locally with the user's own git credentials — no token handoff needed for that flow
- Once pushed: enable Pages in repo Settings → Pages, set custom domain to `guardties.com`, add a `CNAME` file to the repo root containing `guardties.com`
- DNS at the domain registrar will need: an `A` record (or four) pointing at GitHub Pages' IPs (185.199.108.153, .109.153, .110.153, .111.153), plus optionally a `CNAME` for `www` → `<username>.github.io`

## Suggested next steps in Claude Code
1. `git init` in the `project-oak` local folder, add the rebranded `index.html` (start from `guardties-draft.html`)
2. Do the EstateReady → GuardTies find/replace pass, plus any copy the user wants adjusted
3. Consider splitting into a few pages if the user wants (Terms, Privacy) — draft only has the single landing page currently
4. `git remote add origin`, push to `project-oak` on GitHub
5. Add `CNAME` file, enable Pages, walk user through DNS records
