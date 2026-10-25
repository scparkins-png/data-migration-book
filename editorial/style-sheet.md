# House Style Sheet — *Don't Let a Data Migration Panic You*

Every editorial pass checks the manuscript against this sheet. Rules marked **Settled** come from standards Stuart has already set for the book. Rules marked **Proposed** are drawn from how the manuscript is mostly written now and need Stuart's confirmation before they are enforced. Open decisions are listed at the end.

Version 0.1 · 25 October 2026

---

## 1. Language and voice

| Rule | Status |
|:-|:-|
| UK English spelling and usage throughout (organise, colour, programme, licence (noun) / license (verb), catalogue, despatch). | Settled |
| First person when Stuart writes about his own work and experience ("I was brought in…"), never third person. | Settled |
| Plain English. Any jargon is defined the first time it appears (ETL, UAT, BOM, picklist). | Settled |
| Practical, confidence-building tone. Lead each step with the win it secures. The reader already knows migrations carry risk, so avoid repeated warnings. | Settled |
| Examples are either real (with a source) or labelled *Illustrative scenario*. | Settled |
| The second client project ("Gweek") is **not named** anywhere until the review stage. *Current manuscript: not named — compliant.* | Settled |
| Address the reader as "you". Contractions are fine in the Foreword and How to Use chapters; the step chapters mostly avoid them. Keep that split. | Proposed |

## 2. Names and terms

