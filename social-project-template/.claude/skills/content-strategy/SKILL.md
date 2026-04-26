---
name: content-strategy
description: Plan content pillars and topic mix — produces content-pillars.md that downstream skills consume. Trigger on "what should I post about", "what should I write about", "content ideas", "content pillars", "topic clusters", "content plan", "content strategy", "blog strategy", "social media strategy", "content mix", "how should I structure my content", or any request to plan/refresh/build a content strategy or pillar set. Also trigger when another skill needs content-pillars.md and it's missing or stale (older than ~2–3 months). This skill plans WHAT to create and WHY — it does NOT write posts or produce a publishing calendar; defer to social-content / draft-content for that.
---

# Content Strategy

Produces a living `content-pillars.md` that decides **what to create and why** — not how to write it. Downstream skills (especially social content creation) read this file to plan and execute.

---

## Step 0 — Discover project layout (run first, every invocation)

Before anything else, figure out where to read from and write to.

1. **Find the project root.** Walk up from the current working directory and pick the first match in this order:
   a. Nearest ancestor containing `CLAUDE.md` → that is the project root.
   b. If none found: nearest ancestor that directly contains a `.claude/` folder → that is the project root.
   c. If neither found: use the current working directory as the project root. You are in **standalone mode** — use fallbacks throughout.

2. **If `CLAUDE.md` exists, read it fully.** It is authoritative for this project. It may declare where context, references, and outputs live; delegate to other files (e.g., "see `_sop/rules.md`") — read those too; mark additional folders (like `_sop/`, `templates/`) as relevant; or override any default in this SKILL.md. **Project-level instructions beat skill defaults.**

3. **Project-level skills override global skills.** If a global or plugin-installed skill shares this name, the version in `.claude/skills/content-strategy/` is authoritative for this project.

4. **Resolve the context location** (where `_context/` lives):
   - If `CLAUDE.md` declares one, use it.
   - Otherwise, prefer `_context/` at the project root.
   - Fallback: `references/` at project root or next to this `SKILL.md`.

5. **Resolve the references location** (where this skill reads/writes reference files):
   - If `CLAUDE.md` declares one, use it.
   - Otherwise, prefer `.claude/skills/references/` at the project root.
   - Fallback: `references/` next to this `SKILL.md`.

6. **Never hardcode paths in your thinking.** Use whatever paths you resolved above.

---

## Step 1 — Load `_context/` (mandatory)

Read every file in the resolved context folder (recursive) at the start of every invocation:

- `.md` / `.txt` → read directly.
- `.pdf` → use the `pdf` skill.
- `.docx` → use the `docx` skill.
- `.xlsx` / `.csv` → use the `xlsx` skill.

Extract and internalize: company/product, target audience, pain points, goals, brand voice, competitive landscape, USPs, country/market.

**Required context for this skill:**
- Target audience / ideal customer
- Country / market
- Primary content goal (awareness, leads, community, thought leadership, education, etc.)

**If required context is missing**, stop and tell the user:

