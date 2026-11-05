# How this repository was made (Ebonyi State)

This file is written by the build on 2026-11-05, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Ebonyi State Government: Laws and Financials (PDF) | <https://ebonyistate.gov.ng/laws/and/financials> | 2026-11-01 | Laws of Ebonyi State, from the copies the Ebonyi State Government publishes in its public records ("Laws and Financials") at ebonyistate.gov.ng. Official texts of a legislative nature are not eligible for copyright: Copyright Act, 2022 (Nigeria), s. 3(b). |
| Ebonyi State Government: Right of Way Regulations PDF | <https://ebonyistate.gov.ng/storage/documents/min-1-row-regulations-updated-1-1pdf-1749541863.pdf> | 2026-11-05 | Official legislative text published by the Ebonyi State Government; Nigerian Copyright Act 2022, section 3(b). |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `public-sector-audit-amendment-law-2021` | Ebonyi State Public Sector Audit Law (Amendment), 2021 (Law No. 015 of 2021) | 1 | 2021-11-11 to 2021-11-11 |
| `right-of-way-regulations-2024` | Ebonyi State Telecommunication and Related Infrastructure Right of Way Regulations | 1 | 2024-12-30 to 2024-12-30 |

The build made 2 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-05.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (Africa/Lagos) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Law here states its own commencement, and its version is dated by it; no general rule is applied. https://ebonyistate.gov.ng/laws/and/financials

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `351064a2fec4604d35b4c834000bad7e60f9e3573c82790d4572d44444040c0d` (16235 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

2 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 2 history commits and 3 tags (history tip `c9c119639fcedf72aa60d947d448761bd88e5996`).

## Decisions made by hand

- Public Sector Audit Law (Amendment) 2021 is dated 2021-11-11: it "shall be deemed to have come into effect on Thursday the 11th day of November 2021".
- Each Law is one version: the text as enacted, credited to the Law itself (first_law) and dated by its commencement. Later amendments are not in this record.
- One file per section. The title lines printed before the enacting formula are "000-title", the enacting formula (where printed) is "001-enacting-formula", and schedules follow the sections. Each section's heading is its printed margin note (or, where there is none, "Section N") and stands as the file's first line; it is not part of the checked text.
- The text layer is read with line positions: running heads, page numbers and margin notes are set apart by their place on the page, and the pieces of one printed row are joined left to right. Lines wrapped by the printer are joined into one paragraph per line; a new paragraph starts at a section number, a bracketed (sub)paragraph letter or number, a quoted definition, a Part heading or a schedule heading. A Part heading printed after a section is placed at the head of the next section. Typing errors in the source stay as printed.
- One current-text version, with first_law null. Regulation 1.1 states that it is deemed to have come into effect on 30 December 2024. The text is one file because the official PDF text layer does not reliably mark separate section headings.
- The current PDF has four pages and two inline raster images: a page-one letterhead or watermark and a page-four signature. Neither is a normative table, formula, map or schedule. No image asset is included under the current image deferral. The text is extracted from the PDF text layer and span geometry, with no model or OCR corrections.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text is the PDF text layer, parsed by rules; no model wrote or corrected legal text.
- none: programmatic PDF text extraction only; no model wrote or corrected the law text.
