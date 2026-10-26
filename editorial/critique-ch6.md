# Critical Edit — Chapter 6: Test Before You Trust

26 October 2026 · branch `critical-edit-ch6` · checked against the Step 6 template help notes and the Excel checklist

## Verdict

This is a solid, well-organised chapter. These parts are excellent:
- "testing a story, not a system";
- the three things that only show up in testing;
- the chain from Step 1 to Step 4 to Step 6;
- the UAT-001 example with its "passed, but…" comment.

The cross-check found **one factual error**: the chapter says "eight standard fields" twice, but your help notes list nine.

The rest is repetition:
- Three of the five Key things (iterate, chunking, front-end sign-off) are told again in full in From the Field.
- "Test the import templates first" and "front-end access" were already taught in Chapter 4.
- The opening recap retells all five earlier chapters.

Words: about 3,170 → 2,280.

## Proposals

**P1 — Nine fields, not eight.** Both mentions are corrected, and the fields are now a numbered list (1–9) so the count is visible. This matches the "Key Fields Explained" section of your Step 6 help notes.

**P2 — Where You Are: two sentences.** The recap of Chapters 1–5 goes.

**P3 — Key things: five → four, plus a *Tracking back* box.** "Iterate without alarm" becomes the chapter's *Tracking back* box, which is where it belongs. "Chunk the data" becomes a general rule ("respect the target's display limits"); the Sage X3 specifics stay in From the Field. "Front-end sign-off" stays, shortened, because Chapter 4 already explained why.

**P4 — From the Field tells only the Step 6 story.** Four short headed paragraphs:
- two environments, two jobs;
- chunking what we could see;
- the loop ran several times;
- proving the new IDs.

Two passages already taught in Chapter 4 are cut: "test the import templates first" and the front-end paragraph. The opening line ("documented by Stuart Parkins") goes, as in Chapter 5.

**P5 — Checklist: 2 + 8 items → 6 essentials.** Your Excel checklist only has 6A1 and 6B1. The book's extra items come from the help notes. The six essentials keep both Excel tasks: process training is in row 2, and daily issue management is in row 5. (Reference catalogue R4 still suggests adding the help-note items to the Excel.)

**P6 — Plain English.** "DEV/UAT/sandbox" becomes "a development, test or 'sandbox' copy". "AR scripts" becomes "accounts scripts". "Goods-receipt" becomes "goods-in".

**P7 — Your Turn → Exercise 6.1 and Worksheet 6.1.** The exercise is now five numbered drafting steps. The tester fields are left blank on the worksheet. Your "the script will write itself" line is kept.

**P8 — Gate stays at 6** and is tightened. The closing line becomes "do not set the go-live date in stone", which ties back to your help notes' point that issues decide whether the date moves.

**P9 — Standard ending:** **Next**, then the signpost. The *Your template* box carries your "consider an Excel version if issues grow" advice.

## Not changed

- The UAT-001 worked example (field labels changed to sentence case only).
- Figure 6.1.
- The UAT Testing List status and severity values (they match the template exactly).
