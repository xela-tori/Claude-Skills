# Output File Structure (social-content)

Exact spec for saving individual post files. The main SKILL.md's Phase 7a references this file. Every post file must follow this structure so a beginner can open the file and know exactly what to do with each section.

---

## Filename format

`<topic>_<platform>_<format>_<published-date>.md`

- **Topic:** short slug from the subtopic (hyphens, lowercase).
- **Platform:** linkedin, instagram, x-twitter, facebook, tiktok, blog, email, etc.
- **Format:** text-post, carousel, reel, thread, story, article, etc.
- **Published date:** YYYY-MM-DD.

Example: `logging-fatigue_linkedin_text-post_2026-04-18.md`

Overwrite existing files with the same name.

---

## Section action-labels (required on every heading)

Every content section is prefixed with an action label so the reader instantly knows what to do with it:

- **`Publish:`** → copy-paste this into the platform. Live content.
- **`Design:`** → send this to a designer or use for visual/asset creation.
- **`Production:`** → record this yourself or hand to a video editor.
- **`Reference:`** → internal notes. Read for context, do not publish or hand off.

---

## Required elements at top of every file

**1. YAML frontmatter** — metadata at the top:

```yaml
---
platform: [Platform name]
format: [Content format]
date: [YYYY-MM-DD]
pillar: "[Pillar ID and name]"
template: "[Template name used, or 'Adapted from [X]' if fallback]"
repurposed: [Yes/No]
---
```

**2. "How to use this file" section** — brief, format-specific instruction block immediately after the frontmatter. Tailor it to the format:

Text post:

```
## How to use this file
Copy everything under **Publish: Post Text** and paste it into [Platform]'s composer. The **Reference** section is internal notes — do not publish.
```

Carousel:

```
## How to use this file
Copy **Publish: Caption** into [Platform]'s text box. Send **Design: Slide Contents** to your designer — it has every slide's text and layout. **Reference** sections are internal notes.
```

Reel / video:

```
## How to use this file
Copy **Publish: Caption** into [Platform]'s text box. Hand **Production: Video Script** to your video editor (or record it yourself). Send **Design: Thumbnail** to your designer if included. **Reference** sections are internal notes.
```

Blog post:

```
## How to use this file
Copy everything under **Publish: Article Body** into your CMS. Use the frontmatter fields for meta title, description, and URL slug. Visual markers (<!-- VISUAL #1 -->, #2, etc.) show exactly where to place images — send the markers to your designer so they know what to create and where it goes.
```

Email:

```
## How to use this file
Copy everything under **Publish: Email Body** into your email platform. Subject line and preview text are in the frontmatter. Visual markers (<!-- VISUAL #1 -->, #2, etc.) show where images go — send them to your designer. Each marker includes a fallback description for email clients that block images.
```

---

## Content sections (in this order, include only sections relevant to the format)

**1. `## Publish: [Section name]`** — The exact content that goes live. Section name adapts to format:

- `Publish: Post Text` (text posts, photo+text).
- `Publish: Caption` (carousels, reels, stories, static images).
- `Publish: Article Body` (blog posts — includes inline `<!-- VISUAL #N -->` markers).
- `Publish: Email Body` (emails — includes inline `<!-- VISUAL #N -->` markers with fallback fields).
- `Publish: Poll` (polls — clearly separates post text, poll question, and poll options).
- `Publish: Alt Text` (static images — the text for the alt text field).

**2. `## Design: [Section name]`** — Visual creation briefs. Section name adapts:

- `Design: Slide Contents` (carousels — each slide's headline, body text, and visual direction).
- `Design: Visual Brief` (static images — full design spec with colors, typography, layout).
- `Design: Thumbnail` (videos — thumbnail design spec).
- `Design: Story Cards` (stories — each card's text overlays, stickers, and visual direction).

**3. `## Production: Video Script`** — Full timestamped script with spoken words, on-screen text, and visual direction. Only for reels/videos.

**4. `## Reference: Engagement Strategy`** — Reply templates, comment management, pin strategy. Do not publish.

**5. `## Reference: Production Notes`** — Filming tips, editing style, sound design, technical specs. Do not publish.

**6. `## Reference: Content Notes`** — Internal reasoning, template adaptation notes, hook analysis. Do not publish.

---

## Key rules

- Never mix publishable content with internal notes in the same section.
- Within `Design:` sections for carousels, separate each slide clearly (`### Slide 1`, `### Slide 2`, etc.) and within each slide, separate the slide content (what goes ON the slide) from the visual direction (how the designer should style it) using a `**Visual direction:**` label.
- Within `Publish:` sections for polls, use clearly labeled sub-parts: `**Post text:**`, `**Poll question:**`, `**Poll options:**` (as a numbered list).
- The `Publish:` section must contain ONLY text the user copies. No design notes, no parenthetical instructions, no "(Design note: ...)" asides.
