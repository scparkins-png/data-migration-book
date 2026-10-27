# House Style Sheet — *Data Migration the Right Way: The 7-Step System*

Every editorial pass checks the manuscript against this sheet. Rules marked **Settled** come from standards Stuart has already set for the book. Rules marked **Proposed** are drawn from how the manuscript is mostly written now and need Stuart's confirmation before they are enforced. Open decisions are listed at the end.

Version 0.2 · 27 October 2026 (updated after the critical edit)

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
| Address the reader as "you". Contractions are fine in the Foreword, How to Use and *A Final Word*; the step chapters use them sparingly. | Settled (copy-edit 1) |

## 2. Names and terms

| Term | Use | Avoid |
|:-|:-|:-|
| Flow7 | Flow7 (one word, no space). The method's full name is **the Flow7 Data Migration System** (decided 27 Oct 2026) — use it on first use in a chapter, then "Flow7". "Framework" is acceptable in marketing copy, not in the book. | Flow 7, FLOW7, F7 (except in figure labels); "Flow7 Migration System" (old name) |
| Sage products | Sage 50, Sage X3 (X3 alone after first use in a section) | Sage50, SageX3 |
| Arrow in case-study name | Sage 50 → Sage X3 in headings and captions; "Sage 50 to Sage X3" in running text | mixing both in one sentence |
| The planning chapter | **Create Your Plan** | Before You Start (old name) |
| Master data | master set / Master Data Set (when it's the named artefact) | master data source, data master (except Step 3's title) |
| go-live | "go-live" as a noun or adjective ("the go-live window"); "go live" as a verb ("when you go live") | Go Live mid-sentence (keep capitals only for the Step 7 name) |
| Step references | Step 1 … Step 7; sub-steps 1A, 4B, 5C3 etc. | step one, Step One |
| Chapter references | Numbered chapters: Chapter 1 … Chapter 7 (= Step 1 … Step 7). Named chapters by title in italics: *Create Your Plan*, *Know the Business*. | chapter four, Ch. 4, "Chapter 11" |
| Book title | *Data Migration the Right Way: The 7-Step System* (working title, 27 Oct 2026). "7-Step" uses the numeral in the title and on the cover, to echo Flow7; in running text it stays "seven steps". | *Don't Let a Data Migration Panic You* (former title) |
| The book | handbook | workbook (reserved for Excel files) |
| UAT, ETL, BOM, SKU, GRN | Spell out on first use in each chapter, then abbreviation | plural with apostrophe (BOM's) |
| Bills of Materials | Bill of Materials (singular), Bills of Materials (plural) | Boms, BOMS |
| Websites | stuartparkins.com | spdata.co.uk, www. prefix |
| The downloads (decided 27 Oct 2026) | Named by part, never as a bundle: **the Project Plan Checklist** (Excel and PDF, the master tracker) · **the step templates** (STEP1–STEP7 PDFs, the real work) · **the Flow7 Migration Workbook** (the combined Excel file — all step sheets in one) Collectively: "the Flow7 downloads at stuartparkins.com". | Foundation pack, Management bundle, Gumroad names (sales packaging — not in the book); "workbook" for anything that isn't the combined Excel file |
| Company | SP Data Consultancy Ltd | SPDATA (except when citing the original publication) |

## 3. Numbers, dates and units

- Numbers one to nine in words; 10 and above in figures. Always figures for percentages, money, measurements and record counts (3 records, 7,000 products).
- Thousands separator: 7,000 (not 7000). Percentages: 10% (no space) in running text.
- Dates: 28 October 2025. Date formats inside examples stay as the example requires (DD/MM/YYYY).
- Data sizes: MB, GB, TB with a space after the number (40 MB).
- Case-study figures must match across chapters (see open decision D5).

## 4. Punctuation and typography

- Spaced en/em dash as used throughout: "the source — and the target". Keep the em dash (—) with spaces; it is the manuscript's dominant pattern.
- Curly quotes and apostrophes in the final output; the build converts straight quotes automatically, so the Markdown stays plain.
- Double quotes for speech and quoted terms; single quotes only inside double.
- Ellipsis as a single character (…).
- One space after full stops.
- Use the times sign (×) only in formulas; arrows (→) for sequences and the case-study name.

## 5. Chapter structure

**Book structure (settled):** Part One — Getting Started (Foreword, How to Use, Create Your Plan) · Part Two — The Flow7 Data Migration System (Chapters 1–7) · Part Three — After the Move (Know the Business, ending with *A Final Word*) · Appendix A — The Terminology Translator · Appendix B — The Flow7 Templates. No Introduction; no glossary.

**Settled pattern for step chapters (Chapters 1–7)**, in this order:

1. Chapter label and title, with the subtitle "*Step N of the Flow7 Data Migration System — [step name]*"
2. Promise line (bold)
3. Where You Are in Flow7 (progress strip + one or two sentences)
4. In this chapter you will… (no more than five items)
5. What you'll need (named items from earlier steps)
6. Why This Matters
7. What You Are Actually Doing
8. Key things to get right
9. From the Field (with an italic headline: *Sage 50 → Sage X3: …*)
10. Your Checklist (the essentials, tagged with checklist refs; the full list is in the Excel)
11. Worked example (📋 box)
12. Your Turn (numbered exercises, each ending **Where to record it:** naming the step template), then the 📄 Your template box
13. What you have achieved in this chapter
14. You're Ready to Move On When… (the STOP/GO gate, no more than six items), then **Next:**
15. ▶ Know the business signpost

**Headings (settled, copy-edit 1):** the fixed section names are used exactly as written above, in every chapter — their mixed capitalisation is part of the pattern and is not "corrected". Exercise headings are in Title Case (*Exercise 2.1 — The 20-Record Spot-Check*). Other section headings are in sentence case.

**Lists — keep them light (decided 25 Oct 2026):** the reader should never face a massive checklist on the page. The full task list lives in the Excel Project Plan Checklist; the book shows only what helps the reader act now. Each step chapter has three clearly different lists — *Your Checklist* (the essential tasks, short, pointing to the Excel file for the rest), *Your Turn* (practice on the page) and the *STOP/GO gate* (no more than six items). The critical edit trims each chapter to this.

**Signposting system (approved 25 Oct 2026):** see `editorial/reader-flow-and-critical-edit.md` §4 — fixed chapter opener, running heads, recurring box types, distinct list styles.

**Checklist and gate format**: *Proposed* — every checklist as a three-column table (Ref · Task · ☐) and every gate as a two-column table (Gate · ☐), so the printed book has boxes to tick. Done in the critical edit.

**Exercises (decided 27 Oct 2026 — replaces the worksheet pack):** each *Your Turn* is a few short questions, answered straight into the matching Flow7 step template (or, where none fits, the reader's project folder). Each exercise ends with a **Where to record it:** line. There is no worksheet pack and no write-in space in the book.

**Exercises**: numbered by chapter — Exercise 1.1, 1.2…; Planning Exercise 1–3 in *Create Your Plan*; Exercise KB.1 in *Know the Business*; Exercise A.1 in Appendix A.

**Figures**: numbered by chapter in Part Two (Figure 3.1); unnumbered in named chapters.

## 6. Markup conventions in the Markdown files

| Marker | Meaning |
|:-|:-|
| `{{write-in}}` | A full-width writing line for the reader |
| `{{write-in-short}}` | A short writing line |
| `{{write-in-box}}` | A ruled box of several lines |
| `{{figure: id \| caption}}` | Where a figure goes; the id matches `editorial/figure-list.md` |
| `> 🔑 **Key idea…**` | Key idea box (may carry a title: *Key idea — …*) |
| `> 👁 **Watch out.**` | Trap or legal point |
| `> 📋 **Worked example — …**` | Worked example (real, or *illustrative scenario*) |
| `> ▶ **Know the business.**` | End-of-chapter signpost |
| `> ↩ **Tracking back.**` | Go back to an earlier step |
| `> 📄 **Your template.**` | Which template to open and where to download it |
| `{{progress: N}}` | The seven-step "you are here" strip in the chapter opener. `{{progress: foundation}}` (Create Your Plan) shows the strip with no step filled and the Foundation marked. |

## 7. Sources and citation

- Case-study extracts are attributed with the full URL on first citation in the book.
- **Checklists summarise (decided 25 Oct 2026):** the book shows the essential actions in plain words, tagged with their checklist reference (1A, 1B…). The full, word-for-word task list lives in the Excel Project Plan Checklist and the step templates — the book points readers to those resources. Simplicity is the rule.
- **Worked examples:** real (anonymised) where available; otherwise an *illustrative scenario*, clearly labelled, that can be swapped for real client data later.
- **Templates:** the step templates are separate files from the Project Plan Checklist. Each chapter's *Your template* box names the exact files.
- No external statistics (decided 27 Oct 2026: no Introduction, no statistics).
- **References (decided 25 Oct 2026):** Stuart's own material (the Sage 50 → Sage X3 case study, Flow7 templates, checklists and workbooks) is covered once, in a single "About the sources" note in the front matter — no footnotes. External sources (e.g. the Forbes/McKinsey statistics) get a numbered note in the text and a full entry in a References appendix at the back.

---

## Open decisions for Stuart

| # | Decision | Options | Recommendation |
|:-|:-|:-|:-|
| D1 | **References.** | **Decided:** own sources → one "About the sources" note; external sources → numbered note + References appendix | Done — see §7 |
| D2 | **Workbook or handbook?** | **Decided:** "handbook" for the book; "Workbook" only for the Flow7 Migration Workbook (the combined Excel file) | Done |
| D3 | **Chapter numbering.** | **Decided:** three parts. Part One — Getting Started (Foreword, How to Use, Create Your Plan: named, not numbered). Part Two — The Flow7 Data Migration System (Chapters 1–7, chapter = step). Part Three — After the Move (Know the Business: named). Then appendices. | Done — structural pass 1 |
| D4 | **Cooking analogy.** | **Decided:** dropped — the three references removed | Done (pass 1) |
| D5 | **Case-study product count.** | **Decided:** 7,500+ everywhere | Done — apply in copy-edit pass |
| D6 | **Section order.** | **Decided:** How to Use fixed to match the chapters | Done — critical edit How to Use |
| D7 | **Third-person self-references.** | **Decided:** first person throughout; attribution in *About the Sources* | Done — critical edit |
