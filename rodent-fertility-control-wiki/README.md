# Rodent Fertility Control Wiki

A private, shareable knowledge base summarizing what is known about **fertility control (contraception / sterilization) as a tool for managing rodent populations** — the agents, mechanisms, delivery systems, ecological theory, field evidence, and regulatory status.

This wiki is written in plain Markdown so it can be version-controlled with git and hosted privately.

---

## How this wiki is organized

```
rodent-fertility-control-wiki/
├── README.md                     ← you are here (setup + contribution guide)
├── Home.md                       ← landing page / table of contents
├── overview/                     ← what fertility control is and why it matters
│   ├── introduction.md           ★ seed article (fully written)
│   ├── why-fertility-control.md
│   └── glossary.md
├── agents/                       ← specific compounds & biologics
│   ├── contrapest-vcd-triptolide.md   ★ seed article (fully written)
│   ├── ep1-quinestrol-levonorgestrel.md
│   ├── diazacon.md
│   └── immunocontraception.md         ★ seed article (fully written)
├── mechanisms/                   ← how these agents act on reproduction
│   └── reproductive-targets.md
├── ecology-and-modelling/        ← population-level theory & simulation
│   └── population-dynamics.md         ★ seed article (fully written)
├── delivery/                     ← baiting, uptake, non-target exposure
│   └── baiting-and-delivery.md
├── regulation/                   ← EPA / national registration status
│   └── regulatory-status.md
├── evidence/                     ← captive + field trial results
│   └── field-trials.md
├── references/
│   └── bibliography.md           ← central citation list (keyed)
└── _templates/
    └── article-template.md       ← copy this to start a new page
```

Pages marked ★ are fully written seed articles. The rest are stubs with a
consistent structure, ready to expand.

---

## Setup: hosting a private, shareable Markdown wiki with git

You chose a **Markdown + git** approach. Here are three concrete ways to host it,
from lowest to highest effort. My recommendation for most cases is **Option A**
(~75% this is the best fit for a small, invite-only readership).

### Option A — Private git repo with built-in rendering (recommended)

1. Create a **private** repository on GitHub, GitLab, or a self-hosted forge.
2. Push this folder to it:
   ```bash
   cd rodent-fertility-control-wiki
   git init
   git add .
   git commit -m "Initial wiki"
   git branch -M main
   git remote add origin git@github.com:<you>/rodent-fertility-control-wiki.git
   git push -u origin main
   ```
3. **Share** by inviting collaborators (Settings → Collaborators) or, on GitLab,
   sharing to a private group. Readers browse the rendered Markdown directly in
   the web UI. Relative links between pages work out of the box.

Pros: free, private by default, version history, per-person access, zero build
step. Cons: readers need a platform account; no full-text search across pages
beyond the platform's built-in search.

### Option B — Static site (nicer reading + search), still private

Use a Markdown static-site generator, then put the built site behind auth.

- **MkDocs Material** (Python — fits your stack) is the path of least resistance:
  ```bash
  pip install mkdocs-material --break-system-packages
  mkdocs new .          # generates mkdocs.yml
  mkdocs serve          # live preview at http://127.0.0.1:8000
  mkdocs build          # outputs static site to ./site
  ```
  It gives you client-side full-text search, navigation, and dark mode. Point
  its `docs_dir` at the folders above (minor `mkdocs.yml` edit).
- **Host privately** via Cloudflare Access, Netlify password protection, GitHub
  Pages on a private repo (Enterprise), or an internal server behind VPN/SSO.

Pros: best reading experience, real search. Cons: a build step and an auth layer
to maintain.

### Option C — Import into a hosted wiki engine

If you'd rather not manage hosting, **Outline** or a private **Notion** workspace
can import Markdown and handle sharing/permissions for you. You lose git history
but gain WYSIWYG editing for non-technical contributors.

---

## Contribution conventions

- **One topic per file.** Keep pages focused; link liberally between them.
- **Start from the template.** Copy `_templates/article-template.md`.
- **Cite everything.** Every factual claim should trace to `references/bibliography.md`
  using a short key like `[Massei2024]`. Keep full citations centralized so they
  don't drift.
- **Flag confidence.** Where evidence is thin or contested, say so inline
  (e.g. "efficacy at landscape scale is unproven as of 2024 [JacobLinnert2022]").
- **Relative links** between pages, resolved from the current file's folder — e.g.
  from a page in `overview/`, link to ContraPest as
  `[ContraPest](../agents/contrapest-vcd-triptolide.md)`; from `Home.md` at the root,
  it's `[ContraPest](agents/contrapest-vcd-triptolide.md)`. This keeps links working
  in both git-hosted and static-site rendering.

---

## Status & scope note

This is a **starter scaffold**: four seed articles are fully drafted with
citations; the remaining pages are structured stubs. The content reflects the
literature as summarized in mid-2026 and should be checked against primary
sources before being relied on for operational or regulatory decisions.
