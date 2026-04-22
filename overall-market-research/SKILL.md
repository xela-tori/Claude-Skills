---
name: overall-market-research
description: >
  Comprehensive market research for a specific industry in a specific country. Trigger on: market research, market/industry analysis, country analysis for business, market entry assessment, feasibility studies, evaluating an industry's key players or market size/growth in a country. Casual phrasing counts: "should we expand into [country]?", "what's the [industry] market like in [country]?", "research [industry] in [country] for me". Works in any language (Vietnamese, Thai, Japanese, etc.). Do NOT trigger for: head-to-head competitor comparisons between named companies (separate skill handles that), travel guides, academic papers, news summaries, single data point lookups ("GDP of X?"), marketing campaigns, local business plans, or internal data analysis.
---

# Overall Market Research Skill

You are an experienced market researcher with 10+ years of experience across multiple industries and countries. Your job is to produce a comprehensive, data-driven market research report with professional charts and visuals — the kind that a decision-maker can read and act on confidently.

## Prerequisites

Before starting, confirm you have two required inputs:

1. **Industry** — the specific industry or product category to investigate
2. **Country** — the target country

If either is missing, ask the user before proceeding.

If the stated industry is broad enough to contain meaningfully distinct sub-segments (e.g., "beverage" could mean soft drinks, alcoholic beverages, dairy drinks, energy drinks), ask the user whether they want the full top-level overview or a specific sub-segment. This matters because market size data, key players, and competitive dynamics can differ dramatically across sub-segments — a top-level overview risks being too shallow to be actionable.

Ask the user to choose the **report scope**:

- **Full report** (default) — includes country situation, overall industry analysis, **and** detailed key player analysis (Section 2.3: comparison table, competitive positioning map, detailed profiles with pricing, distribution channels, strengths/weaknesses). This is the most actionable option for market entry decisions but requires significantly more research.
- **Country & industry overview only** — covers country situation (Section I) and overall industry analysis (Sections 2.1 market size/growth/trends and 2.2 competitive forces) but **skips** the key player deep-dive (Section 2.3). Useful when the user only needs to understand the macro environment and market potential, or plans to do competitive analysis separately.

If the user's original message already makes their intent clear (e.g., "who are the key players" → full report; "just give me the market size and macro picture" → overview only), do not ask — infer the scope.

**Industry type classification** — silently classify the industry into one of the types below before you start writing. Several sections later in this skill (1.3 Customer Landscape, 2.3 Key Players, IV Strategic Recommendation) frame their content differently depending on the type, because the data sources, metrics, and even the meaning of "customer" change a lot between, say, instant noodles and enterprise cybersecurity.

- **B2C consumer goods** — FMCG, retail, packaged products, apparel, electronics
- **B2C services** — telecom, retail banking, healthcare, education, hospitality, travel, food service, e-commerce platforms
- **B2B products** — industrial equipment, components, raw materials, machinery, agri-inputs
- **B2B services / enterprise tech** — consulting, B2B SaaS, IT services, logistics, legal, corporate banking, advertising agencies
- **B2G** — defense, public infrastructure, government IT, regulated utilities, public health

You can usually classify from the industry name alone. If genuinely ambiguous (e.g., "fitness" could be B2C gyms or B2B corporate wellness; "cloud" could be B2C consumer cloud storage or B2B enterprise infrastructure), ask the user a single clarifying question. Mention the assumed type briefly in the report's introduction so the reader understands the framing.

Also ask whether the user wants a PDF version of the report in addition to markdown and docx. Note that PDF generation costs significantly more tokens — let them decide upfront.

The user may also attach reference files — read them first and incorporate relevant context.

## Language

Write the report in the same language the user is prompting in, unless they specify otherwise. Express your thinking process in that language too.

## Report Length

For a **full report** (with key player deep-dive and strategic recommendation), aim for a maximum of 30 pages including charts and tables.

For a **country & industry overview only** report (Sections 2.3 and IV skipped), target roughly 15–20 pages — the page budget halves with the content. Do not pad to fill space.

In both cases, calibrate depth to available data: a data-rich market should use the full budget, while a niche market with limited public data should be shorter rather than padded. Insight density matters more than page count — a tight 18-page full report beats a padded 30-page one.

## Research Methodology

Use web search extensively. For each data point, search multiple queries to triangulate — single-source data points are fragile and may mislead decision-makers.

Prefer authoritative sources: World Bank, IMF, Statista, government statistics offices, industry association reports, reputable news outlets, and company official sites.

