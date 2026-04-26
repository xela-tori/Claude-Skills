# Project Context

This folder holds the source-of-truth context for your project. Every skill in this bundle reads these files **before** doing any work.

## What to put here

Whatever describes your project — brand, product, audience, voice, market, goals. Any of these formats work:

- `.md` / `.txt` — read directly
- `.pdf` — extracted via the `pdf` skill
- `.docx` — extracted via the `docx` skill
- `.xlsx` / `.csv` — read via the `xlsx` skill

Typical files:

- `brand_context.md` / `brand_context.docx` — the core document (company, product, audience, voice, goals, competitive landscape, country/market)
- `target_audience.md` — detailed persona(s)
- `brand_voice.md` — tone, diction, dos and don'ts
- `style_guidelines.pdf` — visual identity (colors, typography, imagery)
- `competitive_landscape.md` — key competitors and differentiators
- Any first-party data exports (customer surveys, support ticket summaries, GSC exports, etc.)

## Starter template

`Brand context template.docx` is included — copy it, fill it in, rename it to something like `brand_context.docx`, and leave it in this folder.

## How skills use this folder

Skills will:

1. List every file here (recursively) at the start of each invocation.
2. Read each one based on its extension.
3. Extract what they need (audience, voice, goals, etc.).
4. **Stop and ask you** if required context is missing — you can either add the file to this folder or upload it directly in chat.

## Important

- **Do not delete the folder itself.** Empty is fine; missing is not.
- **Keep files current.** When your brand, product, or audience shifts, update the relevant file. Skills trust what they read here.
