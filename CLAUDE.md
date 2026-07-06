# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A content-only repo that translates London Underground station names into Finnish. No build, tests, or tooling — just Markdown. All prose is written in **English**; the Finnish translations are the subject matter.

## Editorial rules for translations

- Base every translation on genuine **etymology / historical context** of the English name, and follow Finnish place-name conventions. Cite sources (usually Wikipedia) inline.
- Keep it **professional — no humorous or joke translations.**
- When a name doesn't translate cleanly, reason it out and choose creatively; justify the choice by pointing to real existing Finnish place names where possible.
- **Prefer a real Finnish toponym that echoes the name over a stiff literal translation** — even if that toponym's own etymology doesn't match the English name 100% (e.g. Angel → _Angeli_, Acton → _Tammela_). Fall back to the literal only when no real place name fits, and say so (e.g. Bank → _Pankki_).
- Wrap Finnish words and chosen translations in `_underscore italics_`.
- Finnish directional compounds are hyphenated: `Itä-` (east), `Länsi-` (west), `Pohjois-` (north), e.g. `Itä-Tammela`.

## Adding a station

1. Create `stations/<kebab-case-english-name>.md` (drop apostrophes: St Paul's → `st-pauls.md`). Grouped stations share one file (e.g. `acton.md` covers Acton Town / East / West / North Acton).
2. Follow this exact section order — see `stations/acton.md` (grouped) and `stations/bond-street.md` (single) as references:
   - `# <Station Name>` (H1, English)
   - Intro paragraph (no heading): which line(s) serve it and where it is located
   - `## Summary` — table `| London Underground station | Finnish translation |`, one row per station covered
   - `## Background` — etymology/history with cited links
   - `## Direct translations` — table `| English | Finnish |` breaking the name into component words (comma-separated alternatives allowed), followed by prose weighing the options
   - `## Conclusion` — final reasoning stating the chosen Finnish name
3. Update the matching row(s) in `all-stations.md`:
   - Link both the Original name and Finnish name cells to the new file: `[Bank](stations/bank.md)`
   - Fill the **Line(s)** column
   - Keep the table **sorted alphabetically by Original name**
   - Untranslated stations use `tbd` in the Finnish column with a blank Line(s) column

## Conventions

- Markdown tables are column-aligned/padded; a format-on-edit hook runs `oxfmt` (installed via `brew install oxfmt`, config in `.oxfmtrc.json`) to maintain this. Do not use Prettier/npx.
- Commit directly to `main` (only when asked).