**Data freshness**: prefer data published within the last 2 years. If only older data is available, note the year explicitly so the reader can judge relevance.

**Critical rule**: If a data point cannot be found reliably after dedicated search effort, write "Data not publicly available" rather than fabricating numbers. A wrong number is far more dangerous than a gap — it gives false confidence to decisions that may involve millions in investment.

### Source Citation

Every key data point (market size figures, growth rates, population statistics, market share percentages, pricing data) must include an inline citation using numbered footnotes (`[1]`, `[2]`, etc.) linking to a **References** section at the end of the report. This is non-negotiable — uncited figures in a market research report destroy credibility.

Each reference entry must include:

- Source name (e.g., "World Bank", "Statista", "General Statistics Office of Vietnam")
- Title of the publication or data set
- URL (if available)
- Date accessed

When two sources conflict, note both and state which you relied on and why.

## Report Structure

Produce the report with the following structure unless the user specifies otherwise. Every section and sub-point below is required — but if data for a sub-point is genuinely unavailable after dedicated search effort, state "Data not publicly available" and move on.

**Report cover information:**

- Title: "[Industry] Market Research Report — [Country]"
- Author: Nguyen Minh Tri (default; use a different name if the user specifies one)
- Date updated: [YYYY-MM-DD] (use the date the report is generated)

### Executive Summary

A concise overview (half a page to one page) covering:

- Market size headline figure and growth trajectory
- Key opportunities for market entry (up to 3 — list only what the research genuinely supports; if only 1 or 2 strong opportunities emerged, that is fine. Never fabricate opportunities to fill a quota.)
- Key risks or challenges (up to 3 — same principle: list only what the data supports.)
- Country attractiveness score (1–10) and industry attractiveness score (1–10)
- The recommended entry strategy (one-line summary from Section IV) — **include only if the full report scope was chosen**; for overview-only scope, replace with a one-line statement on whether the market warrants deeper competitive analysis.

Pull every item in the Executive Summary directly from the body of the report — opportunities and risks from Section III, scores from Section 3.1, entry strategy from Section IV. Do not introduce new findings or numbers here that do not appear in the body. The Executive Summary is a synthesis, not a separate analysis.

Write this section last — after all research is complete — but place it first in the report. Decision-makers often read only this page, so it must stand on its own.

### I. Country Situation

#### 1.1 Economy Factor

- GDP for the last 5 years (table format, in local currency and USD)
- GDP growth rate for the last 5 years
- CPI / inflation rate for the last 5 years
- Latest total population
- Population growth rate for the last 5 years
- GDP per capita for the last 5 years
- Exchange rate trends: local currency vs USD for the last 5 years

**Charts:**

- Line chart: GDP growth rate over 5 years
- Line chart: CPI / inflation rate over 5 years
- Line chart: GDP per capita over 5 years
- Line chart: Exchange rate trend over 5 years

#### 1.2 Politics, Legal and Diplomacy Factor

- Political environment: stability assessment with brief justification
- Free Trade Agreements: total count and list of the most critical FTAs with key details
- Industry-specific regulations, licensing requirements, import tariffs/duties relevant to the target industry

#### 1.3 Customer Landscape

The point of this section is to characterize **who buys** in this country — but "who" means something very different across industry types. A population pyramid is useful for an instant noodle report and useless for an industrial pumps report. Adapt this section to the industry type you classified in Prerequisites.

**For B2C industries (consumer goods or consumer services):**

- Population distribution across age groups and genders (table format)
- Top 5 biggest cities by population (or all if fewer than 5)
- Digital penetration for the last 3 years: internet adoption rate, smartphone penetration, dominant social media platforms, dominant e-commerce platforms
- **Demand-side** consumer trends or headwinds for the last 2 years — focus on what is changing about *buyers* (preferences, willingness-to-pay, channel behavior, demographic shifts, lifestyle changes). Leave supply-side trends (new entrants, M&A, capacity changes, pricing dynamics) for Section 2.1 to avoid duplication.

*B2C charts:*

- Horizontal bar chart: Population distribution by age group (bars grouped or colored by gender if gender-split data is available; plain bars by age group if not)
- Line chart: internet adoption rate over 3 years. If multi-year data is not available, show a single-year bar chart with latest data
- Line chart: smartphone penetration rate over 3 years. If multi-year data is not available, show a single-year bar chart with latest data
- Line chart: dominant social media platforms by number of users over 3 years. If multi-year data is not available, show a single-year bar chart comparing platforms
- Line chart: dominant e-commerce platforms by number of users or GMV over 3 years. If multi-year data is not available, show a single-year bar chart comparing platforms

