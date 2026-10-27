# Critical Edit — Chapter 7: Go Live

27 October 2026 · branch `critical-edit-ch7` (built on `critical-edit-ch6`) · checked against the Excel checklist (Step 7) and the case study

## Verdict

The content is right; the shape is the problem. These parts carry the chapter:
- "go-live is not the finish line";
- the reasoning that most go-live trouble comes from having no plan for *afterwards*;
- the full Sage X3 loading order, which Chapter 4 now points forward to;
- the rollback trigger exercise.

The weaknesses:
- **A 40-row checklist** — the opposite of your "don't overload readers" rule.
- **Four phases in the text, five in the checklist** (edit log X11). The text skips 7C, the go/no-go decision, which is the most important moment of the step.
- **Repetition.** Front-end access, the 1,000-record limit and the loading-order reminder were all taught in Chapters 4 and 6. "Why This Matters" re-lists Steps 1–6.
- **The worked-example placeholder** (edit log M4) is still empty.
- **Two issue logs.** Exercise 7.3 asks for a new log with an H/M/L severity scale, while Chapter 6 already set one up with None/Minor/Serious/Critical.
- **"Looking Further"** sits after the gate, so this is the only step chapter that doesn't end on its STOP/GO gate.

Words: about 3,810 → 2,500 (the worked example adds about 200).

## Proposals

**P1 — Standard opener.** The subtitle matches Chapters 1–6. Where You Are becomes two sentences plus the progress strip. "What you'll need" names the step each item comes from.

**P2 — Why This Matters rewritten around your strongest point:** go-live trouble comes from having no plan for the hours and weeks after the load. The recap of Steps 1–6 goes.

**P3 — Five stages, matching 7A–7E** (fixes X11). The go/no-go decision (7C) is now described in the text: who confirms what, and that the rollback plan stays to hand until the decision is recorded. "Production system" becomes "live system".

**P4 — Key idea box:** "Go-live is not the finish line. It is the start of the validation period." This was the epigraph in your Google Doc draft; it now earns a box instead of citing an internal working document.

**P5 — Key things: five → four.** "Watch the front end" is cut (taught in Chapter 4). The loading-order paragraph becomes a short *Watch out* box: run the order, don't improvise it. "Compare counts at every stage" gains a reason: a difference caught after one load is a quick fix; found three loads later, it is a long night.

**P6 — From the Field tells only the go-live story.** The numbered loading order stays here, as agreed in Chapter 4 (P4). Cut: the 1,000-record chunking (Chapters 4 and 6) and the front-end pro tip (Chapter 4). Kept, in your voice: counts after every load, and "the loading plan was the weekend's communication plan". The supplier-ID round trip is now one sentence that refers back to testing.

**P7 — Checklist: about 40 rows → 7 essentials,** at least one for each of 7A to 7E. The full list stays in the Excel checklist.

**P8 — Worked example: illustrative scenario** (closes M4). The kitchenware wholesaler from Chapters 1 and 4 goes live: a seven-load plan with dependencies, expected and loaded counts, and who checks each load. On the night, two customers are short after load 2 (new accounts with no postcode, set up after the last test load). It is fixed before load 3 because counts were checked after each load. It ties back to Chapter 4's bin-location finding, and the numbers add up (opening balances = customers + suppliers).

**P9 — Your Turn: three exercises → two.** Exercises 7.1 (loading plan) and 7.2 (rollback trigger) become short numbered questions pointing to Worksheets 7.1 and 7.2. Exercise 7.3 (a new issue log) is dropped: the template box now says to keep using the Step 6 UAT Testing List as the go-live issue log. That keeps one log and one severity scale through testing and go-live. The worksheet pack falls from 15 to 14.

**P10 — Gate: 9 items → 6,** matching the rule for every chapter. "Formal go/no-go recorded" gets its own line.

**P11 — "Looking Further" moves** to the end of *Know the Business*, as a short closing section with a *Your template* box for the *7 Steps for Any Data Project* sheet. Every step chapter now ends: gate → **Next** → Know-the-business signpost.

## Not changed

- The 14-item Sage X3 loading order (renumbered 1–14; your draft started at 0).
- The four-week stabilisation period ("duration may vary") and the old-system close-down plan.
- The Know-the-business signpost wording.

## Questions for you

1. **Drop Exercise 7.3?** I've folded it into the Step 6 UAT Testing List. If you'd rather keep a separate go-live log, I'll restore it using the Step 6 severity scale, not H/M/L.
2. **Worked-example numbers.** The wholesaler's counts are invented, and the example is labelled as an illustrative scenario. Happy with that, or would you rather use an anonymised loading plan from a real engagement?

## Answers (27 Oct 2026)

1. Exercise 7.3 dropped — the Step 6 UAT Testing List carries on as the go-live issue log. Agreed.
2. Invented, labelled numbers are fine for now. Stuart has a real project plan among his templates that could replace or support the worked example later (edit log M13).
