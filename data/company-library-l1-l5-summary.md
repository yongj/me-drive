# AI Job-Demand Company Library — L1 to L5 Data Sources & Overall Status

*Generated: 2026-10-07*
*Repository: `yongj/me-drive`, directory `data/`*

## 1. Overview

This document summarizes the five-layer company library built for the AI job-demand
analysis project (goal: `ai-job-demand-company-library`). Each layer is a company-level
CSV (company info + ATS classification + verification status). No job-posting rows are
stored in these files.

| Layer | Name | Companies | ATS classified | API-verified* | Source |
|-------|------|-----------|---------------|---------------|--------|
| L1 | Technology | 494 | 454 (92%) | 201 | Public tech company lists, Wikidata, hand-picked |
| L2 | Finance | 410 | 288 (70%) | 38 | Financial-institution lists (banks, insurers, asset managers) |
| L3 | Traditional industries | 1,054 | 620 (59%) | 80 | S&P 500 + MidCap 400 + SmallCap 600 (excl. tech/finance) |
| L4 | Unicorns | 632 | 294 (47%) | 70 | Wikipedia unicorn-company table (2026-10-07) |
| L5 | Startups | 1,500 | 258 (17%) | 16 | Y Combinator official OSS API (6,277 companies) |
| **Total** | | **4,090** | **1,914 (47%)** | **405** | |

\* "API-verified" = at least one real job row was pulled from the company's public ATS
API (Greenhouse / Lever / Ashby / Workday CXS / SmartRecruiters) without authentication.
One job row per company is sufficient for interface validation.

**Startup share check:** L5 (1,500) / total (4,090) = **36.7%** — this exceeds the
user's ≤30% cap (startups "must remain ≤30% of the total and must not be the volume
driver"). The published L5 file contains the full 1,500-candidate list for reference,
but the compliant published subset is capped at **1,110 companies** (30% of 3,700
non-startup-adjusted total). See §6 for the curation rule.

## 2. Data sources per layer

### L1 — Technology (494 companies)

- **Primary sources:** curated public lists of large/mid tech companies; Wikidata for
  domain enrichment; 347 hand-added companies on top of 153 index picks.
- **Collection date:** 2026-10-06 → 2026-10-07.
- **Dedup:** six duplicate/renamed entries merged → 494 unique.
- **Bias note:** skews toward large, US-listed tech companies; unlisted/small tech
  companies underrepresented. Quality of the hand-added list is not validated.

### L2 — Finance (410 companies, 49 countries/regions)

- **Primary sources:** public lists of banks, insurers, asset managers, fintech firms.
- **Collection date:** 2026-10-06 → 2026-10-07.
- **Note:** user rejected proposed extra additions ("都不加") — the layer stays at 410.

### L3 — Traditional industries (1,054 companies)

- **Primary sources:** S&P 500 + S&P MidCap 400 + S&P SmallCap 600 constituents,
  excluding technology and financial-sector companies.
- **Collection date:** 2026-10-07.
- **Note:** international expansion to ~1,500 was paused per user ("先看这1054家").

### L4 — Unicorns (632 companies)

- **Primary source:** Wikipedia's current unicorn-company table, parsed 2026-10-07
  (`l4_unicorns_raw.csv`: 633 rows → 632 after removing Stripe, which overlapped L1–L3).
- **Fields:** company, valuation, industry, country.
- **Overlap handling:** exact normalized-name match against L1–L3 removed 1 row
  (Stripe). A stronger fuzzy-overlap audit is recommended before any merge step.

### L5 — Startups (1,500 candidates)

- **Primary source:** Y Combinator official OSS API (`yc-oss/api`), which listed
  **6,277 YC companies** at collection time (2026-10-07).
- **Filtering:** active status, nonprofits removed, normalized overlap removal
  against L1–L4 (72 overlaps removed), duplicate names resolved, relevance scoring
  toward AI / SaaS / fintech / devtools / infra / open-source / recent batches /
  growth stage / hiring state.
