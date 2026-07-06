---
name: add-station
description: Scaffold a new London Underground station translation. Creates stations/<kebab-name>.md following the strict template and updates the all-stations.md index row. Use when adding or translating a station.
disable-model-invocation: true
---

# Add a station translation

Usage: `/add-station <Station Name>` (e.g. `/add-station Baker Street`). For grouped stations that share one writeup (like the Actons), pass the group name and cover all of them in one file.

## Steps

1. **Research the etymology first.** Look up the historical/etymological origin of the English name (Wikipedia and the Londonist etymology article linked in README are good starts). Break the name into component words. Do NOT invent a translation without grounding it.

   **Then search for a real Finnish place name before settling on a literal translation.** Once you have the literal Finnish word(s), actively look for an existing Finnish toponym (village, district, farm, street) that echoes the name — check Wikipedia, Kotus, and map/place-name sources. A real place name that matches in sound and feel is preferred over a stiff literal rendering, **even if that toponym's own etymology doesn't match the English name 100%** (e.g. Angel → _Angeli_, a Sámi village whose name is unrelated to "angel"; Acton → _Tammela_ rather than the literal _Tammimaatila_). Fall back to the literal only when no real place name fits, and say so (as with Bank → _Pankki_).

2. **Create `stations/<kebab-case-name>.md`** — kebab-case the English name, dropping apostrophes (St Paul's → `st-pauls.md`). Use this exact structure:

   ```markdown
   # <Station Name>

   <Intro sentence: which line(s) serve it and where it is located.>

   ## Summary

   | London Underground station | Finnish translation |
   | -------------------------- | ------------------- |
   | <Station Name>             | <Finnish name>      |

   ## Background

   <Etymology/history with cited inline links, e.g. Wikipedia. Blockquote source material where useful.>

   ## Direct translations

   | English | Finnish         |
   | ------- | --------------- |
   | <word>  | <finnish, alts> |

   <Prose weighing the alternatives — consider Swedish loanword roots and Finnish place-name norms (-la/-lä suffixes in the west, -nen in the east). Explain the choice.>

   ## Conclusion

   <Final reasoning stating the chosen Finnish name, ideally justified by a real existing Finnish place name.>
   ```

3. **Follow the editorial rules** (see CLAUDE.md): etymology-based, professional (no jokes), Finnish terms in `_underscore italics_`, directional compounds hyphenated (`Itä-`, `Länsi-`, `Pohjois-`).

4. **Update `all-stations.md`:**
   - Find the station's existing `tbd` row (table is alphabetical by Original name).
   - Link both the Original name and Finnish name cells to the new file: `[Bank](stations/bank.md)`.
   - Fill the **Line(s)** column.
   - Keep the table sorted alphabetically; keep columns aligned.
   - For grouped stations, add a linked row for each individual station, all pointing to the same file.

5. **Show the user** the chosen translation and reasoning before considering it done. Do not commit unless asked.
