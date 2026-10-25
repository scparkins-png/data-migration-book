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
| The planning chapter | **Create Your Plan** | Before You Start (old name, still in Ch 4 and Ch 5) |
| Master data | master set / Master Data Set (when it's the named artefact) | master data source, data master (except Step 3's title) |
| go-live | "go-live" as a noun or adjective ("the go-live window"); "go live" as a verb ("when you go live") | Go Live mid-sentence (keep capitals only for the Step 7 name) |
| Step references | Step 1 … Step 7; sub-steps 1A, 4B, 5C3 etc. | step one, Step One |
| Chapter references | Chapter 4, Chapter 11 (numerals) | chapter four, Ch. 4 |
| UAT, ETL, BOM, SKU, GRN | Spell out on first use in each chapter, then abbreviation | plural with apostrophe (BOM's) |
| Bills of Materials | Bill of Materials (singular), Bills of Materials (plural) | Boms, BOMS |
| Websites | stuartparkins.com | spdata.co.uk (still in Ch 8), www. prefix |
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

**Settled pattern for step chapters (Chapters 4–10)**, in this order:

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

Note: *How to Use This Handbook* lists "In this chapter you will…" **before** "Where you are in Flow7"; every chapter does the reverse. One of them needs to change (open decision D6).

**Headings**: one H1 per chapter (the title). Section headings in Title Case as above. *Proposed: standardise "Why This Matters" etc. — current chapters mix "Why this matters" and "Why This Matters".*

**Checklists and gates**: *Proposed* — every checklist as a three-column table (Ref · Task · ☐) and every gate as a two-column table (Gate · ☐), so the printed book has boxes to tick. Currently Chapters 6–9 use bullet lists.

**Exercises**: numbered by chapter — Exercise 4.1, 4.2… (*Proposed*; Chapter 3 and Chapter 4 currently both use 1.1–1.3).

## 6. Markup conventions in the Markdown files

| Marker | Meaning |
|:-|:-|
| `{{write-in}}` | A full-width writing line for the reader |
| `{{write-in-short}}` | A short writing line |
| `{{write-in-box}}` | A ruled box of several lines |
| `{{figure: id \| caption}}` | Where a figure goes; the id matches `editorial/figure-list.md` |
| `> ▶ **…**` | A callout box (worked example, key idea) |
| `> 💡`, `> 📋`, `> ⚠️` | Tip, worked-example placeholder and caution callouts |

## 7. Sources and citation

- Case-study extracts are attributed with the full URL on first citation in the book.
- Checklist items are verbatim from the Flow7 Data Migration Project Plan Checklist.
- Forbes/McKinsey migration statistics appear in the Introduction only, with a transparent editorial footnote; the McKinsey attribution is removed. Primary source still to be verified.
- How references are presented is an open decision (D1).

---

## Open decisions for Stuart

| # | Decision | Options | Recommendation |
|:-|:-|:-|:-|
| D1 | **References.** Pass 2 replaced per-chapter References with one "About the sources" note. Chapter 11 and Appendix E (written later) have their own references again. | (a) single "About the sources" note; (b) per-chapter references | (a) — it's what you chose in Pass 2 and keeps chapters clean; fold Ch 11 and App E citations into it |
| D2 | **Workbook or handbook?** The text uses "workbook" 16 times and "handbook" 7 times. | handbook / workbook | "handbook" for the book (it's in the How to Use title); "workbook" only for the Excel checklist |
| D3 | **Chapter numbering.** Front matter is numbered as Chapters 1–3, so Step 1 is Chapter 4. Create Your Plan says "Chapters 1 to 7" meaning the steps; Ch 4 says data quality "comes in Chapter 2". | (a) number only the step chapters 1–7 and leave front matter unnumbered; (b) keep 1–11 and fix the cross-references | (a) — chapter number = step number is far easier for readers |
| D4 | **Cooking analogy.** Chapters 5, 9 and 10 refer to "the cooking analogy that runs through Flow7", but it is never introduced. | introduce it in Create Your Plan or How to Use / remove the references | Introduce it briefly in How to Use (two or three sentences) |
| D5 | **Case-study product count.** 7,000 in Chapters 5–6, 7,500+ in Chapter 9. | which is right? | Your call — check against the case study |
| D6 | **Section order.** See §5 above. | Fix How to Use / fix every chapter | Fix How to Use (one edit instead of seven) |
| D7 | **Third-person self-references.** Chapters 8, 9 and 11 open From the Field with "documented by Stuart Parkins", and Chapter 8's opening quote is signed "— Stuart Parkins". | keep as source attribution / rewrite in first person | First person in the text; keep the formal attribution in the source note |
