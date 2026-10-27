# Create Your Plan

### *The Foundation — before the seven steps of the Flow7 Data Migration System*

**Every successful migration needs a clear plan — written down and agreed by the people who will do and manage the work — before a single record is moved.**

## Where You Are in Flow7

{{progress: foundation}}

This is the start. It sits *before* the seven numbered steps, and it is where you sense-check the project and outline it at a high level.

## In this chapter you will…

- Run a short readiness assessment to sense-check your reasons, timeline and budget
- Get to know the Flow7 Project Plan Checklist — the seven steps ahead, and where owners and dates sit
- Write your Outline Migration Statement: what you are moving and why, what success looks like, what is out of scope, and who signs it off
- Note your first risks and flag your privacy and compliance position

## What you'll need

- The *Are You Ready?* Data Migration Checker
- The Flow7 Data Migration Project Plan Checklist (Excel)
- An hour with the person who will sign the plan off

## Why This Matters

Before you do anything else — before you book a demo, before you speak to a supplier, before you touch a spreadsheet — give yourself a good foundation: a written plan.

A migration that starts with a clear plan moves differently from one that does not. Decisions are made deliberately. The people doing the work know what they are doing and why. Business owners and managers know where responsibility sits.

This work is not glamorous, and it can feel a bit boring. It is tempting to dive straight into the data, or to start poking around the new system — I know, I have done exactly that. But don't, not just yet. Work through this chapter first.

## What You Are Actually Doing

Three short pieces of work:

1. **Run a readiness assessment.** It brings out the high-level factors that can shape or derail your migration — your reasons, timeline, budget, and a first view of your data's volume and quality.
2. **Get to know the Project Plan Checklist.** Open it and read through Steps 1 to 7. You are not filling it in yet — you are getting a feel for the whole journey, and for where the work, the dates and the owners sit.
3. **Write your Outline Migration Statement.** This is the document that keeps the project on track. It starts with a one-sentence aim — what you are moving and why — and adds what success looks like, what is out of scope, and who signs it off.

## Key things to get right

Five disciplines do most of the work at this stage.

**1. Write the aim in one sentence.** A short, clear statement of what this migration must deliver, agreed by the person who signs it off. That sentence becomes the test for every later decision: *does this serve the aim, or has it crept past it?*

**2. Know your team and who signs off.** You do not need to allocate every task yet — the Project Plan Checklist carries an owner against each task, and you assign them step by step. What you need now is to know who is involved, and who has the authority to sign the plan off.

**3. Sense-check the timeline backwards from go-live.** Pick the date that matters and work back through the seven steps. You are checking whether the *shape* of the timeline is realistic, not building a detailed schedule. The detail firms up as you work the plan.

**4. Think about your risks before you meet them.** What could go wrong for your business, and how would you respond — an IT failure, a key person unavailable, a supplier delay? Note a sensible response to each. The readiness assessment will help bring these out.

**5. Flag your compliance position early.** If personal data is involved, the privacy and GDPR position needs to be signposted before any records are pulled. The fuller compliance work comes in Step 2.

## Know the Business — and Its Language

A migration is never only a data job. Underneath it, you are learning a business: how it actually works, and the words its people use. Whatever your role — inside the business already, or a data specialist brought in — the project will teach you more about the business than you expect.

Most advice says "understand the business before you start". That is true, and impossible to do fully on day one, because most of how a business works is not written down. It lives in habits, in workarounds and in people's heads. What you *can* do is carry one question from the start. For everything you touch, ask: what does the business call it, what does the system call it, and what is it really?

Terminology is where trouble usually shows. The same thing often has three names: the shop floor calls it a "job", the old system calls it a Works Order, the new system stores it as a Manufacturing Order. If whoever maps the fields later does not know they are one thing, you get duplicates, broken links, or data quietly dropped.

