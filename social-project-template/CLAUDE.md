# Project: [Your project name]

[One- or two-sentence description of what this project is about. Example: "Social content engine for [brand]. Produces platform-native posts, calendars, and supporting visuals across LinkedIn, Instagram, TikTok, and email."]

---

## How Claude should navigate this project

1. **Read this file first.** It is the source of truth for this project's structure, conventions, and overrides. If a section here conflicts with a skill's default behavior, this file wins.
2. **Read everything in `_context/` next.** That folder holds the brand, audience, voice, and market context. Every skill needs it before doing any real work.
3. **Project-level skills override global skills.** The skills in `.claude/skills/` are the source of truth for this project. If a global or plugin-installed skill with the same or overlapping name exists, prefer this project's version.
4. **Follow delegations.** If a section below points to another file (e.g., "see `_sop/brand-voice.md`"), read that file and apply its rules.

---

## Folder structure

| Folder | Purpose |
|---|---|
| `_context/` | Brand/project context. All skills read this first. Supports `.md`, `.txt`, `.pdf`, `.docx`, `.xlsx`. See `_context/README.md`. |
| `social content/latest/` | Output folder for `social-content`: post files, `Social content calendar.xlsx`, `content-plan.md`, `progress.md`. |
| `social content/latest/visuals/` | Generated visuals for posts. |
| `social content/repurposing content/` | Optional: drop source material here (blog posts, podcast transcripts, video transcripts, newsletter archives) for `social-content` to repurpose. |
| `.claude/skills/` | Project-level skills (override any global skill of the same name). |
| `.claude/skills/references/` | Shared reference files used and written by skills. |

---

## Skills in this project

| Skill | What it does | Reads | Writes |
|---|---|---|---|
| `social-platform-research` | Researches how each platform currently works (algorithms, formats, specs, norms). | User inputs (platforms, countries). | `.claude/skills/references/platform-knowledge-base.md` |
| `content-strategy` | Plans content pillars, scores them, identifies topics/subtopics. | `_context/`, `platform-knowledge-base.md` (recommended). | `.claude/skills/references/content-pillars.md` |
| `social-post-template` | Builds a platform-aware library of post templates, hook formulas, and CTA formulas. | `platform-knowledge-base.md` (recommended). | `.claude/skills/references/social-post-templates.md` |
| `social-content` | Writes posts, builds calendar, optionally creates visuals. | `_context/`, all three reference files above, optional extras in `references/`. | Post files + calendar + plan + progress + visuals in `social content/latest/`. |

### Skill dependency order

```
social-platform-research
        │
        ▼
platform-knowledge-base.md
        │
        ├────────────────┬─────────────────┐
        ▼                ▼                 ▼
content-strategy   social-post-template    (consumed by social-content)
        │                │
        ▼                ▼
content-pillars.md   social-post-templates.md
        │                │
        └────────┬───────┘
                 ▼
          social-content
     (needs all 3 references + _context/)
```

Run in this order for a new project. Once all three reference files exist, `social-content` can run whenever needed.

---

## Additional folders (optional)

You can create other folders at the project root — for example:

- `_sop/` — standard operating procedures.
- `templates/` — reusable templates (report shells, slide decks, email frames).
- `data/` — first-party data exports.
- `archive/` — older generated content you want to keep but not reference.

**Claude will only use these folders if you declare them here.** Add entries to the section below so skills know which folders are relevant and to which skill.

### My additional folders

<!--
Add one line per folder you want skills to know about. Example:

- `_sop/brand-voice.md` — extra voice rules. **social-content** must read and apply these before writing any post.
- `_sop/content-rules.md` — governance rules. **All skills** must follow.
- `templates/monthly-report.docx` — output template. **social-content** writes the monthly recap into this shape.
- `data/customer-survey-q1.csv` — first-party audience research. **content-strategy** should factor this in.
-->

*(none declared yet — add entries above as you create folders)*

---

## Overrides

Use this section to change any default behavior from a skill's `SKILL.md`. Overrides declared here win.

<!--
Examples:

- **social-content** writes post output to `posts/` instead of `social content/latest/`.
- **content-strategy** must use the journey framework "Discover → Engage → Subscribe → Advocate" (not the default B2B Awareness/Consideration/Decision).
- **social-content** skips visual generation by default (the team produces visuals in Figma).
- **All skills** must treat the `_sop/tone-rules.md` file as authoritative on voice — even if it conflicts with `_context/brand_voice.md`.
-->

*(no overrides declared — skills use their defaults)*

---

## How to extend this project

1. **Add context:** drop files into `_context/` (any supported format).
2. **Add a folder:** create it at project root, then declare its purpose in the "Additional folders" section above so skills read and use it.
3. **Change skill behavior:** declare the change in "Overrides" above.
4. **Add a skill:** drop a new skill folder under `.claude/skills/<skill-name>/` with its own `SKILL.md`.

---

## Notes

- **Generated reference files** (`content-pillars.md`, `platform-knowledge-base.md`, `social-post-templates.md`) are produced by the skills themselves. You don't need to create them manually — run the skill and it will generate a fresh copy into `.claude/skills/references/`.
- **Refresh cadence:** platform knowledge and content strategy drift. Plan to re-run `social-platform-research` every 2–3 months and `content-strategy` whenever your product, audience, or market shifts.
