# Resume Formatting Guide

This file is the source of truth for future resume updates in this repository.

## Core Rule

Always update the resume section-wise.

When new information is provided:
- Identify which section it belongs to first.
- Update only the relevant section file under `src/`.
- Keep the existing section order from `resume.tex`.
- Avoid mixing unrelated content across sections.
- Prefer shortening content within a section instead of changing global spacing.

## Current Section Order

The resume currently renders sections in this order:

1. `src/heading.tex`
2. `src/summary.tex`
3. `src/experience.tex`
4. `src/skills.tex`
5. `src/certifications.tex`
6. `src/education.tex`

Do not reorder sections unless explicitly requested.

## File Responsibilities

### `resume.tex`
- Controls document structure and section order.
- Should stay minimal.
- Only update this file when:
  - adding/removing a section
  - changing global document settings
  - changing package usage

### `custom-commands.tex`
- Stores reusable LaTeX macros and list spacing.
- Treat this as layout infrastructure.
- Do not tighten spacing aggressively to force content into one page.
- If page overflow happens, reduce content length first.

### `src/heading.tex`
- Contains:
  - full name
  - title / years of experience
  - email
  - phone
  - LinkedIn
- Keep this compact and centered.
- Keep contact details on a single line when possible.
- Avoid adding extra links unless clearly valuable.

### `src/summary.tex`
- Must stay short: ideally 2 lines, max 3 lines in the compiled PDF.
- Focus on:
  - total experience
  - primary stack
  - strongest domain/engineering strengths
- Do not turn this into a paragraph-heavy career objective.

### `src/experience.tex`
- Each company entry should be updated independently.
- Use one `\resumeSubheading` per role.
- Format:
  - company / project name on left
  - date range on right
  - role on left of second line
  - location on right of second line
- Bullet rules:
  - Prefer 2 to 5 bullets per role.
  - Keep each bullet concise and achievement-focused.
  - Start with a strong action verb.
  - Mention technologies only when they add signal.
  - Avoid repeating the same skill in every bullet.
  - Prefer impact, ownership, scale, security, performance, automation, delivery.
- If space is tight:
  - shorten bullets first
  - merge overlapping bullets
  - remove lowest-signal bullet last

### `src/skills.tex`
- Keep skills grouped by category.
- Current categories:
  - Backend
  - Frontend
  - Databases & Caching
  - Cloud & DevOps
  - Messaging & Integration
  - AI Skills
- Add skills only if they are actually reflected in experience, projects, or certifications.
- Avoid large unstructured keyword dumps.

### `src/certifications.tex`
- Keep one certification per bullet.
- Use official certification names.
- Keep ordering intentional:
  - most relevant first, or
  - strongest brand/value first

### `src/education.tex`
- Keep this compact.
- One entry is usually enough unless explicitly asked to add more.
- Format:
  - institution
  - year range
  - degree
  - location

## Style Rules

- Target a clean single-page resume.
- Do not solve layout issues by forcing negative vertical spacing that causes overlap.
- Keep wording professional, concise, and recruiter-friendly.
- Use action-oriented bullet phrasing.
- Avoid weak filler such as:
  - responsible for
  - worked on
  - involved in
- Prefer:
  - developed
  - built
  - implemented
  - optimized
  - delivered
  - integrated
  - secured
  - automated

## Single-Page Strategy

If the resume spills to a second page, fix it in this order:

1. Shorten the summary.
2. Shorten long bullets in `src/experience.tex`.
3. Reduce redundant skills in `src/skills.tex`.
4. Trim low-value certification items if necessary.
5. Adjust layout spacing only as a last resort.

Never reintroduce line-overlap issues to save space.

## Updating Workflow

For every future update:

1. Classify the new content by section.
2. Edit only the relevant `src/*.tex` file first.
3. Check whether the update affects page length.
4. If it does, compress content in that same section before touching global formatting.
5. Recompile and verify that the resume remains readable and single-page.

## Compile Reminder

Use:

```powershell
pdflatex resume.tex
pdflatex resume.tex
```

The output file is `resume.pdf`.