> 👁 **Watch out.** The worst version is inverted logic. On one of my own mapping projects, a source field *OPTEDIN = "Yes"* had to map to a target field *Email Opt Out = "False"* — the same fact, reversed. Map that carelessly and you opt an entire database back in to marketing, in breach of GDPR. Terminology is not cosmetic; it is where a small misunderstanding becomes an expensive one.

So from Step 1 onwards, keep a running note — your **Terminology Translator**: *our word / the system's word / what it really is*. Add a row every time a name does not obviously match, and hand it to whoever runs the system next. The full reference, including the "false friends" that cause the most trouble, is in **Appendix A**.

> 🔑 **Key idea.** Carry this as a lens, not a step. You will not learn the business in one sitting. Each step will teach you something about it — note what you learn as you go, and you will pull it together in the closing chapter, *Know the Business*.

## From the Field

### *Sage 50 → Sage X3: whose timeline?*

On the Sage 50 to Sage X3 migration that runs through this book, the original plan was "two to three months, max". It was set before any proper assessment, on the assumption that a move within the same software family must be simple. It was not.

The project also ran alongside an implementation partner working to their own project plan. Their timeline was theirs; the data work was mine. Knowing that difference from the outset is what keeps a project honest about how long it will really take.

So set your *own* timeline. Don't take the dates suggested by system vendors or implementation partners at face value. They run to their own schedules, and those schedules rarely include the time it takes to get your data sorted or to work around your staff's availability. A readiness assessment brings these risks out early, before the project has even started.

## Your Turn

### Planning Exercise 1 — Run Your Readiness Assessment

Work through the *Are You Ready?* Data Migration Checker and keep the result. It flags the high-level factors — reasons, timeline, budget, data quality — and you will use it for the next two exercises.

### Planning Exercise 2 — Write Your Outline Migration Statement

A five-minute exercise. Do it now, before you move on. Answer five questions:

1. **Our migration is…** *(e.g. "Moving our customer and sales data from [System A] to [System B].")*
2. **We are doing it because…** *(e.g. "The current system licence ends in March.")*
3. **We will know it has worked when…** *(e.g. "All customer records are in the new system, the team can raise invoices, and no data has been lost.")*
4. **Out of scope is…** *(e.g. "Archived records from before 2018" or "Email history.")*
5. **The person who signs this off is…**

Questions 1 and 2 together are your one-sentence aim.

{{worksheet: P.2 | Outline Migration Statement}}

### Planning Exercise 3 — Note Your First Three Risks

Using what the readiness assessment brought out, write down the first three things that could go wrong. Don't overthink it. For each one, note how likely it is, how much it would hurt, and who owns it.

{{worksheet: P.3 | First three risks}}

> 📄 **Your template.** The *Flow7 Data Migration Project Plan Checklist* (Excel) holds every task for Steps 1 to 7, with status, owner and date columns. Open it now and scan the milestones — you don't need to fill it in yet, just to know what is ahead. The *Are You Ready?* checker and Worksheets P.2 and P.3 are at **stuartparkins.com**.

## What you have achieved in this chapter

You have sense-checked whether you are ready to migrate, seen the whole journey through the seven steps, and written an agreed migration aim with a named sign-off. Your scope is clear, your first risks and your compliance position are flagged, and everyone involved knows what this migration must deliver — and roughly how long it will take.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Your Outline Migration Statement is written — aim, success, scope — and agreed by the person who signs it off | ☐ |
| You have run the readiness assessment and noted the risks and timeline it brought out | ☐ |
| You have opened the Project Plan Checklist and understand the seven steps ahead | ☐ |
| Your team is broadly identified, and who signs off is confirmed | ☐ |
| Your privacy and compliance position is flagged (where personal data is involved) | ☐ |
| The plan documents are stored where the whole management team can reach them | ☐ |

**If you cannot tick every box, finish your planning before you move on.**

**Next:** Chapter 1 — Step 1, Know Your Data Sources.