| Term | Use | Avoid |
|:-|:-|:-|
| Flow7 | Flow7 (one word, no space). "the Flow7 Migration System" on first use in a chapter. | Flow 7, FLOW7, F7 (except in figure labels) |
| Sage products | Sage 50, Sage X3 (X3 alone after first use in a section) | Sage50, SageX3 |
| Arrow in case-study name | Sage 50 → Sage X3 in headings and captions; "Sage 50 to Sage X3" in running text | mixing both in one sentence |
| The planning chapter | **Create Your Plan** | Before You Start (old name) |
| Master data | master set / Master Data Set (when it's the named artefact) | master data source, data master (except Step 3's title) |
| go-live | "go-live" as a noun or adjective ("the go-live window"); "go live" as a verb ("when you go live") | Go Live mid-sentence (keep capitals only for the Step 7 name) |
| Step references | Step 1 … Step 7; sub-steps 1A, 4B, 5C3 etc. | step one, Step One |
| Chapter references | Numbered chapters: Chapter 1 … Chapter 7 (= Step 1 … Step 7). Named chapters by title in italics: *Create Your Plan*, *Know the Business*. | chapter four, Ch. 4, "Chapter 11" |
| The book | handbook | workbook (reserved for Excel files) |
| UAT, ETL, BOM, SKU, GRN | Spell out on first use in each chapter, then abbreviation | plural with apostrophe (BOM's) |
| Bills of Materials | Bill of Materials (singular), Bills of Materials (plural) | Boms, BOMS |
| Websites | stuartparkins.com | spdata.co.uk (still in Ch 5), www. prefix |
| Company | SP Data Consultancy Ltd | SPDATA (except when citing the original publication) |

## 3. Numbers, dates and units

- Numbers one to nine in words; 10 and above in figures. Always figures for percentages, money, measurements and record counts (3 records, 7,000 products).
- Thousands separator: 7,000 (not 7000). Percentages: 10% (no space) in running text.
- Dates: 28 October 2025. Date formats inside examples stay as the example requires (DD/MM/YYYY).
- Data sizes: MB, GB, TB with a space after the number (330 MB). *Proposed — current text uses 330MB.*
- Case-study figures must match across chapters (see open decision D5).

## 4. Punctuation and typography

- Spaced en/em dash as used throughout: "the source — and the target". Keep the em dash (—) with spaces; it is the manuscript's dominant pattern.
- Curly quotes and apostrophes in the final output; the build converts straight quotes automatically, so the Markdown stays plain.
- Double quotes for speech and quoted terms; single quotes only inside double.
- Ellipsis as a single character (…).
- One space after full stops.
- Use the times sign (×) only in formulas; arrows (→) for sequences and the case-study name.

## 5. Chapter structure

**Book structure (settled):** Part One — Getting Started · Part Two — The Flow7 Migration System (Chapters 1–7) · Part Three — After the Move · Appendices.

**Settled pattern for step chapters (Chapters 1–7)**, in this order:

1. Chapter label and title, with "Step N — …" subtitle
2. Hook line (bold)
3. Where You Are in Flow7
4. In this chapter you will…
5. What you'll need from earlier chapters
6. Why This Matters
7. What You Are Actually Doing
8. Key things to get right
9. From the Field
10. Your Checklist (items verbatim from the Flow7 Project Plan Checklist)
11. Worked example
12. Your Turn (exercise, then "Now go to the full template")
13. What you have achieved in this chapter
14. You're Ready to Move On When… (the STOP/GO gate)
15. "Know the business" signpost (one line, pointing forward to *Know the Business*)

Note: *How to Use This Handbook* lists "In this chapter you will…" **before** "Where you are in Flow7"; every chapter does the reverse. One of them needs to change (open decision D6).

**Headings**: one H1 per chapter (the title). Section headings in Title Case as above. *Proposed: standardise "Why This Matters" etc. — current chapters mix "Why this matters" and "Why This Matters".*

**Lists — keep them light (decided 25 Oct 2026):** the reader should never face a massive checklist on the page. The full task list lives in the Excel Project Plan Checklist; the book shows only what helps the reader act now. Each step chapter has three clearly different lists — *Your Checklist* (the essential tasks, short, pointing to the Excel file for the rest), *Your Turn* (practice on the page) and the *STOP/GO gate* (no more than six items). The critical edit trims each chapter to this.

**Signposting system (approved 25 Oct 2026):** see `editorial/reader-flow-and-critical-edit.md` §4 — fixed chapter opener, running heads, recurring box types, distinct list styles.

**Checklist and gate format**: *Proposed* — every checklist as a three-column table (Ref · Task · ☐) and every gate as a two-column table (Gate · ☐), so the printed book has boxes to tick. Currently Chapters 6–9 use bullet lists.

**Exercises**: numbered by chapter in Part Two — Exercise 1.1, 1.2…; in *Create Your Plan*, Planning Exercise 1–4. Chapters 3–6 currently have single unnumbered exercises — fine as they are.

**Figures**: numbered by chapter in Part Two (Figure 3.1); unnumbered in named chapters.

## 6. Markup conventions in the Markdown files

| Marker | Meaning |
|:-|:-|
| `{{write-in}}` | A full-width writing line for the reader |
| `{{write-in-short}}` | A short writing line |
| `{{write-in-box}}` | A ruled box of several lines |
| `{{figure: id \| caption}}` | Where a figure goes; the id matches `editorial/figure-list.md` |
| `> ▶ **…**` | A callout box (worked example, key idea) |
| `> 💡`, `> 📋`, `> ⚠️` | Tip, worked-example placeholder and caution callouts |
| `> ↩ **Tracking back.**` | Go back to an earlier step |
| `> 📄 **Your template.**` | Which template to open and where to download it |
| `{{progress: N}}` | The seven-step "you are here" strip in the chapter opener |

## 7. Sources and citation

- Case-study extracts are attributed with the full URL on first citation in the book.
- **Checklists summarise (decided 25 Oct 2026):** the book shows the essential actions in plain words, tagged with their checklist reference (1A, 1B…). The full, word-for-word task list lives in the Excel Project Plan Checklist and the step templates — the book points readers to those resources. Simplicity is the rule.
- **Worked examples:** real (anonymised) where available; otherwise an *illustrative scenario*, clearly labelled, that can be swapped for real client data later.
- **Templates:** the step templates are separate files from the Project Plan Checklist. Each chapter's *Your template* box names the exact files.
- Forbes/McKinsey migration statistics appear in the Introduction only, with a transparent editorial footnote; the McKinsey attribution is removed. Primary source still to be verified.
- **References (decided 25 Oct 2026):** Stuart's own material (the Sage 50 → Sage X3 case study, Flow7 templates, checklists and workbooks) is covered once, in a single "About the sources" note in the front matter — no footnotes. External sources (e.g. the Forbes/McKinsey statistics) get a numbered note in the text and a full entry in a References appendix at the back.

---

## Open decisions for Stuart

| # | Decision | Options | Recommendation |
|:-|:-|:-|:-|
| D1 | **References.** | **Decided:** own sources → one "About the sources" note; external sources → numbered note + References appendix | Done — see §7 |
| D2 | **Workbook or handbook?** | **Decided:** "handbook" for the book; "workbook" only for Excel files (the Project Plan Checklist, the Data Mapping workbook) | Done — structural pass 1 |
| D3 | **Chapter numbering.** | **Decided:** three parts. Part One — Getting Started (Foreword, How to Use, Create Your Plan: named, not numbered). Part Two — The Flow7 Migration System (Chapters 1–7, chapter = step). Part Three — After the Move (Know the Business: named). Then appendices. | Done — structural pass 1 |
| D4 | **Cooking analogy.** | **Decided:** dropped — the three references removed | Done (pass 1) |
| D5 | **Case-study product count.** | **Decided:** 7,500+ everywhere | Done — apply in copy-edit pass |
| D6 | **Section order.** See §5 above. | Fix How to Use / fix every chapter | Fix How to Use (one edit instead of seven) |
| D7 | **Third-person self-references.** Chapters 5 and 6 and *Know the Business* open From the Field with "documented by Stuart Parkins", and Chapter 5's opening quote is signed "— Stuart Parkins". | keep as source attribution / rewrite in first person | First person in the text; keep the formal attribution in the source note |