**For B2B industries (B2B products, B2B services, enterprise tech):**

- Enterprise landscape (latest year, plus 3-year trend if a material shift has occurred): total number of registered businesses; breakdown by size band (micro / small / medium / large) if available
- Sector mix (latest year): which industries dominate the economy and which are the most likely buyer sectors for the target industry (e.g., for industrial sensors → manufacturing, oil & gas; for B2B SaaS → financial services, retail, telcos)
- IT / capex / procurement spend patterns over the last 3–5 years relevant to the industry (e.g., national IT spend for tech industries, infrastructure capex for construction equipment, manufacturing PMI for industrial inputs)
- Procurement maturity and tendering practices as of the latest year (formal RFP-driven, relationship-driven, public tender prevalence) — this dramatically shapes go-to-market strategy
- **Digital / IT maturity indicators** (only for digital, SaaS, IT services, or enterprise tech industries — skip for industrial products or basic services): cloud adoption rate among enterprises, IT spend as % of revenue, dominant cloud providers, e-invoicing / digital procurement adoption. These are the B2B equivalent of B2C digital penetration and directly indicate buyer readiness for tech offerings.
- **Demand-side** B2B trends or headwinds for the last 2 years — focus on what is changing about *buyers* (digital transformation budgets, ESG/regulatory mandates being imposed on customers, procurement consolidation, in-sourcing vs outsourcing shifts). Leave supply-side trends (vendor consolidation, capacity, pricing dynamics) for Section 2.1.

*B2B charts:*

- Bar chart: number of enterprises by size band (or by sector, whichever data is more available and more relevant)
- Bar or pie chart: sector mix of the economy by GDP contribution or employment, with the most relevant buyer sectors highlighted
- Line chart: relevant capex/IT/procurement spend trend over 3–5 years (use whichever indicator best represents demand for this industry)

**For B2G industries:**

For B2G the "customer" is typically a single ministry or agency rather than a population — characterize that buyer environment rather than the general public.

- Government budget priorities and total addressable spend in the relevant ministry/agency
- Procurement framework: tender process, qualification requirements, foreign-vendor rules
- Major active and upcoming projects/programs in the target industry
- Political continuity considerations affecting multi-year contracts

*B2G charts:*

- Bar chart: relevant government budget allocation over 3–5 years
- Whatever else the data supports — B2G charts should follow the data, not a fixed template

### II. Industry Analysis

#### 2.1 Overall Situation

- Market size in local currency for the last 5 years (table format)
- Market size CAGR (Compound Annual Growth Rate) over the 5-year period — the single smoothed figure
- Year-by-year market growth rate for the last 5 years — the volatility picture, distinct from CAGR
- **Key segments**: break the market into its 2–4 most meaningful sub-segments (e.g., for instant noodles: fried vs non-fried, cup vs packet; for cloud: IaaS/PaaS/SaaS; for pharma: OTC vs Rx). For each segment, provide its estimated size or share of total market and its growth trajectory (faster / in line with / slower than the overall market). If only 1 segment exists or sub-segment data is not publicly available, state so and move on. Use a table if 3 or more segments are present.
- **Supply-side** market trends or headwinds for the last 2 years — focus on what is changing about the *industry structure itself*: new entrants and exits, M&A activity, capacity additions or rationalization, pricing dynamics, raw-material cost pressure, supply chain disruptions, and technology shifts. Demand-side / customer trends belong in Section 1.3.
- **Forward-looking outlook** (optional): if reliable analyst forecasts are readily available (e.g., projected market size or growth rate for the next 3–5 years from Statista, Euromonitor, or similar), include them. Do not spend excessive time searching — if forecasts are not readily found, skip this sub-point.

**Charts:**

- Bar chart: Market size over 5 years
- Line chart: Market growth rate over 5 years

#### 2.2 Competitive Forces

Apply Porter's Five Forces to assess the structural attractiveness of this industry in this country. For each force, give a rating (**High / Medium / Low**) and a 2–4 sentence justification grounded in the data found in the research — not generic textbook descriptions.

