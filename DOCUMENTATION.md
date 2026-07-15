# Abdus Sameer — IT & Semiconductor Equity Research
## Website Documentation

**Version:** 1.0
**Type:** Static multi-page website (HTML / CSS / vanilla JS — no build step, no framework, no backend)
**Owner:** Abdus Sameer
**Last updated:** July 2026

---

## 1. Goal & Purpose

### 1.1 What this site is
A personal-branding and publishing platform for independent equity research focused on the **IT and semiconductor value chain** — product-led software companies, IT services firms, AI platforms, and the chipmakers/equipment makers underneath them (e.g. Nvidia, ASML, TSMC).

### 1.2 Why it exists (the underlying business goal)
Two goals, pursued simultaneously:
1. **Credibility** — build a public, named, dated body of research that demonstrates real analytical judgment, in order to support career opportunities in finance (senior/expert-level roles).
2. **Audience** — attract and retain readers (retail investors and finance students) who return regularly because the analysis is trustworthy, consistent, and explains *why something matters*, not just *what happened*.

### 1.3 What makes this different from existing platforms
Existing platforms (Screener, Groww, Moneycontrol, Yahoo Finance, Bloomberg, TradingView) either:
- give raw data with no interpretation, or
- give headlines with no depth, or
- sit behind paywalls (sell-side research).

This site's differentiation is:
- **A named person's judgment**, not an anonymous aggregator.
- **One repeatable analytical framework**, applied visibly every time (see §6.4 — Methodology).
- **A narrow, defensible niche** (IT + Semiconductors) instead of trying to cover the whole market.
- **Editorial, minimal design** — explicitly *not* styled like a trading dashboard. No tickers, no flashing widgets, no ad-like clutter.

---

## 2. Target Audience

| Audience | What they come for |
|---|---|
| Retail / individual investors | Plain-English analysis they can act on, without needing a finance degree |
| Finance students | A transparent, repeatable framework to learn how real sector analysis is built |
| Employers / recruiters / industry contacts | Proof of expert-level judgment via a public, dated track record |

---

## 3. Brand Identity

| Element | Decision |
|---|---|
| Name on site | Abdus Sameer |
| Tagline | "Reading the tech stack behind the stock price." |
| Sector focus | IT & Semiconductors — Product companies, Services companies, AI companies, Semiconductors/Chips |
| Voice | Direct, plain-English, opinionated but evidence-based. Admits uncertainty and past misses. |
| Compliance stance | Explicitly **not** a SEBI-registered investment adviser (stated in every footer). Site is framed as independent research/education, not investment advice. |
| Visual identity ("wafer grid" system) | Graphite/off-white/teal palette + IBM Plex Sans (body/display) + IBM Plex Mono (data, labels, tickers) — chosen because IBM Plex is itself a technology-company typeface, reinforcing the IT/semiconductor subject matter. Signature visual motif: a 4-tile "wafer/die" coverage grid on the homepage. |

---

## 4. Site Architecture (Sitemap)

```
/
├── index.html            Homepage — brand hub, coverage map, teasers
├── news.html              "Technology Intelligence" — the news/alerts page
├── reports.html            Equity Research Reports — full report index
├── sample-report.html      Full example equity research report (FSA template)
└── style.css                Single shared stylesheet used by all 4 pages
```

**Navigation is consistent across all pages:**
`Coverage → Technology Intelligence → Reports → Methodology → About → [Get Alerts CTA]`

- `Coverage`, `Methodology`, `About`, `Get Alerts` are **anchor links** that only exist on `index.html` (e.g. `index.html#coverage`). From any other page, these links jump back to the homepage section.
- `Technology Intelligence` and `Reports` are **standalone pages** (`news.html`, `reports.html`).

---

## 5. Page-by-Page Breakdown

### 5.1 `index.html` — Homepage
Purpose: brand hub and entry point. Establishes who Abdus Sameer is, what he covers, and routes visitors to the two content engines (News/Intelligence and Reports).

| Section | id/class | Purpose |
|---|---|---|
| Hero | `.hero` | Headline + value prop + scrolling ticker strip (NVDA, ASML, TCS, etc.) |
| About | `#about` | Author bio, sector-focus badges, compliance line |
| Coverage Map | `#coverage` (`.wafer` / `.wafer-grid`) | Signature 4-tile "die" grid: Product / Services / AI / Semiconductors — the site's core navigation-by-sector concept |
| News Feed (teaser) | `#feed` (`.feed-section`) | Preview of 4 alert items, links out to `news.html` |
| Reports (teaser) | `#reports` | Preview of 3 report cards, one linking to the full `sample-report.html` |
| Methodology | `#methodology` | The 5-step process applied to every report (see §6.4) |
| Alerts signup | `#alerts` | Email capture (front-end only — **not wired to a real email service**, see §9.2) |
| Archive / GitHub | `#archive` | Placeholder card linking to a GitHub profile for data/model archives |
| Footer | — | Nav links, SEBI-style disclaimer |

