# Reader Flow, Signposting and the Critical Edit

Proposal · 25 October 2026 · for discussion with Stuart

Goal: a handbook that is very easy to follow, where the reader always knows where they are, what to do next, and where to find the tool for it. The structure is settled now so that the design stage (layout, colour, icons) has a clear system to dress.

---

## 1. The revised editorial sequence

| # | Phase | Who | Status |
|:-|:-|:-|:-|
| 1 | Consolidate from Drive | Claude | Done |
| 2 | Structural pass — parts, numbering, cross-references | Claude, Stuart approves | Done, awaiting approval |
| 3 | **Critical edit — chapter by chapter, rewriting together** | Stuart and Claude | **New** |
| 4 | Copy-edit — grammar, consistency, style sheet | Claude, Stuart approves | Moved after the critical edit |
| 5 | Design — layout, colour, icons, figures | Together | |
| 6 | Proofread — on the laid-out pages | Claude, Stuart approves | |
| 7 | Originality check, front matter, production files | Claude + external checker | |

The copy-edit moves after the critical edit. Otherwise we would tidy sentences that are about to be rewritten. The 33 copy-edit items are kept; many will disappear in the rewrite.

## 2. How the critical edit works

For each chapter:

1. **Critique.** Claude reads the chapter as a first-time reader and sends a short verdict:
   - does it keep its promise ("In this chapter you will…")?
   - what is repeated, missing or in the wrong place?
   - where would a reader get lost?
   - what could be cut without losing anything?
2. **Proposed rewrites.** Each one is shown as before → after, a passage at a time, with the reason for the change.
3. **Your call.** For each proposal: accept, change it, or rewrite it yourself. Anything that needs talking through, we talk through.
4. **Approve.** The agreed chapter goes onto its own branch, and you approve it before it is merged.

Ground rules:
- your voice stays — first person, plain English, practical
- Claude proposes and you decide
- nothing new goes in unless it is real or labelled as an illustrative scenario
- cut before adding

Suggested order:
- **Pilot: Chapter 1.** It sets the standard for the rest.
- **Chapters 2–7.**
- **Create Your Plan, How to Use, then the Foreword and the Introduction.** These describe the chapters, so they are rewritten after the chapters are settled.
- ***Know the Business* last.**

Critiques can be prepared while you're away; the rewriting happens together, and that works by phone.

## 3. What the manuscript does now — flow problems found while consolidating

Real findings, with locations, for the critical edit to resolve.

**The recap grows with every chapter.** "Where You Are in Flow7" retells every earlier chapter. Chapter 6 lists Chapters 1–5 one by one, and Chapter 7 lists Chapters 1–6. By the end, readers are re-reading the book's contents page in prose. *Fix: one sentence plus a visual "you are here" strip (see §4).*

**The same lessons appear in several chapters.** Readers notice the repetition and start skimming, and then miss what is new.
- *"Get access to the front end"* appears in Chapter 4 (twice), Chapter 6 (twice) and Chapter 7.
- *"Test the import templates first"* appears in Chapter 4 (twice) and Chapter 6.
- *The 1,000-record display limit* appears in Chapter 4, Chapter 6 (twice) and Chapter 7.
- *The loading order* appears in Chapter 4 as prose and in Chapter 7 as a numbered list — and again in Chapter 7's worked-example placeholder.

*Fix: teach each lesson once, in the step where it belongs, and refer back to it elsewhere.*

**Each chapter makes the same point twice internally.**
- Chapter 3 makes its "Excel is fine as a master" point in a highlighted box and again as Key thing #1.
- Chapter 5's Key things repeat the subsections on picklists and real sample data that come just before them.

*Fix: Key things becomes a short summary list, or the earlier subsections shrink.*

**Chapters open in four different ways.**
- Chapter 1: italic intro, then a quote between rules.
- Chapter 2: italic intro, then a bold hook.
- Chapter 3: a bold quote.
- Chapter 5: a quote signed by you.

*Fix: one fixed chapter opener (see §4).*

**Three tick-lists per chapter, with unclear roles.** Your Checklist, Your Turn and the Gate all look like lists of boxes. A reader can't tell at a glance which one is the real work, which is practice, and which proves the step is done. *Fix: give each one a distinct name, purpose line and look.*

**"Tracking back" is said in passing, inconsistently.**
- Chapter 3 has a long paragraph beginning "I will mention this a few times…".
- Chapter 4 has "A CLASSIC EXAMPLE OF TRACKING BACK!!".
- Chapter 6 has Key thing #4.

It's one of the method's most reassuring ideas. *Fix: a recurring "Tracking back" signpost that names the earlier step to return to.*

**Template pointers vary.**
- "Now Go to the Full Template" (Chapter 1, as a heading).
- "Then take it to the template(s)" (Chapters 3 and 4, in bold).
- Downloads at spdata.co.uk (Chapter 5) and at stuartparkins.com (everywhere else).

*Fix: one standard "Your template" box, naming the file and one web address.*

**Part One is a long run-up.** The Foreword, the Introduction (still to come) and How to Use all come before the reader does anything. *Question for the critical edit: merge the Introduction into the Foreword, or keep the Introduction to one page?*

## 4. Proposed signposting system

Every element below is tagged in the manuscript now, so the design stage can give each one its layout, colour and icon without touching the text.

**Chapter opener (the same in all seven step chapters):**
- step badge and a seven-dot progress strip, with the current step filled
- chapter number and title
- a one-line promise (what you'll have when you finish)
- In this chapter you will… (no more than five items)
- What you'll need (from earlier steps, by name)

**On every page:**
- a running head such as "Step 3 of 7 · One Version of the Truth"
- in print, coloured thumb tabs on the page edge, one position per step, so a reader can flip straight to a step
- in the PDF and web versions, clickable cross-references and a persistent contents panel

**Recurring boxes.** One look each, explained once in a key in How to Use:

| Box | Job | Replaces |
|:-|:-|:-|
| Key idea | The one thing to remember | ▶ boxes |
| Plain English | Definition of a term on first use | "Plain-English box" |
| Watch out | A trap or legal point (e.g. GDPR) | ⚠️ boxes |
| From the Field | The Sage 50 → Sage X3 story at this step | case-study sections |
| Worked example | A filled-in template row or sheet | ▶ worked example |
| Tracking back | "Found a gap? Go back to Step N" | scattered asides |
| Your Turn | Practice on the page, with write-in space | exercises |
| Your template | Which file to open and where to get it | four different phrasings |
| Know the business | What this step taught you about the business | new signposts |
| STOP/GO gate | Proof the step is done | gate tables |

**The three lists, made distinct:**
- **Your Checklist:** "the work — tracked in the Excel checklist".
- **Your Turn:** "practice it here".
- **STOP/GO gate:** "don't move on until every box is ticked". The gate always ends the chapter, styled as a stop sign that turns into a go.

**Book-level navigation:**
- a one-page Flow7 map at the front, showing all seven steps, what each produces and where it is in the book
- a full checklist and template index in the appendices (already planned as Appendix A/B)

**A design note to settle later.** Your Flow7 badges use red for Steps 1–5, amber for 6 and green for 7. In a book titled *Don't Let a Data Migration Panic You*, five red chapters may read as "danger". Worth considering a calm per-step palette for the book, keeping red, amber and green only for the STOP/GO gate.

## 5. Decisions needed

1. Approve the phase order in §1, with the critical edit before the copy-edit.
2. Approve the signposting system in §4 as the structure the design will dress, adjusting anything you'd like.
3. Should the pilot critique of Chapter 1 start now?