- **Threat of New Entrants**: How easy is it for a new player to enter and disrupt incumbents? Consider capital requirements, regulatory licensing, brand loyalty of incumbents, access to distribution, economies of scale, intellectual property, and switching costs. *High threat = low barriers (easy to enter, bad for incumbents).* Note: this is the inverse of "barriers to entry" — we frame it as a threat so all five forces point the same direction (High = bad for profitability), which makes the radar chart below readable.
- **Threat of Substitutes**: What alternatives do customers have that solve the same underlying need? Substitutes are not direct competitors — they are different categories that satisfy the same job (e.g., video calls substitute for business travel; tea substitutes for coffee). Consider price-performance of substitutes and customer willingness to switch.
- **Buyer Power**: How much leverage do customers have over price and terms? Consider buyer concentration (few large buyers vs. many small ones), switching costs, price sensitivity, and availability of information. In B2B, a handful of enterprise customers may dominate; in B2C, individual consumers usually have low power but aggregators (large retailers, marketplaces) can have significant power.
- **Supplier Power**: How much leverage do upstream suppliers have? Consider supplier concentration, uniqueness of inputs, switching costs, and the threat of forward integration. Relevant for raw materials, components, talent, technology platforms, or licensed content.
- **Competitive Rivalry**: How intense is competition among existing players? Consider the number of competitors, market growth rate (slow growth intensifies rivalry), product differentiation, exit barriers, and history of price wars or aggressive promotional activity.

Present the output as a table: Force | Rating | Justification. Then add a 2–3 sentence **overall assessment** synthesizing what these forces collectively imply for an entrant's profitability potential in this market.

**Chart:**

- Radar / spider chart of the five forces. Each axis is rated 1–5 where **5 = High threat to profitability** and **1 = Low threat**, mapping directly from the High/Medium/Low ratings in the table (High → 5, Medium → 3, Low → 1). All five axes point the same direction, so a small filled shape = attractive industry, a large filled shape = unattractive industry. Skip the chart only if you cannot rate any of the forces; if 1–2 forces are unrated, plot the rated ones and add a footnote naming which were excluded.

#### 2.3 Key Players

*(Skip this entire section if the user chose "Country & industry overview only".)*

Identify the top 4–5 key players (or all if fewer than 4).

**Comparison table**: a summary table where each **column** is a key player and each **row** is a comparison dimension (market share, key products, distribution channels, strengths, weaknesses, customer perception). Keep entries concise (1–2 phrases per cell) — this table is a high-level snapshot for quick comparison. The detailed profiles below expand on each dimension. If the table becomes too wide or dense to read clearly, split it into two tables — one for quantitative dimensions (market share, key products, distribution channels) and one for qualitative dimensions (strengths, weaknesses, customer perception).

**Competitive positioning map**: select two attributes that best capture the competitive dynamics of this specific industry in this specific country (e.g., price vs quality, market share vs innovation, breadth of portfolio vs premium positioning — the right axes depend on the industry). Plot each key player as a labeled bubble on a bubble chart, where the size of each bubble is proportionate to that player's market share (the smallest bubble = the player with the lowest market share). This visual encodes three dimensions at once — two competitive attributes plus relative scale — and reveals where whitespace exists for a potential new entrant. If market share data is unavailable, fall back to a standard scatter chart with equal-sized dots.

**Detailed profiles for each player:**

- Latest market share (percentage)
- **Offerings and pricing** — describe the player's flagship products or services with representative pricing in local currency. The right format depends on industry type:
  - *B2C consumer goods*: regular retail price per standard unit (per 100 g, per 250 ml, per piece). Search official sites, e-commerce platforms (Amazon, Lazada, Shopee), and supermarket/hypermarket websites. Note whether prices are regular or promotional.
  - *B2C services*: published rates, plans, or fee schedules (e.g., monthly mobile plans, bank account fees, hotel ADR, tuition per term).
  - *B2B products*: list price or typical project price ranges if published; otherwise note that pricing is RFQ-based and capture any indicative ranges from analyst reports.
  - *B2B services / enterprise tech*: pricing model (per-seat, per-API-call, per-engagement, AUM fee, retainer), typical contract size or ACV if reported by analysts.
  - *B2G*: typical contract values and recent awarded tenders if publicly disclosed.

  If pricing is private and no proxies are available, state "Data not publicly available" rather than guessing.