### 5.2 `news.html` — "Technology Intelligence"
Purpose: **not a raw news feed.** Deliberately designed to reduce information overload rather than add to it — every item is filtered, explained, and rated for confidence/impact rather than just reported. Rebuilt from an original "News Alerts" concept into this format per an explicit design brief requesting an "AI research analyst" feel, editorial in style (Stratechery/Stripe/Apple-like), **not** a financial dashboard (Bloomberg/Yahoo Finance/TradingView-like).

| # | Section | Purpose |
|---|---|---|
| — | Hero | "Understanding what matters, not reading everything" + trust markers (Verified / Cross-referenced / Evidence-based / Updated continuously) |
| 1 | Today's Five Most Important Developments | Editorial list (not cards) of 5 stories, each with: headline, AI-style summary, impact rating, confidence indicator, affected companies, link to full analysis |
| 2 | Technology Timeline | Chronological feed of the day's events, each with a one-line "why it matters" |
| 3 | Sector Intelligence | 6 sector cards (AI, Semiconductors, Cloud, Cybersecurity, Enterprise Software, IT Services) — trend, key companies, link |
| 4 | AI Explained | One fully unpacked example story broken into: What happened / Why / Financial impact / Tech impact / Who benefits / Who loses / Long-term implications / Key risks / Confidence & evidence |
| 5 | Technology Connections | Interactive horizontal chain diagram (OpenAI → Azure → Nvidia → TSMC → ASML → Applied Materials) — **functional**: clicking a node reveals how it connects to the rest of the stack (vanilla JS, no backend) |
| 6 | Signal vs Noise | Two-column list: what gets filtered out (rumours, clickbait, price speculation, hype) vs what qualifies (earnings, deals, leadership, regulation, M&A, supply chain, breakthroughs) |
| 7 | What Changed Since Yesterday | Short one-line bullet list of daily deltas |
| 8 | Deep Intelligence | Long-form article index (4 items) |
| 9 | Ask AI | **Demo only** — input box + 4 suggested prompts that return pre-written canned answers. Clearly labeled "Demo response — connect an AI backend for live answers." Not connected to any real model. |
| 10 | Methodology | 4 pillars (Cross-referenced / Fact-checked / AI-assisted / Human-reviewed) + confidence-level legend (80–100% / 50–79% / <50%) |

### 5.3 `reports.html` — Equity Research Reports
Purpose: full, filterable index of research reports.

- Filter tabs: All / Product / Services / AI / Silicon (client-side JS filter by `data-sector` attribute — no backend)
- Report cards show: rating chip (Buy/Hold/Watch), sector tag, title, one-line teaser, read time
- One card ("Persistent Systems") links to the full worked example at `sample-report.html`; the rest currently link back to `reports.html` itself as placeholders pending real write-ups
- Bottom callout links to the sample report as "see the FSA framework applied in full"

### 5.4 `sample-report.html` — Full worked example report
Purpose: **proof of analytical depth.** This is the single most important credibility page on the site — it demonstrates the actual Financial Statement Analysis (FSA) framework in practice.

⚠️ **Clearly banner-marked at the top:** *"SAMPLE REPORT — this is a template to show the framework. Figures below are illustrative placeholders, not real financials."* This was a deliberate choice — the report is about a real, named company (Persistent Systems), so fabricated-but-unlabeled figures would be misleading. The banner and footer disclaimer both restate this.

Report structure (this is the reusable template for all future reports):
1. Business overview
2. Revenue & growth quality (with a real FSA-style data table)
3. Margin & profitability analysis (data table)
4. Balance sheet & cash flow
5. Valuation
6. Verdict (rating + reasoning)