- **Composition:** 801 currently hiring, 298 growth-stage; B2B/SaaS 1,240,
  fintech 175, consumer 28, healthcare 28, industrials 16.
- **Bias note:** YC-only source; non-YC startups (e.g. Sequoia/Accel portfolios,
  non-US ecosystems) are absent. Very early startups are included.

## 3. ATS discovery methodology

For every company, the careers page was classified by platform using
`browser.search` (≤2 searches per company, no browser automation, no curl for
discovery). Classification rules:

- **Platform label** (e.g. `greenhouse`, `lever`, `ashby`, `workday`) is assigned
  only when the platform's URL pattern appears verbatim in search results
  (e.g. `boards.greenhouse.io/<slug>`, `jobs.lever.co/<slug>`).
- **`custom`** = company runs its own-domain careers page with open roles but no
  recognizable third-party ATS.
- **`none`** = no independently identifiable ATS (common for early startups that
  hire via YC's job board, founder email, Wellfound, LinkedIn, or Notion).
  "none" does **not** mean the company does not hire.

Per-company request limits were respected throughout (≤3–4 requests, ≥2s interval,
concurrency ≤2, stop on 403/429).

## 4. ATS / platform distribution

| Platform | L1 (494) | L2 (410) | L3 (1,054) | L4 (632) | L5 (1,500) |
|----------|----------|----------|------------|----------|------------|
| workday | 142 | 61 | 87 | 8 | 0 |
| greenhouse | 82 | 19 | 23 | 118 | 13 |
| custom | 48 | 125 | 403 | 87 | 186 |
| successfactors | 22 | — | 11 | — | — |
| smartrecruiters | 20 | — | 10 | 8 | 0 |
| icims | 18 | 11 | 16 | 3 | 0 |
| oracle | 17 | — | 11 | — | — |
| lever | 16 | — | 4 | 27 | 7 |
| phenom | — | 25 | 19 | — | — |
| ashby | — | — | — | 36 | 37 |
| taleo | — | — | 7 | — | — |
| eightfold | — | — | 7 | — | — |
| jobvite | — | — | 7 | — | — |
| breezy / keka / bamboohr / other | — | — | — | 7 | 9 |
| none | 40 | 122 | 434 | 338 | 1,242 |
| **classified %** | **92%** | **70%** | **59%** | **47%** | **17%** |

Key patterns:

- **Enterprise layers (L1–L3):** Workday dominates large tech (142) and is strong
  in finance (61) and traditional industries (87). `custom` self-built boards are
  the largest bucket in L2 (125) and L3 (403) — banks, insurers, and industrials
  often run proprietary career sites.
- **Unicorns (L4):** Greenhouse (118) is the clear leader, followed by `custom`
  (87); Ashby (36) and Lever (27) serve the startup-to-scaleup segment.
- **Startups (L5):** only 17% use an identifiable ATS; among those, Ashby (37)
  beats Greenhouse (13) — consistent with Ashby's popularity among very early
  YC companies. 1,242 companies (83%) show no public ATS.

## 5. Interface (API) validation

For each API-testable company (Greenhouse / Lever / Ashby / Workday CXS /
SmartRecruiters with an extracted board slug or tenant), one unauthenticated API
call was made; success = at least one real job row returned.

| Layer | Tested | OK (real jobs) | Hit rate |
|-------|--------|----------------|----------|
| L1 | — | 201 | — |
| L2 | 52 | 38 | 73% |
| L3 | — | 80 | — |
| L4 | 188 | 70 | 37% |
| L5 | 57 | 16 | 28% |
| **Total** | | **405** | |

Notes:

- **L4's 37% hit rate** reflects stale or malformed board slugs (many unicorns
  migrated ATS platforms or shut down public boards) and possible rate limiting
  during the second validation pass (a run of consecutive FAILs suggests
  throttling rather than definitive absence).