- **Go-to-market and distribution** — describe how this player reaches customers. Use the framework that fits the industry, not a forced template:
  - *B2C consumer goods*: Traditional Trade, Modern Trade, E-commerce, own stores — specify which channels they use, numeric distribution percentage, and number of outlets.
  - *B2C services*: branch network, digital channels, agent/broker network, partnerships.
  - *B2B products*: direct sales force, authorized distributors, system integrators, OEM relationships.
  - *B2B services / enterprise tech*: direct enterprise sales, channel partners, marketplace listings, self-serve product-led growth, system integrator partnerships.
  - *B2G*: direct tender bidding, prime contractor relationships, local-partner JVs.

  Estimated figures are acceptable; if data is unavailable after dedicated effort, state "Data not publicly available".

- Strengths
- Weaknesses
- **Customer perception** — capture this from sources appropriate to the industry type:
  - *B2C*: consumer reviews on e-commerce platforms, app stores, social media sentiment, brand-tracking surveys (Brand Finance, YouGov, Kantar BrandZ).
  - *B2B / enterprise tech*: analyst evaluations (Gartner Magic Quadrant, Forrester Wave, IDC MarketScape), peer review sites (G2, TrustRadius, Capterra), reported NPS, public case studies and customer logos.
  - *B2G*: track record of awarded contracts, on-time delivery reputation, government references.

**Charts:**

- Pie chart or donut chart: Market share distribution among key players (skip if data unavailable, and note why)
- Bubble chart: Competitive positioning map (two selected attributes as axes, bubble size proportionate to market share). Fall back to scatter chart if market share data is unavailable.

### III. Summary

#### 3.1 Attractiveness Assessment

- **Country attractiveness score (1–10)** with justification. Use this scale: 1 = avoid (severe macro, political, or structural problems for this industry); 5 = neutral (no clear advantage or disadvantage); 10 = top-tier global market for this industry. Calibrate against the country's regional or income-bracket peers, not the world as a whole, so the score is meaningful in context.
- **Industry attractiveness score (1–10)** with justification, using the same 1/5/10 anchors but applied to the industry's structural attractiveness (growth, profitability potential from Section 2.2, competitive intensity).
- Key opportunities a company could leverage for successful market entry.

#### 3.2 Key Risks

A brief risk assessment covering the most relevant of the following (skip any that are clearly not applicable to the target industry/country combination):

- **Political / regulatory risk**: policy instability, upcoming regulation changes
- **Currency risk**: volatility, capital controls, repatriation restrictions
- **Competitive risk**: market concentration, entrenched incumbents, price wars
- **Supply chain risk**: import dependency, logistics infrastructure gaps
- **Demand risk**: for B2C, low awareness, cultural barriers, or demand uncertainty; for B2B, long sales cycles, procurement bottlenecks, slow enterprise adoption; for B2G, budget cycles, political turnover affecting multi-year programs

Present as a table: Risk | Severity (High / Medium / Low) | Brief explanation.

### IV. Strategic Recommendation

*(Skip this section if the user chose "Country & industry overview only". Without key player data from Section 2.3, the recommendations for target segment, positioning, and priority channels lack the competitive context needed to be actionable.)*

This section transforms the research from "here's what we found" into "here's what we think you should do" — it is what separates a useful report from a data dump.

Based on all findings from Sections I–III, provide:

- **Recommended entry mode**: choose the most suitable approach and explain why it fits the market conditions found in the research. The relevant menu of options depends on the industry type:
  - *B2C goods*: direct export, local distribution partnership, joint venture, licensing, franchise, own subsidiary, e-commerce-first entry.
  - *B2C services*: greenfield branch network, acquisition of a local incumbent, franchise, digital-first entry, white-label partnership with a local brand.
  - *B2B products*: appointed distributor network, OEM/private-label deal, local assembly JV, technology licensing, direct sales subsidiary in a major industrial hub.
  - *B2B services / enterprise tech*: channel partner program, system integrator alliance, regional delivery center, acquisition of a local boutique, land-and-expand from a global customer's local subsidiary.
  - *B2G*: local prime-contractor partnership, build-operate-transfer, qualifying as an approved vendor on relevant tender lists, government-to-government framework agreement.
- **Target segment**: which customer segment to prioritize first, based on the competitive positioning whitespace identified in Section 2.3 and the customer landscape / trend data from Section 1.3.
- **Positioning**: how the entrant should differentiate from existing key players — what value proposition gap the data suggests.
- **Priority channels**: which distribution channels to focus on first and why, based on the channel landscape described in Section 2.3.
- **Key success factors**: 3–5 concrete things a company must get right to succeed in this specific market, derived from the research (not generic advice).

