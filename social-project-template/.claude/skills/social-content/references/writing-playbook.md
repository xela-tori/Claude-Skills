# Social-Content Writing Playbook

Detailed per-format writing guidance. The main SKILL.md's Phase 5 points here for the long form details. Every principle below is enforced by the Phase 5 self-check.

---

## For searchable content (blog posts, SEO-focused pieces)

- **Offer 2–3 headline options** for every blog post — one optimized for SEO (primary keyword up front), one optimized for social sharing (curiosity or counterintuitive angle), one direct (clearest possible statement of value). Let the user choose.
- Target specific keywords from the pillars file (primary + 2–3 secondary).
- Match search intent — answer what the searcher actually wants.
- Place the primary keyword in the title, first paragraph, one subheading, and meta description.
- Use secondary keywords naturally in body copy and other subheadings — write for humans first, not keyword density.
- **Readability rules:** 8th-grade reading level for broad audiences (adjust up for technical/niche readers). Paragraphs 2–4 sentences max. Subheading (H2 or H3) every 200–300 words so the article is scannable without reading every word.
- Provide comprehensive coverage — use "People Also Ask" results to find related questions worth answering in the piece.
- **Structure for featured snippets:** lead each major section with a clear definition or direct-answer sentence, use numbered lists for step-by-step processes, use tables for comparisons — these formats win position-zero placements.
- Include data, examples, and links to authoritative sources (1–2 external) and related content on the same site (2–3 internal).
- Optimize for SEO/AEO/AI/LLM discovery: clear positioning, structured content, brand consistency.
- **Inline visual markers:** Embed visual placement markers directly inside the article body, exactly where an image, infographic, or GIF should appear. Use HTML comment syntax so markers are invisible if the markdown is rendered. Each marker is numbered sequentially and includes everything a designer needs to create the visual without asking questions. Format:
  ```
  <!-- VISUAL #1: [Brief concept description]
       Layout: [Composition and arrangement]
       Dimensions: [Width x height, e.g., 1200x630px for blog featured width]
       Alt text: "[Accessibility description]" -->
  ```
  This lets the copywriter know exactly where to place the image when pasting into the CMS, and lets the designer find all visual briefs by searching for `<!-- VISUAL`. The numbering (`#1`, `#2`, etc.) gives everyone a shared reference language.

---

## For email content

- **Offer 2–3 subject line options** for every email, each with a brief note on its open-rate angle (e.g., "curiosity gap", "direct value statement", "urgency/social proof"). Subject lines under 50 characters clear mobile preview panes cleanly. Preview text should complement — not repeat — the subject line.
- **Mobile-first:** most email is read on a phone. Short paragraphs (2–3 sentences), bold key phrases so skimmers catch the point, and a single clear CTA button rather than a text link buried in a paragraph.
- **Personalize where possible** — first name at minimum; company name, role, or behavior-based triggers (e.g., "you downloaded X last week") where the data exists.
- **Include an unsubscribe footer reminder** in the `Publish:` section — a placeholder like `[Unsubscribe] | [Company name] | [Address]`. Every marketing email legally requires one and the copywriter needs to know it goes there.
- Follow the same inline visual marker system as blog posts, but add email-specific fields:
  ```
  <!-- VISUAL #1: [Brief concept description]
       Dimensions: [Max 600px wide for email-safe rendering]
       File size: [Keep under 500KB for deliverability]
       Fallback: [Static image description for email clients that block GIFs/animations]
       Alt text: "[Accessibility description]" -->
  ```
- The `Fallback` field is required for any animated GIF or dynamic visual, since many email clients block animations by default.

---

## For shareable content (social posts, thought leadership)

- Lead with a novel insight, original data, or counterintuitive take.
- Challenge conventional wisdom with well-reasoned arguments.
- Tell stories that make people feel something.
- Create content people want to share to look smart or help others.
- Connect to current trends or emerging problems.
- Share vulnerable, honest experiences others can learn from.

---

## For video / reel content

Write full scripts in markdown format including:

- **Hook** (first 1–3 seconds — on-screen text and spoken word).
- **Script body** with timestamps or beat markers.
- **On-screen text overlays.**
- **B-roll / visual direction notes.**
- **CTA** (end card).
- **Caption** for the post.
- **Hashtags.**

---

## Cross-platform coherence

Posts from the same pillar in the same week should feel thematically connected but each must be fully standalone. A reader seeing only the LinkedIn post should get complete value. A reader seeing only the Instagram carousel should get complete value. But someone who sees both should feel they came from the same strategic mind — not from different campaigns.

---

## Writing as a genuine human (non-negotiable)

Every post must read as if a real person sat down and wrote it — with natural imperfections, personal voice, and authentic rhythm. If the AI writing detection guide was loaded in Phase 1, actively avoid every pattern it documents. Even without the guide, follow these principles:

- Vary sentence length unpredictably.
- Use concrete sensory details instead of abstract summaries.
- Include specific numbers and real-feeling anecdotes.
- Avoid hedging phrases like "it's worth noting" or "it's important to remember."
- Never list three adjectives in a row.
- Don't start consecutive sentences or paragraphs with the same structure.
- Skip formulaic "In today's world" or "In conclusion" wrappers.
- Let some sentences be blunt, incomplete, or conversational.

The reader should never think "this sounds like ChatGPT wrote it."

---

## Visual defaults (every post gets a Design section)

Across virtually every major platform, content with visuals significantly outperforms plain text in reach and engagement — algorithms reward it, humans scroll past text walls. Every post file must include a `Design:` section with a visual brief. Even text-format posts benefit from a supporting image (quote graphic, data card, branded photo).

Scale the number of visuals to content length:

- Short posts (under ~300 words) → one visual.
- 300–800 words → two visuals.
- 800+ words (blog posts, emails) → one visual roughly every 300–400 words to break up text.

**Deliberate exceptions** — cases where skipping visuals is the right call:

- LinkedIn text posts where raw, unpolished authenticity IS the strategy (founder vulnerability stories).
- Personal/founder-voice emails where plain text signals trust and intimacy.
- Polls where the poll UI itself is the visual engagement element.
- X/Twitter hot takes and short replies where text-nativeness is the point.

For these exceptions, note in the `Reference: Content Notes` section why visuals were intentionally omitted.

**`visuals_mode` note:** The `Design:` section must always be written in full regardless of `visuals_mode`. It is the brief that downstream image production consumes. Whether actual images get generated in Phase 6 depends on the mode the user chose in Step 0.

---

## Quality self-check (run for every post before saving)

- [ ] Follows the content rules from the template file.
- [ ] Uses the correct template structure for this platform + format.
- [ ] Hook lands before the platform's "see more" cutoff.
- [ ] Single CTA, matched to post objective.
- [ ] Brand voice is present but platform-adapted.
- [ ] Hashtags/keywords follow platform-specific guidance.
- [ ] Technical specs are correct (character count, format dimensions noted).
- [ ] If repurposed: works as a standalone piece without needing the source.
- [ ] Fact claims are sourced or flagged for user verification.
- [ ] **Reads like a human wrote it, not an AI.** Re-read the post and ask: would a real person actually write this sentence? Check for AI tells — generic filler phrases, overly balanced "on one hand / on the other hand" structures, suspiciously perfect parallel constructions, hollow superlatives, and any pattern flagged in the AI writing detection guide. If any sentence feels robotic, rewrite it until it sounds like a person with opinions and a personality.
