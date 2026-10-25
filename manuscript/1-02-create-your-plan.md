# Create Your Plan

---

**Every successful migration needs a clear plan — written down and agreed by the people who will do and manage the work — before a single record is moved.**

---

## Where You Are in Flow7 — Foundation

{{figure: fig-plan-01 | Flow7 flow diagram with Foundation highlighted}}

This is the start. It sits ***before*** the seven numbered steps of the Flow7 Migration System. It is where you sense-check and outline the project at a high level.

**In this chapter you will…**

- Run a short readiness assessment to sense-check your reasons, timeline and budget at a high level
- Get to know the Flow7 Project Plan — the seven steps ahead, and where task ownership and dates sit
- Write a simple, one-sentence migration aim: what you are moving, why, what success looks like, and what is out of scope
- Confirm who signs the plan off, note the top risks the assessment surfaces, and flag your privacy and compliance position

---

## What you'll need before starting

- Tool: The *Are You Ready?* Data Migration Checker
- Spreadsheet: The Flow7 Data Migration Project Plan Checklist

---

## Why This Matters

Before you do anything else — before you book a demo, before you speak to a supplier, before you touch a spreadsheet — give yourself a good foundation: a written plan.

A migration that starts with a clear plan moves forward differently to one that does not. Decisions get made deliberately. The people doing the work know what they are doing and why. Business owners and managers know where responsibilities sit — more on this later.

The work is not glamorous, and it can feel a bit boring. It is tempting to dive straight into the data, or to start poking around the new system — I know, I have done exactly that. But don't, not just yet. Work this foundation chapter first.

---

**Know the Business — and Its Language**

A migration is never only a data job. Underneath it, you are learning a business — how it actually works, and the words its people use. Both matter, and both tend to bite hardest when you least expect them. Whatever your role, whether in the business already or a new data specialist the involvement in the project will increase your knowledge and business understanding.

Most advice says "understand the business before you start." That is true, and it is also impossible to do fully on day one, because most of how a business works is not written down — it lives in habits, in workarounds, and in different people's  heads. What you can do is carry the question from the very start: for everything you touch, ask what the business calls it, what the system calls it, and what it actually is.

That last point — terminology — is where the trouble usually shows. The same object often has three names: the person on the shop floor calls it a "job", the old system labels it a Works Order, the new system stores it as a Manufacturing Order. All one thing. If whoever maps the fields later does not know that, you get duplicate records, broken links, or data quietly dropped on the floor.

The worst version is inverted logic. In a real Flow7 mapping, a source field OPTEDIN = "Yes" mapped to a target field Email Opt Out = "False" — the same fact, reversed. Map that carelessly and you opt an entire database back in, breaching GDPR. Terminology is not a cosmetic problem; it is where a small misunderstanding becomes an expensive one.

So from Step 1 onward, keep a running note — your Terminology Translator: our word / the system's word / what it really is. Start it early, add a row every time a name does not obviously match, and hand it to whoever runs the system next. The full three-language reference — across sales, purchasing, manufacturing, logistics, finance, eCommerce and CRM, plus the "false friends" (Order, Account, CoA, Invoice) that cause the most trouble — is in Appendix E: The Terminology Translator. Keep it open beside you from planning through to go-live.

Carry this as a lens, not a step. You will not learn the business in one sitting. Step 1 shows you where knowledge really lives; Step 2 shows what the business has tolerated; Step 3 forces it to decide what is true; Steps 4 and 5 expose where its language collides with the new system. Note what each step teaches you — the closing chapter, *Know the Business*, is where you consolidate it.

## What You Are Actually Doing

This first stage is the foundation of the entire Flow7 framework. It happens before the seven numbered steps begin — before you inventory your data sources, before you assess data quality, before you think about field mapping.

Before any of that, you need a plan. In practice, that is three short pieces of work:

1. Run a short readiness assessment. This surfaces the high-level factors that can shape or derail your migration — your reasons, timeline, budget, initial data volume and quality.
2. Get to know the Project Plan. Open the Flow7 Project Plan Checklist and read through Steps 1 to 7. You are not completing it — you are getting a feel for the whole journey and where the work, the dates and the ownership sit.
3. Write a simple Outline Migration Statement. This is the core document you use to keep the project on track: what you are moving, why, what success looks like, and what is out of scope.

---

## Key things to get right

Five disciplines do most of the work at this stage. Get them in place and the rest of the project moves on solid ground.

1\. Write the aim down in one sentence. A short, clear statement of what this migration must deliver, agreed by the person who signs it off. The sentence is the test for every later decision: *does this serve the aim, or has it crept past it?*

