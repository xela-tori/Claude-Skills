# Research Sources & Methods (content-strategy)

Detailed source catalog and community-mining guidance for Phase 1 (audience interest & trend research) and Phase 2 (competitor audit). The main SKILL.md points here when deep source detail is needed.

---

## First-party data (highest value — use if available)

- **Google Search Console** — queries already bringing the user's site traffic. Shows real demand from the real audience.
- **Site search logs** — what visitors search FOR on the user's site. Missing answers = content gaps.
- **Customer support tickets, DMs, live chat logs** — questions in customer language.
- **Sales call transcripts, review comments** — objections, pain points, phrasing.
- **Survey responses** — open-ended responses (topics & language), common themes (30%+ mention = high priority), resources requested (what they wish existed), content preferences (formats they want).
- **The user's own blogs and social pages** — if the user shares URLs to their blog, newsletter archive, or social profiles (Facebook, Instagram, TikTok, LinkedIn, YouTube, X/Twitter, Threads, Pinterest, etc.), fetch and analyze them directly. Extract:
  - Topics they're already covering.
  - Posts with highest engagement (proxy for audience interest).
  - Recurring themes or series.
  - Hashtags and phrases the audience responds to.
  - Comments and replies (questions, objections, language).
  - Topic gaps in the user's own coverage that show up as underserved interests.
  Mine comments and replies as a first-party language source on par with support tickets. If the user mentions they have a blog or socials but doesn't share URLs, ask for them before running the crawl.

---

## Free SERP-native sources (always available, no tools needed)

- **Google autocomplete** — seed keyword + prefixes like "how to", "why", "best", "vs", "alternatives".
- **People Also Ask (PAA) boxes** — expand recursively; each expansion spawns more questions.
- **Related searches** at the bottom of any SERP.
- **YouTube autocomplete and YouTube Search suggestions** — different intent than Google.
- **TikTok search suggestions + "Others searched for"** — primary search engine for younger audiences.
- **Pinterest autocomplete and Pinterest Trends** — strong for lifestyle, food, DIY, beauty, fashion, wedding, home niches.
- **Amazon autocomplete** — gold for product and commercial-intent keywords.
- **Bing autocomplete** — skews older / enterprise / B2B.

---

## Free specialized tools

- **Google Trends** — topic trajectories (rising vs. declining), regional interest, related queries.
- **Google Keyword Planner** — free with a Google Ads account, real volume (bucketed).
- **AnswerThePublic** (free tier) — question patterns around a seed keyword.
- **AlsoAsked** (free tier) — PAA trees several levels deep.
- **Keyword Sheeter** — scrapes Google autocomplete at scale.
- **Exploding Topics** (free tier) — emerging/rising topics before they hit mainstream tools.
- **Keywords Everywhere** (cheap Chrome extension) — volume overlay on any SERP.
- **LowFruits / Keysearch / KWFinder / Ubersuggest / Serpstat** — affordable alternatives to Ahrefs/SEMrush.

## SERP structure analysis

- Scan top-ranking pages for a seed keyword — their H2s and H3s are the subtopic keywords Google already rewards. Reverse-engineer the structure.

## Paid keyword tools (if the user has them)

- If the user provides keyword exports from **Ahrefs, SEMrush, Moz, GSC, or similar**, analyze for: topic clusters, buyer stage, search intent, quick wins (low competition + decent volume), content gaps vs. competitors.

## Market adaptation

**Adapt source selection to the user's market.** Google Trends and GSC don't always give useful data in small or non-English markets. Lean more on social listening, community mining, and local-platform autocomplete (e.g. Naver in Korea, Baidu in China, Yandex in Russia, Cốc Cốc in Vietnam).

---

## Social listening

Look for active conversations, viral moments, frustrations, and debates in the user's niche on the platforms where their audience actually is (reference `platform-knowledge-base.md`). Identify:

- Trending conversations, debates, and viral moments in the niche.
- Common audience sentiments, frustrations, and desires.
- Trending hashtags and conversations.
- Hooks and angles currently getting traction.

---

## Community mining (adapt to the user's space)

- **Tech / SaaS / indie**: Reddit, Hacker News, Indie Hackers, Product Hunt, dev Discords.
- **Creator / marketing**: Twitter/X, LinkedIn, marketing Slack groups, specialized newsletters.
- **E-commerce / D2C**: Reddit (r/[niche]), Facebook Groups, review sites, TikTok comments.
- **B2B / enterprise**: LinkedIn Groups, industry Slack communities, trade forums, association sites.
- **Local / service**: Nextdoor, Google Reviews, local Facebook Groups, Yelp.
- **Health / wellness / lifestyle**: Reddit, specialized forums, Instagram/TikTok comment sections, Discord servers.

Mine each relevant community for: most-upvoted questions, repeated complaints, language and phrases the audience uses organically, unanswered pain points.

---

## Trending hooks (time-sensitive layer)

While doing the research above, also capture time-sensitive opportunities:

- Trending conversations relevant to the niche *right now*.
- Upcoming events, holidays, product launches, seasonal moments (next 30–90 days).
- Emerging subtopics gaining momentum.
- Cultural or industry news creating permission-giving angles.

These get tagged to pillars in Phase 3, each with an approximate expiry date.

---

## Competitor audit — what to extract

**Go directly to their blogs and social pages — don't rely on general search alone.** For each competitor, locate and crawl:

- Their **blog / resources / learn / help center / newsletter archive** — the full topic map of what they publish.
- Their **social profiles** on whichever platforms matter in the user's niche: Facebook, Instagram, TikTok, LinkedIn, YouTube, X/Twitter, Threads, Pinterest, Reddit communities they run, Discord/Slack where relevant. Reference `platform-knowledge-base.md` (if available) to pick the right platforms per industry.
- Their **SERP footprint** — search `site:competitor.com [seed topic]` to find what ranks, and check which of their pages appear on high-intent queries the user cares about.

**For each competitor, extract:**

- Topics they cover consistently (map the taxonomy — categories, tags, recurring series).
- Top-performing posts as a signal of audience interest (highest engagement, comments, shares, views).
- Formats and platforms they lean on, and which ones they underuse.
- Recurring angles, frameworks, and content "hooks" they own.
- Keywords and phrases they rank for or use repeatedly in titles and captions.
- Hashtags and community tie-ins.
- Comments and replies on their posts — customer language, objections, unanswered questions.
- Topics they're **ignoring or covering poorly** (= content gap).
- Missing angles, formats, or audience segments.

**Then synthesize:**

- Topics you can cover *better* (quality gap).
- Topics competitors aren't touching (whitespace gap).
- Saturated areas to avoid unless the user has a unique angle.
- Underused formats on platforms where the user's audience is active.
- Keywords and phrases worth targeting that show up in competitor content but aren't well-served.

If a competitor blocks crawling or hides engagement metrics, say so in the output and fall back to visible signals (post frequency, recent titles, comment counts where shown). Don't fabricate numbers.