> This skill requires [list specifically what's missing]. You have two options:
>
> (a) Add the file(s) to `_context/` (supported: `.md`, `.txt`, `.pdf`, `.docx`, `.xlsx`), OR
> (b) Upload the file(s) directly in this chat.
>
> Which do you prefer?

Do not proceed until context is provided.

---

## Step 2 — Read `platform-knowledge-base.md` if it exists

Look for `platform-knowledge-base.md` at the resolved references location. It's produced by the **social-platform-research** skill. If you can't locate it, check sibling skill folders and any path the user specifies.

This file tells you how each platform works, what formats perform, and where the audience is active. Use it to inform platform-aware recommendations. If the file genuinely doesn't exist, note this to the user and recommend they run the **social-platform-research** skill afterward so future runs have platform context.

---

## Step 3 — Ask only what's still missing. Don't interrogate.

**Business context** (if not already covered by `_context/`)
- What does the company do?
- What problems does the product solve?
- Primary goal for content? (awareness, traffic, leads, engagement, community, conversion, thought leadership, education, etc.)
- Building personal brand, company brand, or both?

**Customer research** (if not already covered)
- Who is the ideal customer? *(required — do not proceed without this)*
- What questions do they ask before buying?
- What objections come up in sales conversations?
- What pain points appear in support tickets, reviews, or DMs?
- What language do customers use to describe their problems?

**Country / market** (if not already covered)
- Which country or countries is the content targeting? Required before proceeding.

**Current state**
- Do you have existing content? What's working and what's not?
- What resources do you have? (time, team, formats you can produce — written, video, audio, graphics)

**Competitive landscape** (if not already covered)
- Who are your 3–5 main competitors or peer accounts?

If the user doesn't know how to answer any question except ideal customer and country, move on. Don't block progress.

---

## Core principle: Searchable, Shareable, or Both

Every piece of content should be **searchable**, **shareable**, or **both**.

- **Searchable content** captures *existing demand* — people already looking for answers. Optimized for search (Google, YouTube, TikTok SEO, Pinterest, blog). Targets specific keywords or questions.
- **Shareable content** creates *new demand* — spreads ideas and gets people talking. Leads with novel insights, original data, contrarian takes, or emotional storytelling. Distributed through social feeds, shares, and reposts.

Prioritize searchable as the foundation (it compounds), then layer shareable for reach and authority. Tag each pillar as primarily searchable, shareable, or both.

---

## Phase 1 — Audience interest & trend research

Search for what the target audience is actively asking, complaining about, and engaging with. **Adapt all queries to the user's specific industry, niche, and country.** Generic queries produce generic strategy.

For the detailed catalog of sources (first-party data, SERP-native sources, free and paid tools, social listening, community mining per industry, and trending-hook capture), read **`references/research-sources.md`**.

### Organize findings into
- 5–10 trending conversations, debates, or viral moments.
- Common audience sentiments, frustrations, and desires.
- Language and phrases the audience uses organically (→ **Audience Language Bank** in output).
- Hooks and angles currently getting traction, tagged with rough expiry.
- Repeated questions = high-demand content opportunities.

---

## Phase 2 — Competitor content audit

Research 3–5 competitors or peers (user-provided or discovered via search). For the full competitor-audit checklist — what to crawl, what to extract per competitor, and how to synthesize into gaps — read **`references/research-sources.md`** (last section).

Short version: go directly to their blogs and social pages (don't rely on general search alone), map their taxonomy and top posts, extract the language and hooks they use, then synthesize into **quality gaps** (can cover better), **whitespace gaps** (untouched topics), and **saturated areas** to avoid unless the user has a unique angle. If a competitor blocks crawling or hides engagement metrics, say so — don't fabricate numbers.

---

## Phase 3 — Pillar synthesis

Cross-reference Phases 1–2 with the user's product, goals, and audience to define **3–6 content pillars**. Each pillar spawns subtopics and post ideas.

### How to identify pillars (four lenses)
1. **Product-led** — What problems does the product solve? What use cases matter?
2. **Audience-led** — What does the audience need to learn, solve, or feel?
3. **Search-led** — What topics have search volume and/or social interest?
4. **Competitor-led** — Where are competitors weak or absent?

### Pillar criteria
- Aligns with user's product/service.
- Matches what the audience cares about.
- Has demonstrated demand (search volume, social conversation, community questions).
- Broad enough to spawn many subtopics.
- User has genuine expertise, data, or a contrarian perspective to offer.

### For each pillar, define
- **Name and description.**
- **Differentiation angle:** What makes the user's take unique? If no clear angle exists, flag it.
- **Journey stage** — pick the vocabulary that matches this business type. See **`references/journey-and-intent.md`** for the six journey frameworks (B2B, B2C, creator, community, local/service, education). State the chosen framework at the top of the output so downstream skills know which vocabulary to use.
- **Searchable, shareable, or both.**
- **Content mix %:** Proportion of total content. Base on user's primary goal — see **`references/journey-and-intent.md`** for content-mix guidance by goal. Keep pure promotional content ≤ 5–10% regardless of goal.
- **Subtopics / post ideas:** 5–10 per pillar, each with suggested formats and platforms (reference `platform-knowledge-base.md` if available).
- **Trending hooks** (from Phase 1) tagged to this pillar with expiry dates.
- **Search-intent keyword modifiers** (for searchable content) — awareness, consideration, decision, implementation. Populate each bucket with **real keywords discovered in Phase 1** (autocomplete, PAA, GSC, keyword tools, community mining) and Phase 2 (competitor content audit), grouped by intent. See **`references/journey-and-intent.md`** for the four intent categories and starter-phrase examples.

---

## Phase 4 — Scoring and ranking

Score each pillar on four factors to determine ranking.

| Factor | Weight | Evaluate |
|---|---|---|
| **Audience demand** | **40%** | Frequency in research • % of audience affected • **Emotional charge** of pain point • Search volume & trajectory (rising / stable / declining) |
| **Strategic alignment** | **25%** | Fit with user's primary goal • Natural path from content to desired outcome • Connection to product/offer where relevant |
| **Competitive gap + differentiation** | **25%** | Low competitor coverage OR a strong unique angle in a crowded space • Quality gap in existing coverage • User's proprietary insight or perspective |
| **Execution feasibility** | **10%** | Time + team capacity • Format capability • Assets & research available vs. required • Sustainability over 3–6 months |

Score each factor **1–10**, then compute the composite as a **weighted average**:

```
Score = (Audience demand      × 0.40)
      + (Strategic alignment  × 0.25)
      + (Competitive gap      × 0.25)
      + (Execution feasibility × 0.10)
```

**Example:** demand 9, alignment 8, competition 7, feasibility 8 →
`(9 × 0.40) + (8 × 0.25) + (7 × 0.25) + (8 × 0.10) = 3.60 + 2.00 + 1.75 + 0.80 = 8.15`

Round composite scores to **one decimal place**. Rank pillars by composite score, highest first. Mark **(estimated)** next to any individual factor score where the underlying data is thin.

---

## Output

Write to the resolved references location as `content-pillars.md` (create folder if needed). Overwrite on full refresh. For single-pillar updates, **read existing file first** and edit only that section; re-rank the summary table.

```markdown
# Content Strategy: Pillars & Topics

**Last updated (DD-MM-YYYY):** DD-MM-YYYY
**Review by (DD-MM-YYYY):** DD-MM-YYYY (~2-3 months out)
**Brand/Product:** [from context]
**Primary goal(s):** [from context]
**Target audience:** [from context]
**Country / Market:** [from context]
**Journey framework used:** [e.g. Awareness → Consideration → Decision → Retention]

---

## Pillar Ranking Summary

| Rank | Pillar | Journey Stage | Searchable/Shareable | Content Mix % | Trend  | Pillar Attractiveness | Score |
|------|--------|---------------|----------------------|---------------|--------|-----------------------|-------|
| 1    | ...    | Awareness     | Both                 | 30%           | Rising | Highly attractive     | 8.2   |
| 2    | ...    | Consideration | Searchable           | 25%           | Stable | Little-medium         | 7.5   |

<sub>Example worked scores — row 1: (9×0.40) + (8×0.25) + (8×0.25) + (6×0.10) = **8.2**. Row 2: (8×0.40) + (9×0.25) + (5×0.25) + (8×0.10) = **7.5**.</sub>

> **Trend** uses 3 levels: `Rising` · `Stable` · `Declining` (as of month of last research).
>
> **Pillar Attractiveness** uses 5 levels: `Little attractive` · `Little-medium` · `Medium` · `Medium-high` · `Highly attractive`.

---

## Pillar 1: [Name]

**Journey stage:** [stage name from chosen framework]
**Type:** Searchable / Shareable / Both
**Content mix:** X%
**Differentiation angle:** [user's unique take]
**Trend status:** Rising / Stable / Declining (as of [month])
**Pillar attractiveness:** Little attractive / Little-medium / Medium / Medium-high / Highly attractive
**Score:** X.X &nbsp; = &nbsp; (demand X × 0.40) + (alignment X × 0.25) + (competition X × 0.25) + (feasibility X × 0.10)

### Why this pillar
[2-3 sentences: demand + alignment + opportunity]

### Subtopics & post ideas
- **Subtopic A:** [description]
  - Post idea 1, Post idea 2
  - Formats: [carousel, thread, reel, blog, etc.]
  - Platforms: [from platform knowledge base]
  - Search-intent keywords: [if searchable — list real keywords grouped by intent stage]
- **Subtopic B:** ...

### Trending hooks
- [Conversation/event] — expires ~[date]
- [Seasonal moment] — window: [date range]

### Competitor landscape
- **Who's covering this:** [Which competitors are active and how]
- **Where the gap is:** [Specific whitespace — topics, angles, formats, or audiences]
- **Opportunity:** [One concrete recommendation combining gap with differentiation angle]

---

(repeat per pillar)

---

## Audience Language Bank

Phrases, questions, and emotional language the audience uses organically. Useful for hooks and copywriting.

- "[phrase]" — context: [source]
- ...

---

## Pillar Refresh Signals

Review when:
- Engagement on a pillar declines 3+ consecutive weeks.
- Major industry event shifts conversation.
- New competitor enters or changes strategy.
- User's product/offer changes significantly.
- Scheduled review date reached.
```

---

## Writing style

Optimized for skill consumption and human scanning:
- Bullets, not prose. One actionable fact per bullet.
- Concrete numbers where available.
- Mark uncertainty: *(disputed)*, *(estimated)*, *(as of [month])*.
- Cite sources where useful.
- Date each section's last verification.

---

## Important reminders

- **Always search the web.** Don't rely on training knowledge for trends, search volume, competitors, or audience conversations.
- **Parallelize.** Split audience research, competitor audit, and trend research into parallel tasks where possible.
- **Preserve on partial updates.** Single-pillar updates: read file first, edit that section only, re-rank the summary table.
- **Be honest about gaps.** If data is unavailable or ambiguous, say so — don't fabricate numbers.
- **Adapt to the user's industry and market.** Generic queries produce generic strategy.
- **Don't write content.** This skill produces strategy. The social content creation skill writes posts.
