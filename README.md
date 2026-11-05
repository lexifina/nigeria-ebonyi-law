# Ebonyi State: law history in git

The Laws of Ebonyi State (Nigeria) as a git history: one file per section, one paragraph per line, so `git blame`, `git log` and `git diff` work line by line. The text is the English text of the Laws as enacted.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Laws as enacted and one current regulation.** The Ebonyi State Government publishes Laws and regulations as PDFs. The Public Sector Audit Law (Amendment) 2021 is its text as enacted. The Right of Way Regulations are the current text in the Government's updated PDF, dated by their stated commencement.

| Folder | What |
| --- | --- |
| one folder per Law (e.g. `public-sector-audit-amendment-law-2021/`) | the Law as enacted: `000-title.md`, one file per section, then any schedules |
| `right-of-way-regulations-2024/` | the updated Right of Way Regulations: one full-text file, effective 30 December 2024 |

The texts are added in parts as each is verified. Only PDFs with a text layer are used; scanned copies (pictures of pages) are left out, as are Bills and appropriation (budget) Laws.

Known gaps in the source: The Public Sector Audit Law (Amendment) 2021 amends the Ebonyi State Public Sector Audit Law 2021, which is not in this record; its assent date is blank in the copy, and it is dated by its own commencement clause.

## Source

[Ebonyi State Government](https://ebonyistate.gov.ng/laws/and/financials): PDFs of the Laws. Each PDF's sha256 is recorded with its version in `data/versions.json`.

## Dates

Each text is dated by the day it came into force under its own commencement provision, at noon in Lagos time (West Africa Time, UTC+1).

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

The text layer of each PDF (no OCR) is read with the position of every line: running heads, page numbers and margin notes are set apart by their place on the page, and each section's margin note stands as the first line of its file. Lines wrapped by the printer are joined, so each paragraph is one line. Typing errors stay as printed.

## How it is checked

Every version is read back from git on the day it took effect and must match the corpus. A second, independent reading of every PDF (a different PDF engine) must contain every letter and digit of each Law in the same order, with nothing in the body left out (only page furniture and margin notes may lie between). Results are in `REPRODUCE.md`.

## What "author" means

The author of each commit is the Law that made the change, with an e-mail address that cannot exist; the committer is always Lexifina.

## Limits

Only the texts listed above; later amendments to the 2021 Law are not applied. The Government's PDFs are not the authoritative text; the Ebonyi State Official Gazette is.

## Licence

See [LICENSE](LICENSE): official texts of a legislative nature are not eligible for copyright in Nigeria (Copyright Act, 2022, s. 3(b)). Source: Ebonyi State Government.
