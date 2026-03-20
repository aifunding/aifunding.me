<h1 align="center">
  <br/>
  <a href="https://aifunding.me">
    <img src="https://aifunding.me/logo-header.png" alt="AI Funding" width="80" height="80" />
  </a>
  <br/>
  AI Funding
  <br/>
</h1>

<h4 align="center">Track every AI startup funding round — as it happens.</h4>

<p align="center">
  <a href="https://aifunding.me"><img src="https://img.shields.io/badge/site-aifunding.me-0EA5E9?style=flat-square" alt="Website" /></a>
  <a href="https://aifunding.me/deals"><img src="https://img.shields.io/badge/deals-148%2B-10B981?style=flat-square" alt="Deals" /></a>
  <a href="https://aifunding.me/companies"><img src="https://img.shields.io/badge/companies-132%2B-8B5CF6?style=flat-square" alt="Companies" /></a>
  <a href="https://aifunding.me/top-ai-startups"><img src="https://img.shields.io/badge/funding-$55.8B%2B-F59E0B?style=flat-square" alt="Funding" /></a>
  <a href="https://twitter.com/aifunding"><img src="https://img.shields.io/badge/twitter-@aifunding-1DA1F2?style=flat-square&logo=twitter&logoColor=white" alt="Twitter" /></a>
</p>

<p align="center">
  <a href="#features">Features</a> |
  <a href="#data-pipeline">Data Pipeline</a> |
  <a href="#tech-stack">Tech Stack</a> |
  <a href="#api--data-access">API</a> |
  <a href="#newsletter">Newsletter</a>
</p>

---

## About

**AI Funding** ([aifunding.me](https://aifunding.me)) is the most comprehensive AI venture funding database. We automatically collect, verify, enrich, and publish every AI startup funding round — from pre-seed to mega-rounds.

Every deal auto-enriches **6+ page types**: company profiles with funding timelines, investor portfolios, sector breakdowns, geographic analysis, leaderboards, and in-depth research insights.

### Key Numbers

| Metric | Value |
|---|---|
| Companies tracked | 132+ |
| Funding rounds | 148+ |
| Active investors | 48+ |
| Total funding tracked | $55.8B+ |
| Static pages generated | 430+ |
| Data freshness | Updated daily (automated) |

## Features

### For Investors & Analysts
- **Live Deals Feed** — every AI funding round, grouped by week, filterable by sector and stage
- **Company Profiles** — full funding history with source links, investor details, cumulative totals, and valuations
- **Top AI Startups Leaderboard** — ranked by total capital raised with valuation data
- **Sector Analysis** — 16 canonical AI sectors with company counts and funding totals
- **Data Explorer** — filter, sort, and analyze the complete dataset

### For AI Assistants
- **[llms.txt](https://aifunding.me/llms.txt)** — concise summary optimized for AI assistant discovery
- **[llms-full.txt](https://aifunding.me/llms-full.txt)** — comprehensive dataset reference
- **JSON-LD** — structured data on every page (21+ schema types: Organization, Article, Dataset, FAQ, ItemList, etc.)

### For Developers
- **Public RSS Feed** — machine-readable deal updates
- **Embeddable Widget** — drop AI funding data into any site
- **Open Data** — all funding data stored as JSON, validated with Zod schemas

## Data Pipeline

AI Funding runs a fully autonomous data pipeline — zero manual editorial work required.

```
RSS Feeds (4x daily)
    |
    v
collect-deals.ts         Collect from 10+ RSS sources
    |
    v
ingest-deals.ts          Extract company, amount, stage, investors
    |                    3-layer dedup (collection, ingest, build-time)
    v
auto-fix-data.ts         Quality fixes (no LLM needed):
    |                    - Discover website URLs (favicon verification)
    |                    - Estimate valuations (stage-based dilution model)
    |                    - Generate descriptions from round context
    |                    - Remove duplicates and orphans
    |                    - Validate source links (replace 404s)
    |                    - Detect light favicons for dark-bg rendering
    v
enrich-companies.ts      LLM enrichment (OpenAI -> Gemini -> regex):
    |                    - Professional descriptions and overviews
    |                    - Correct sectors and locations
    |                    - Prioritizes landing page companies
    v
Build & Deploy           Next.js static generation -> Cloudflare Pages
    |
    v
430+ pages live          Company profiles, leaderboard, sectors, insights
```

### Quality Assurance
- **3-layer dedup** prevents duplicate deals (collection-time, ingest-time, build-time)
- **Quality gate** prevents publishing companies with template/stub data
- **Source link validation** ensures every funding round links to a verifiable article
- **Favicon brightness scanner** auto-detects white-on-white logos
- **Weekly data quality audit** with auto-fix and GitHub issue creation

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 15 + React 19 |
| Language | TypeScript |
| Styling | Tailwind CSS v4 + shadcn/ui |
| Data | JSON files + Zod validation |
| Deployment | Cloudflare Pages |
| Email | Resend (contact form) + Buttondown (newsletter) |
| CI/CD | 8 GitHub Actions workflows |
| LLM | OpenAI GPT-5 Mini + Google Gemini 3 Flash |

## API & Data Access

### For AI Assistants
```
GET https://aifunding.me/llms.txt
GET https://aifunding.me/llms-full.txt
```

### Structured Data
Every page includes JSON-LD markup with schema.org types. Use the [Google Structured Data Tool](https://search.google.com/test/rich-results) to inspect any page.

### Embeddable Widget
```html
<iframe src="https://aifunding.me/embed" width="400" height="300"></iframe>
```

## Newsletter

Weekly AI funding roundup — top deals, sector trends, and market intelligence.

**[Subscribe at aifunding.me](https://aifunding.me/#newsletter)**

## Contact

- **Email**: [support@aifunding.me](mailto:support@aifunding.me)
- **Twitter**: [@aifunding](https://twitter.com/aifunding)
- **Contact Form**: [aifunding.me/contact](https://aifunding.me/contact)

## License

All rights reserved. The data and content on aifunding.me is proprietary. The source code powering the data pipeline is not open source.

---

<p align="center">
  <a href="https://aifunding.me">
    <img src="https://img.shields.io/badge/Visit-aifunding.me-0EA5E9?style=for-the-badge" alt="Visit AI Funding" />
  </a>
</p>