2\. Identify your team and confirm who signs off. You do not need to allocate every task yet. The Flow7 Project Plan carries an owner against each task, and ownership is assigned step by step as you work through it. What you need now is to know who is involved and who has the authority to sign the plan off.

3\. Sense-check the timeline backwards from go-live. Pick the date that matters and work back through the seven steps. At this stage you are checking whether the *shape* of the timeline is realistic — not building a detailed schedule. The detail firms up as you work the plan.

4\. Discuss your likely risks before you meet them. Think through what could go wrong for your business and divert your resources — an IT failure, a key person unavailable, a supplier delay — and note a sensible response for each. The readiness assessment will help surface these.

5\. Confirm your compliance position early. If personal data is involved, the privacy and GDPR position needs to be signposted before any records are pulled. Fuller compliance work is covered under Step 2 — Data Assessment.

---

## From the Field

**A readiness assessment highlights likely risks early, before the project even starts.**

And whatever you do, set your *own* business timeline. Don't take the timelines suggested by system vendors or implementation partners at face value — they run to their own schedules, and those schedules rarely include the time it takes to get your data sorted or to work around your staff's availability.

On the Sage 50 to Sage X3 migration that runs through this book, the original plan was "two to three months, max" — set before any proper assessment, on the assumption that a move within the same software family must be simple. It was not. The project also ran alongside an implementation partner working through their own project plan. Their timeline was theirs; the data work was mine. Knowing that difference from the outset is what keeps a project honest about how long it will really take.

---

## Your Turn

### Planning Exercise 1 — Conduct your readiness assessment

Try the *Are You Ready?* Data Migration Checker. Keep the result — you will use it as a reference for your Outline Migration Statement, and it flags the high-level factors (reasons, timeline, budget, data quality) that shape your project.

### Planning Exercise 2 — Write your Outline Migration Statement

**This is a five-minute exercise. Do it now, before you move on.**

---

**Our migration is:**

*(e.g. "Moving our customer and sales data from [System A] to [System B].")*

{{write-in}}

---

**The reason we are doing it is:**

*(e.g. "The current system licence ends in March" or "We need better reporting across the business.")*

{{write-in}}

---

**We will know it has worked when:**

*(e.g. "All customer records are visible in the new system, the team can raise invoices, and no data has been lost.")*

{{write-in}}

---

**What is out of scope:**

*(e.g. "We are not migrating archived records from before 2018" or "Email history is excluded.")*

{{write-in}}

---

**The person who signs this off is:**

{{write-in}}

---

### Planning Exercise 3 — Note your first three risks

**Using what the readiness assessment surfaced, write down the first three things that could go wrong. Don't overthink it — write whatever comes to mind first.**

| **#** | **Risk** | **Likelihood (H/M/L)** | **Impact (H/M/L)** | **Who owns this?** |
|:-:|:-:|:-:|:-:|:-:|
| **1** |   |   |   |   |
| **2** |   |   |   |   |
| **3** |   |   |   |   |

### Planning Exercise 4 — Get to know the full Project Plan Checklist

The full project plan tasks live in the Flow7 Data Migration Project Plan Checklist — an Excel workbook that accompanies this handbook. It contains all the task rows, status tracking, date columns and owner fields for every step.

Scan the milestones and tasks to get a feel for the areas you will manage during the migration. It is a crucial management document — you don't need to complete it now, just to know what is ahead.

---

## What you have achieved in this chapter

You have sense-checked whether you are ready to migrate, seen the whole journey through the seven steps, and written a simple, agreed migration aim with a named sign-off. Your scope is clear, the top risks and your compliance position are flagged, and everyone involved knows what this migration must deliver and roughly its duration. Everything in Chapters 1 to 7 builds directly on this foundation.

---

## Stop/Go Gate

## You're Ready to Move On When…

**You are ready to move from planning to Step 1 — Knowing Your Data Sources — when all of the following are true. Do not proceed until every item can be ticked honestly.**

| **Gate** | **✓** |
|:-|:-:|
| **A written Outline Migration Statement exists — aim, reason, success and scope — and is agreed by the person who signs it off** | ☐ |
| **You have run the readiness assessment and noted the risks and timeline it surfaced** | ☐ |
| **You have opened the Flow7 Project Plan Checklist and understand the seven steps ahead** | ☐ |
| **Your team is broadly identified and who signs off is confirmed** | ☐ |
| **The privacy and compliance position has been flagged (where personal data is involved)** | ☐ |
| **The plan documents are stored where the whole management team can access them** | ☐ |

**If you cannot tick all of these, go back and finish your planning before moving on.**
