# SEO Cartograph — SEO MCP Server + Free SEO Skills for Claude

**The SEO MCP server that runs on _your_ real data.** Connect Claude (or any MCP client)
to SEO Cartograph and let your AI read your crawl, Google Search Console, GA4, keyword
positions, semantic clusters and internal-link map — then act on them. Ships with a suite
of **SEO skills for Claude**, including free ones that work without an account.

> One install: an **MCP SEO server** (OAuth) **+ SEO skills**. The intelligence is paid by
> your Claude subscription — no per-token billing on our side.

**Keywords:** MCP SEO · SEO MCP server · MCP for SEO · Claude SEO · free SEO skills ·
Claude Code SEO · Search Console MCP · rank tracking · internal linking · content brief ·
technical SEO audit · SEO reporting.

---

## Install

```
/plugin marketplace add tom-ned/seo-cartograph-mcp
/plugin install seo-cartograph
```

The first time an SEO Cartograph tool runs, Claude opens an OAuth screen: you sign in with
your app.tnedjar.com account, and access stays **read-only** — the AI proposes, you approve
inside the cockpit. The free skills below work even without an account.

---

## The skills — what does what

### 🆓 Free SEO skills (no account required)

| Skill | What it does |
|---|---|
| **`audit-express-seo`** | Audits any page in minutes against a strict grid (title/meta/Hn/schema/images/links) and returns a scored verdict with **5 fixes written ready to paste**. |
| **`landing-page-seo`** | Builds a complete SEO landing page — structure, copywriting, title/meta, JSON-LD schema, internal-link plan — tailored to your **tech stack**: static HTML, WordPress, Next/Nuxt/Astro, or Webflow/Wix/Squarespace. Richer when the MCP is connected (real Search Console data). |
| **`schema-markup`** | Detects, validates and generates **JSON-LD structured data** (LocalBusiness, Product, Article, FAQPage, BreadcrumbList, Service) ready to paste — with a guardrail against inventing ratings or facts. |

### 🔑 Account skills (SEO Cartograph MCP connected)

| Skill | What it does |
|---|---|
| **`audit-technique`** | Full **technical SEO audit** on your real crawl — errors sorted **systemic vs isolated** (fix the template once, not 100 pages), prioritized by impact, delivered as a readable report. |
| **`opportunites-seo`** | Surfaces the **top SEO opportunities by return-on-effort** from your real Search Console data: positions 4-10, page-2 keywords, low-CTR pages, cannibalizations, legitimate gaps. |
| **`brief-de-contenu`** | Writes a **content brief** ready for a writer, calibrated on the live SERP and real Search Console lexicon: target query, structure, differentiating angle, questions to cover, internal-link plan. |
| **`verdict-de-page`** | For a single URL, a decisive verdict on evidence: **keep / refresh / merge / kill** — using its real traffic, positions, crawl health and role in the cluster. |
| **`chantier-maillage`** | Runs a guided **internal-linking** project on the real link map — justified link proposals (source, target, anchor, reason) sent to the cockpit for your validation. |
| **`calendrier-editorial`** | Builds an **SEO editorial calendar** — what to publish, in what order, and when — from opportunities, cluster gaps and **Search Console seasonality** (ship the Christmas piece in October). |
| **`bilan-seo-mensuel`** | The short **monthly SEO report**: GSC, GA4, positions, SERP moves — and the 3 actions for next month. |
| **`rapport-client`** | The full **white-label SEO client report**: executive summary, performance, positions, technical health, competitors, roadmap — as markdown or print-ready HTML/PDF. |

---

## What the MCP server exposes

~30 read-only tools across the SEO cockpit: crawl (overview, pages, issues, audit,
clusters), **Google Search Console** queries and history, **GA4** analytics, **live SERP**
(serper.dev) and rank tracking, semantic clusters, and the internal-link map — plus
propose-only actions (internal links, on-page fixes) that land in the cockpit for human
validation.

- Free plan: crawl, audit, editor, clusters.
- Pro / Agency plans: Search Console, live SERP, positions, analytics, internal-linking
  tools — with a monthly **SERP-credit** allowance (cached lookups are free).

## The model

- **Your data stays yours** — the MCP reads your account via OAuth, scoped to your
  organization, revocable in one click. Read-only: the AI proposes, you validate.
- **The AI is paid by your Claude subscription** — no token meter on our side.
- **Real data, not estimates** — every skill runs on your actual crawl, Search Console and
  positions, not third-party guesses.

## Languages

Deliverables default to **French** (Swiss market) and support **English** on request. The
lexicon and SERP data always follow the market you target (locale `fr-ch`, `de-ch`,
`en-us`, …).

## Links

- Product & MCP page: https://tnedjar.com/fr-fr/seo-cartograph/mcp/
- App / sign-in: https://app.tnedjar.com

---

_Maintained from the `claude-plugin/` folder of the private cockpit repo; published here as
the installable marketplace._