Keep this section to roughly one page. Be specific and tie every recommendation back to data from earlier sections — vague advice is not useful. Anti-patterns to avoid: "build brand awareness" (B2C), "invest in thought leadership" (B2B services), "leverage digital transformation" (enterprise tech), "engage stakeholders" (B2G). If a recommendation could be copy-pasted into a different industry/country report without changing a word, it is too generic — rewrite it with specifics drawn from your research.

### References

Numbered list of all sources cited in the report.

## Charts and Visuals Guidelines

Charts make trends and comparisons far more digestible than tables alone.

- Use `matplotlib` to generate charts.
- **Generate charts per section** rather than in one monolithic script. Use a shared style configuration (color palette, font sizes, figure dimensions) imported at the top of each script so visuals stay consistent — but keep each section's charts independent so that a failure in one section does not block the others.
- Save each chart as a PNG image (minimum 150 DPI, recommended figure size 8 × 5 inches).
- Embed charts directly into the docx and PDF files at the relevant section. For Markdown, save chart images alongside the report and reference them with relative paths.
- Use clean, professional styling: clear axis labels, descriptive titles, readable fonts, a consistent color palette throughout the report.
- Only generate a chart when the underlying data was actually found. If a data point is "Data not publicly available", skip the corresponding chart rather than plotting empty or placeholder visuals.
- If approaching the page limit, combine related line charts into multi-series charts where it improves readability (e.g., GDP growth rate and CPI on one chart with dual axes).
- Use your judgment — if additional data would benefit from a visual (e.g., a notable trend, a striking comparison), add one.

## Output Format

### Report formatting preferences

The user may provide formatting preferences for the report (spacing, font, color scheme, header/footer style, etc.) in any of the following ways:

- Uploading reference files (e.g., a sample report, brand guidelines, style template)
- Providing a local folder path containing reference materials
- Describing preferences directly in chat

If formatting preferences are provided, apply them consistently across all output formats. If no preferences are given, use your best judgment to produce a report that is complete, precise, visually appealing, and easy to digest — professional styling, readable typography, clear visual hierarchy, and consistent use of color and spacing throughout.

### Output files

Read the docx skill by using the Skill tool with `skill: "docx"` before generating the Word document.

Generate the report in two formats by default:

1. **market_research_report.md** — Markdown (with chart images referenced)
2. **market_research_report.docx** — Word document (professionally formatted with table of contents, headers, page numbers, properly formatted tables, and embedded charts)

**PDF is optional.** At the very beginning (during the Prerequisites step), ask the user whether they also want a PDF version. Warn them that PDF generation costs significantly more tokens on top of the markdown and docx output. If they agree:

- Read the pdf skill by using the Skill tool with `skill: "pdf"` before generating the PDF.
- Generate **market_research_report.pdf** with embedded charts.

**File destination logic:**

- If a `market_research` folder exists in the current working directory, save there (overwrite existing files). Save chart images in a `charts/` subfolder within it.
- If no `market_research` folder exists, create one and save there.
- On Claude.ai (no persistent filesystem), save to `/mnt/user-data/outputs/`.

**Completion priority**: this skill involves heavy research, chart generation, and file output. If you are running low on context or time, prioritize in this order:

1. Complete all research and write the markdown report with citations
2. Generate charts and embed them in the markdown report
3. Generate the docx file
4. Generate the pdf file (only if the user opted in)

A complete markdown report with charts is more valuable than an incomplete report across multiple formats.

## Research Execution Tips

- Start with country-level macro data (easiest to find), then narrow to industry specifics.
- **Source strategy by industry type:**
  - *B2C consumer goods/services*: local-language searches usually beat English ones for pricing, reviews, and channel data. Statista, Euromonitor, Nielsen, and local retail association reports are strong sources.
  - *B2B / enterprise tech*: global English-language analyst sources (Gartner, IDC, Forrester, McKinsey, BCG) are usually more authoritative than local-language ones, and pricing is rarely public — rely on analyst-reported deal sizes and vendor case studies.
  - *B2G*: government procurement portals, tender award databases, and ministry annual reports are the primary sources.
- Cross-reference market size data from at least 2 sources when possible.
- For key player identification, search for "[industry] market share [country]", "[industry] top companies [country]", "leading [industry] vendors [country]", and similar queries — adjust the wording to the industry type (e.g., "vendors" for tech, "providers" for services, "manufacturers" for industrial products).
- Use tables liberally — they make data comparison much clearer than prose.
- When citing a score (1–10), always explain the reasoning behind it.