Also includes a "risk callout" component (the one risk the market isn't pricing in) and an author strip (name, role, compliance line).

---

## 6. Shared Design System (`style.css`)

### 6.1 Color tokens
```css
--bg:        #F1F3EE   /* page background — soft warm-gray, not pure white/cream */
--bg-alt:    #E7EAE1   /* alternating section background */
--surface:   #FFFFFF   /* card/surface fills */
--ink:       #10161A   /* primary text */
--ink-soft:  #4B565C   /* secondary text */
--ink-faint: #7B848A   /* tertiary/meta text */
--line / --line-strong  /* hairline borders, two weights */
--teal / --teal-deep / --teal-tint   /* primary accent — "circuit" teal */
--gold:      #D9A441   /* secondary accent — used sparingly (highlights, demo tags) */
--brick:     #B4483A   /* negative/risk accent */
```

### 6.2 Typography
- **IBM Plex Sans** — body text, headings
- **IBM Plex Mono** — data, tickers, labels, kickers, timestamps
- Loaded via Google Fonts CDN in every page's `<head>`

### 6.3 Layout system
- `.wrap` — max-width 1180px content container, 28px side padding
- `.dotgrid` — subtle radial-dot background texture used on hero/methodology sections
- Standard section rhythm: `section { padding: 86px 0; }`
- Responsive breakpoints: 900px (tablet), 760/700/620/560px (mobile), handled via `@media` queries throughout

### 6.4 The 5-step Methodology (used across the whole brand)
1. Filter the noise
2. Read past the press release
3. Map the numbers to the narrative
4. Flag the risk nobody's pricing in
5. Take a position, publicly

This exact 5-step list appears on the homepage (`#methodology`) and is the implied backbone of every report and every "Today's Five" item on the Technology Intelligence page.

### 6.5 Component inventory (reusable classes)
| Component | Classes | Used on |
|---|---|---|
| Nav bar | `.site`, `.navbar`, `.brand`, `.links`, `.nav-cta`, `.nav-toggle` | All pages |
| Buttons | `.btn`, `.btn-primary`, `.btn-ghost` | All pages |
| Ticker marquee | `.ticker`, `.ticker-track` | Homepage |
| Wafer/die coverage grid | `.wafer-grid`, `.die` | Homepage |
| Feed/alert list (legacy homepage teaser) | `.feed-list`, `.alert-item`, `.sector-chip` | Homepage |
| Report cards | `.report-card`, `.tag`, `.report-meta` | Homepage, Reports page |
| Filter tabs | `.filter-bar`, `.filter-tab` | News page, Reports page |
| Rating/impact indicators | `.rating-chip`, `.impact-tag`, `.trend` | Reports page, News page |
| FSA data tables | `.fsa-table` | Sample report |
| Thesis / risk / verdict callouts | `.thesis-box`, `.risk-callout`, `.verdict-box` | Sample report |
| Editorial list (no card-box styling) | `.dev-list`, `.dev-card`, `.deep-list`, `.deep-item` | News page |
| Sector intelligence tiles | `.sector-grid`, `.sector-card` | News page |
| Explainer template | `.explain-card`, `.explain-grid`, `.explain-block` | News page |
| Connections chain (interactive) | `.connections-chain`, `.chain-node`, `.chain-detail` | News page |
| Signal vs Noise columns | `.criteria-section`, `.criteria-grid`, `.criteria-col` | News page |
| Ask AI demo | `.ask-box`, `.ask-input-row`, `.ask-chip`, `.ask-response` | News page |
| Methodology pillars | `.method-grid`, `.method-pillar`, `.confidence-legend` | News page |

> **Design intent note:** components on the News/"Technology Intelligence" page were deliberately built *without* card backgrounds, colored pill badges, or progress-bar widgets — an earlier draft looked too much like a financial dashboard (Bloomberg/TradingView-style) and was revised to a flush, hairline-divided, editorial list style instead, per explicit design direction to feel like Stratechery/Stripe/Apple rather than a trading terminal.

---

## 7. Content Status — What's Real vs Placeholder

This is the most important section to check before publishing. **Nothing on this site currently contains real, sourced financial data or real news.** Everything is illustrative, written to demonstrate format and voice.

| Content | Status | Action needed before going live |
|---|---|---|
| Author bio (`index.html #about`) | Real name, honest/generic bio (no fabricated credentials) | Review wording, add real photo if desired (currently a monogram avatar) |
| Report cards (homepage, `reports.html`) | Placeholder titles, marked "Sample/Draft" | Replace with real, published reports as they're written |
| `sample-report.html` | Real company name (Persistent Systems), **fabricated illustrative figures** | Clearly banner-marked as a template — replace all figures with sourced data before treating as a real report, or swap to a fully fictional company name |
| News/alert items (`index.html`, `news.html`) | Entirely illustrative, written to demonstrate the "Signal vs Noise" filter | Replace with real, sourced items once the research/agentic pipeline is running |
| "Today's Five", Timeline, Sector Intelligence, "What Changed", Deep Intelligence (`news.html`) | Entirely illustrative | Same — placeholder content demonstrating format only |
| Ask AI (`news.html`) | **Non-functional demo.** 4 hard-coded canned answers, no real model connection | Requires a real backend integration — see §9.3 |
| Alerts signup form (`index.html`, `news.html`) | **Front-end only.** Submitting just changes button text to "Added ✓"; no email is actually captured | Needs wiring to a real email service — see §9.2 |
| GitHub links | Placeholder URL (`https://github.com/`) | Replace with real GitHub handle |
| Disclaimer / SEBI language | Real, intentional, present in every footer | Review with a professional if planning to formally publish investment-adjacent content in India |

---

## 8. File Structure Reference

```
/mnt/user-data/outputs/
├── index.html          16 KB   Homepage
├── news.html            28 KB   Technology Intelligence page
├── reports.html          9 KB   Reports index
├── sample-report.html   10 KB   Worked example report
└── style.css             31 KB   Shared stylesheet (all pages import this)
```

**Dependencies:** none beyond a browser and an internet connection for Google Fonts (IBM Plex Sans/Mono, loaded via `<link>` in each `<head>`). No npm packages, no build tools, no server required — this is a plain static site that can be opened directly from disk or deployed to any static host (GitHub Pages, Netlify, Vercel, S3, etc.).

---

## 9. Technical Notes & Known Limitations

### 9.1 No backend
This is a fully static site. There is no server, no database, and no API. All "interactivity" (filter tabs, the connections chain, Ask AI demo, mobile nav toggle) is handled with small inline vanilla-JS blocks per page — no external JS framework.

### 9.2 Alerts signup is not functional
The email form on `index.html` and `news.html` only performs a cosmetic `preventDefault()` and changes the button label. **No email is sent or stored anywhere.** To make this real, it needs to be pointed at an email service provider (e.g. Mailchimp, ConvertKit, Buttondown) via their form-submission endpoint or API.

### 9.3 Ask AI is a static demo
The Ask AI box on `news.html` only recognizes 4 hard-coded prompts and returns pre-written text, explicitly labeled as a demo. To make it live, it would need a backend endpoint calling a real LLM (e.g. the Claude API) with appropriate context/grounding — this is a genuine backend build, not something achievable in a static HTML file alone.

### 9.4 No CMS
All content is hand-written directly into HTML. There is currently no content-management layer — adding a new report or alert means manually editing the relevant `.html` file. If publishing volume increases, this will become the main bottleneck; worth considering a static-site generator (e.g. Eleventy, Astro) or a headless CMS at that point.

### 9.5 Browser support
Uses modern CSS (`:root` custom properties, `backdrop-filter`, CSS Grid, `clamp()`). Works in all current evergreen browsers (Chrome, Safari, Firefox, Edge). No fallback provided for very old browsers (not a practical concern for this audience).

### 9.6 QA history (for transparency)
During development, `style.css` briefly contained a duplicated/orphaned draft of the Technology Intelligence component styles, which caused two real layout bugs (a broken grid layout on the "Today's Five" cards, and a stray border on the Timeline section). This was diagnosed by cross-referencing every CSS class against actual HTML usage, and resolved by deleting the ~150 lines of dead/conflicting CSS. A full duplicate-selector and orphaned-class audit was run afterward and confirmed clean — see §6.5 note for the resulting design.

---

## 10. Roadmap (stated intentions, not yet built)

1. **Agentic AI research pipeline** — the long-term intention is to use AI agents to help gather, cross-reference, and draft News/Intelligence items and report data, with a human (Abdus Sameer) reviewing before publishing (this is already reflected in the "AI-assisted, Human-reviewed" Methodology section on `news.html`).
2. **GitHub archive** — publishing underlying data pulls, models, and the agentic workflows themselves in a public GitHub repo, linked from the Archive section.
3. **Live Ask AI** — replacing the static demo with a real backend-connected assistant grounded in the site's own published research.
4. **Functional alerts** — wiring the email capture form to a real ESP.
5. **Growing the report library** — the single highest-priority content task, since credibility compounds only through a real, dated track record (see §1.2).

---

## 11. Quick Reference — "Why does this page exist?" (one-line summary per page)

- **`index.html`** — "Who is Abdus Sameer and what does he cover?"
- **`news.html`** — "What happened today, and why does it actually matter?"
- **`reports.html`** — "Show me all the deep research."
- **`sample-report.html`** — "Prove you can actually do the analysis."