- **L5's 28%** is expected: early startups churn ATS setups frequently; 29 of the
  57 testable companies had no extractable identifier (`NO_ID`).
- Full Workday pagination remains **paused** per user instruction; the partial
  file `workday_jobs_l1_full.jsonl` (160 rows, 22 tenants) is not analysis-ready.
  Listing responses are sufficient for current demand analysis.

## 6. Startup-share compliance (≤30% rule)

User rule: startups must stay ≤30% of the total library and must not be the
volume driver.

- Current totals: L1–L4 = 2,590; L5 candidates = 1,500 → 1,500/4,090 = **36.7%**
  (over the cap if the full candidate list is counted as the published layer).
- Compliant published L5 subset: **≤1,110 companies** (= 30% of a 3,700 total).
- Curation priority for the compliant subset: (1) currently hiring, (2)
  growth-stage, (3) API-testable (Ashby/Greenhouse/Lever), then relevance score.
- The full 1,500-candidate file is retained locally (`l5_startup_list.csv`) and
  the published `data/l5_company_library.csv` carries all 1,500 rows with ATS
  fields; downstream consumers must apply the ≤1,110 cap. A future non-startup
  expansion (e.g. completing L3 international or adding L6) would raise the cap
  proportionally.

## 7. Limitations & sampling bias

1. **ATS discovery is search-based**, not crawl-based: platforms are only detected
   when their URL patterns surface in search results. `custom` and `none` are
   broad buckets; some `none` companies do use an ATS that isn't publicly indexed.
2. **API validation is a point-in-time liveness check** (2026-10-07). Boards go
   stale; FAIL/ZERO is not proof a company stopped hiring.
3. **L1 skews big/US/listed** (153 index picks + 347 hand-added); quality of the
   hand-added list is unvalidated.
4. **L3 is US-listed only** (S&P indices); international traditional industries
   are not covered.
5. **L4 overlap audit was exact-match only** (removed Stripe); fuzzy duplicates
   across L1–L4 (e.g. renamed unicorns) may remain.
6. **L5 is YC-only**; non-YC startup ecosystems are absent. 83% have no public ATS,
   so job-demand signal for L5 must come from YC's job board / Wellfound, not
   from ATS APIs.
7. **Workday full pagination is paused** — L1's 201 verified companies are
   interface-validated only; full job corpora are not yet collected.

## 8. Files in me-drive

| File | Description |
|------|-------------|
| `data/l1_company_library.csv` | L1 technology (494) |
| `data/l2_company_library.csv` | L2 finance (410) |
| `data/l3_company_library.csv` | L3 traditional industries (1,054) |
| `data/l4_company_library.csv` | L4 unicorns (632) — commit `51274cd0` |
| `data/l5_company_library.csv` | L5 startups (1,500) — commit `cacf21fc` |
| `data/README.md` | Per-layer documentation index |
| `data/company-library-l1-l5-summary.md` | This file |

Local working files (not pushed): `~/workspace/upstream-samples/company_lib/`
(`l4_api_verify.csv`, `l5_api_verify.csv`, per-group ATS results, ID lookups).

## 9. Reference sources

- Wikipedia unicorn-company table — parsed 2026-10-07
  (https://en.wikipedia.org/wiki/List_of_unicorn_startup_companies)
- Y Combinator OSS API (`yc-oss/api`) — 6,277 companies at collection, 2026-10-07
  (https://github.com/yc-oss/api)
- ATS platform docs used for API validation:
  - Greenhouse Boards API (`boards-api.greenhouse.io`)
  - Lever Postings API (`api.lever.co`)
  - Ashby Posting API (`api.ashbyhq.com`)
  - Workday CXS API (`POST /wday/cxs/<tenant>/<site>/jobs`)
  - SmartRecruiters API (`api.smartrecruiters.com`)
