# Smith+Nephew Windchill PLM — CI/CD Modernization Case Study

An interactive portfolio case study for the **Smith+Nephew Windchill PLM CI/CD modernization** — a before/after walk from the original 2022 Azure DevOps Classic Release Pipeline architecture to a 2026 modern stack with YAML multi-stage pipelines, Bicep infrastructure-as-code, Octopus Deploy release orchestration, and end-to-end observability.

**Repo:** https://github.com/shidokan/smith-nephew.git
**Will be live at:** https://shidokan.github.io/smith-nephew/

---

## What's in here

```
index.html                       — the case study (React app, self-contained)
assets/before-diagram.png        — original 2022 architecture diagram (Cognizant + Smith+Nephew)
assets/one-click-pipeline.jpg    — modern one-click CI/CD pattern reference
assets/after-diagram.jpg         — full 2026 target-state architecture diagram
README.md                        — this file
```

The HTML is fully self-contained — React 18 from CDN, Babel for in-browser JSX, Google Fonts (Manrope + JetBrains Mono). No build step.

---

## What the page covers

Eight sections walking the modernization arc:

1. **Hero with stat band** — 25 devs led at original delivery, 3 environments (Dev/QA/Prod), 0s production downtime per release, 12 pipeline stages
2. **Before / After / Side-by-side toggle** — interactive SVG diagrams with 14 clickable services. The before diagram uses coral/amber for "old" elements; the after uses teal/lavender with "NEW IN 2026" badges on additions
3. **What changed** — four columns: Preserved, Modernized, Added in 2026, Retired
4. **Eight capability cards** — pipeline-as-code, IaC, tenant-aware releases, runbooks, zero-downtime, observability, compliance audit trail, reusable templates
5. **The modernized pipeline** — 12-stage walkthrough from `git push` through `slot swap` and runbook ops, each tagged "new", "changed", or "kept"
6. **Six design decisions** — Octopus vs Classic Release, Octopus vs YAML-only, Bicep vs Terraform, slot swaps vs containers, Katalon vs Playwright, and how this maps to the "one-click" requirement in the JD
7. **Tech stack before/after table** — every component with what changed and why
8. **Reference diagrams** — the four uploaded architecture artifacts
9. **About** — context, the "modernize what's broken, preserve what works" principle, and the B2B SaaS transfer pattern

---

## Strategic positioning

This case study was deliberately built to support a job application for the **Ripple / GTreasury Staff Cloud Infrastructure Engineer role** (Chicago, April 2026, reporting to Director of Technical Operations). The JD specifies:

- **Deep Terraform expertise** with module development at scale — addressed via the Bicep-vs-Terraform decision card, which positions Terraform as the multi-cloud choice
- **One-click / automated provisioning patterns** — the central thesis of the modernization narrative
- **B2B SaaS experience** — Smith+Nephew is a $6.1B FTSE 100 medical device manufacturer; the modernization patterns transfer to GTreasury's multi-tenant treasury platform
- **Octopus Deploy** (nice-to-have per hiring manager Rick) — featured throughout as the release orchestration layer
- **New Relic** (nice-to-have per Rick) — addressed via the Azure Monitor + Application Insights section, with notes on cross-cloud APM alternatives
- **Exceptional communication** — the entire case study is the artifact; it demonstrates the ability to explain architecture trade-offs clearly to multiple audiences
- **Leading platform evolution** — the before/after framing IS the leading-platform-evolution story

The "Why this matters for Ripple / GTreasury" callout in the gallery section makes the connection explicit.

---

## Visual identity

Distinct from the four other portfolio case studies:

- **Light theme** — clean white/off-white background, engineering documentation aesthetic (Linear/Stripe/JetBrains vibe)
- **Slate-blue ink** (#0F172A) — modern, professional, not navy
- **Electric teal accent** (#14B8A6) — primary highlight color, distinct from Azure-teal and emerald-green used elsewhere
- **Coral** (#F26A4F) — for "before" / "old" elements
- **Lavender** (#8B5CF6) — for "new in 2026" elements
- **Octopus green** (#2DAB7F) — homage to Octopus Deploy brand
- **Manrope** for display and body, **JetBrains Mono** for code

The result reads as a modern engineering documentation site — appropriate for the technical leadership audience this work targets.

---

## Deploying to GitHub Pages

```bash
cd path/to/your/local/smith-nephew/folder
git init
git add .
git commit -m "Initial commit: Smith+Nephew Windchill CI/CD modernization case study"
git branch -M main
git remote add origin https://github.com/shidokan/smith-nephew.git
git push -u origin main
```

Then enable Pages:

1. Go to the repo on GitHub → **Settings → Pages**
2. **Source:** Deploy from a branch
3. **Branch:** main · **Folder:** / (root)
4. **Save**

Live at `https://shidokan.github.io/smith-nephew/` within 60-90 seconds.

---

## Customizing content

All content is driven by JavaScript data blocks near the top of the `<script>` tag:

- **`SERVICES`** — 14 clickable architecture services across both before and after diagrams. Each has an `era` field ("before", "after", "both") and an optional `new: true` flag that drives the "NEW IN 2026" badge in the modal
- **`PIPELINE_STEPS`** — the 12-stage modern pipeline walkthrough
- **`CHANGES`** — four-column before/after change matrix (Preserved, Modernized, Added, Retired)
- **`DECISIONS`** — six design-decision cards with HTML support via `dangerouslySetInnerHTML` for `<strong>` tags
- **`CAPABILITIES`** — eight capability cards

Edit these to tune the narrative for a specific interview or as the platform evolves.

---

## Using this in an interview

A few practical notes:

- **The Before/After toggle is the conversation primer.** Open on the After view, walk through what changed, drop into the Before view if the interviewer asks "what did you have originally?"
- **The Side-by-side view is the cleanest visual for a screen-share interview** — both diagrams at once, easy to point at specific changes
- **The Decision cards are interview-question primers** — every "Why X over Y" card is designed to be a 60-second answer to a likely follow-up question
- **The Capability cards are the elevator pitch** — eight outcomes the modernization delivers, each in 2-3 sentences

If a hiring manager asks about Octopus Deploy specifically, the relevant Service modal has detailed talking points including Tenant deployments (the B2B SaaS killer feature), Runbooks (one-click ops), and the variable-management story.

If they ask about Terraform specifically, the Bicep modal explicitly addresses when to choose Terraform vs Bicep, with the multi-cloud trade-off front and center.

---

## Credit

Original Windchill PLM DevOps work led at CDW (engagement with Smith+Nephew) during March–November 2022. Architecture modernization analysis and this case study assembled in 2026.

— John Carlo Cueva, Principal Cloud Architect · Chicago
