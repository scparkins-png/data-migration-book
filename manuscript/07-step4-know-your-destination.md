**CHAPTER 7**

# Know Your Destination

## Step 4 — Know Your Target System(s)

**A migration that respects what the target system actually expects — its mandatory fields, its formats, its loading order — imports cleanly first time. That is what this step builds for you.**

## Where You Are in Flow7

You have spent three chapters working on the data you already have. In **Chapter 4** you found every source. In **Chapter 5** you took an honest look at its quality. In **Chapter 6** you pulled the right parts together into one controlled master set — your single source of the truth.

Now you turn around and look the other way. Step 4 is about the system you are moving *into* — what it expects, what it will refuse, and how the people who use it will actually work once the data lands.

Now I can hear a few shouts, why not do this first? Don't get sidelined by the new shinny system at the start, it's demo data sets will work a charm, it's workflows and document examples will work, but it's not your Data!

You need to be aware of your data,  processes and terminology first. Armed with that you will be better placed looking at the new system. Remember

## In this chapter you will…

- Get verified admin and user access to every system that will receive migrated data
- Document the destination, area by area — fields, formats, validation rules, limits
- Run sample imports and measure how long they take
- Export each area with field titles, ready for mapping in Chapter 8
- Document the user processes that will be tested in Chapter 9

## What you'll need from earlier chapters

- Your Master Data Set from Chapter 6
- Your Step 1C Business Process List — used as the starting point for the user-process side
- Working admin and user accounts in the target system

## Why This Matters

Knowing your destination as well as you know your source is what makes the migration import cleanly the first time. Every new system has rules the old one never had — fields it insists on, formats it expects, validation it applies, loading orders it requires. None of that is a fault; it is simply how the new system works. Discover it now, on purpose and in advance, and each of those rules becomes a documented requirement your mapping in Chapter 8 will satisfy. Discover it during the migration window, and each one becomes an emergency.

There is a second reason this step matters, and it is easy to underrate. A migration is not only about data arriving in the right boxes. It is about people being able to do their jobs in the new system the morning after. Step 4 therefore has two halves: knowing what the system will *accept* (the data side), and knowing how users will *work* in it (the process side). Get both, and your testing in Chapter 9 has something solid to test against. Get only the first, and clean data ends up sitting in a system nobody knows how to operate.

## What You Are Actually Doing

Flow7 splits Step 4 into two sheets, and they answer two different questions.

**4A — The Summary Target Sheet (the data side).** This is your structured record of the destination system itself. At the top you capture the basics of the system: its name, version or build, how you access it (URL or login), where the help documentation lives, and a note of its data schema. Then, for each target area or module — products, customers, orders, finance, and so on — you work across a set of columns and record what you find:

- **Process / Dept.** — which business process or department this area serves.
- **Sample Data?** — have you got sample data for this area? (Yes / No / To Import.)
- **Import Check?** — have you actually tested importing into it, and how long did it take? (Yes / No, with the time.)
- **User Process Docs?** — is there documentation for how users work in this area? (Yes / No, with the file.)
- **Reports** — what reporting will this area need, with any notes.

Underneath those columns sit the activities that fill them in. Get proper access to the system. Check each area against the real business processes. Look for sample data. Load those samples to test the import and gauge its complexity. Export data out *with its field and column titles* — this becomes the raw material for your mapping in Chapter 8. And identify how you will report on day one.

**4B — The User Target Processing List (the people side).** This sheet is about high-level process mapping: how a user will actually carry out their job in the new system. For each target area or module you record the process and department, write a short note on the user process, describe the **process that needs testing and user-experience (how-to) documenting**, and mark whether it has been documented and checked yet (Yes/Yes, Yes/No, and so on).

The activities here are deliberately simple: create a list of the processes that are needed — and you do not start from a blank page, because you already built a Business Process List back in Step 1; identify the user experience for each of those processes in the new system; and document the processes *with your team*, not in isolation.

This second sheet does quiet but important work. It is, in effect, where your **User Acceptance Testing (UAT) scripts begin**. A documented process — "this is how a sales clerk raises an order in the new system" — becomes a test you can hand to a real user in Chapter 9. The checklist makes the link explicit: the documented processes turn into UAT test scripts used at Step 6.

> **Plain-English box — what is UAT?** **UAT** stands for *User Acceptance Testing*. It simply means letting the actual users — not the technical team — try to do their real jobs with the migrated data, and confirm it works for them. A "UAT script" is just a written set of steps for them to follow, so the test is consistent and nothing important gets skipped. You are writing the first drafts of those scripts now, in Step 4, while the processes are fresh in your mind.

## Key things to get right

Four disciplines turn a target system from an unknown into a documented destination.

**1. Get access to the front-end system.** You need to see what users see — not just what the database holds. A record that looks right in a table can look completely different on the user's screen, where formatting, layout and the field that did not quite map all become visible. Confirm admin and user access early; it tends to take longer than anyone expects.

**2. Test the import templates first, before the data is fully cleaned.** Prove the *pipe* works on a representative sample before you start filling it with months of cleaned data. This is the single fastest way to surface the target's surprises — mandatory fields you had not spotted, validation rules that reject your formats, loading-order dependencies between records.

**3. Document the loading order.** ERP systems especially have dependencies — some records must exist before others can be created (suppliers before supplier products, customers before sales orders, locations before stock). Work the sequence out now, in writing, while you have time. At go-live this becomes the script everyone runs to.

**4. Map every mandatory target field back to a source.** A mandatory field with no source value is a decision the business needs to make — a default, a calculation, or new data to be created — not a problem to be discovered at go-live. The Step 4A Summary Target Sheet captures this directly.

> **Plain-English box — what is a "mandatory field"?** A **mandatory field** is a box the new system *insists* is filled in before it will save a record. If the new system makes "warehouse location" mandatory for every product, then every product without one will be rejected — no matter how clean the rest of its data is. Part of Step 4 is finding every mandatory field in the target so that nothing gets refused at the door later. The same goes for **validation rules** (the system's checks on what counts as acceptable — a date in the right format, a value from an approved list) and **field limits** (how much a field will hold, such as a maximum text length).

## From the Field — Sage 50 to Sage X3

*The following is drawn from a real migration …*

Step 4 is where this project's "same software family, must be simple" assumption finally broke against reality. Sage X3 was a far more sophisticated system than the Sage 50 setup it was replacing, and getting to know it threw up requirements the source had simply never carried:

- **It demanded data Sage 50 never tracked.** There were no warehouse locations recorded in Sage 50, and no Bills of Materials (assembly instructions) at all — yet X3 needed them. Much of the target's required data did not exist anywhere and had to be created from scratch.
- **The front end had a hard display limit.** The X3 interface would only show 1,000 records at a time, so it was better to chunk data up for error-checking rather than trying to load and review everything at once.
- **Loading order mattered.** Records had to go in in a specific sequence, because later imports depended on data from earlier ones — and some fields generated by X3 (such as new supplier IDs) had to be exported *back* into the master set to populate the next load.

A CLASSIC EXAMPLE OF TRACKING BACK!!

I had one advantage worth noting honestly: I had worked with the parent company before and already understood their X3 setup and data structures. That is not luck you can rely on — but it shows the value of the knowledge Step 4 is designed to capture for everyone else.

Two lessons from this step are worth carrying forward into the rest of your migration:

- **Test the import templates first.** I suggest, always tests the import templates first — making sure they actually work with every data set — because early testing is crucial and prevents nasty surprises at go-live.
- **Get access to the front end.** "Get access to the front-end system. You need to see what users see." You cannot document a user process, or judge whether the data will be usable, from the back end alone.

The case study also gives a real, concrete example of why loading order belongs in Step 4 rather than being discovered on migration. The team's loading sequence ran, broadly: suppliers and contacts first, then customers and addresses, then the main product records, then supplier and loan products, then locations, product sites and costing, then the four different types of Bill of Materials, then work centres, then purchase and sales orders, stock receipts and finally financial data. You do not need to copy that order — yours will be different — but you do need to *work yours out in advance*, because the new system will not.

## Your Checklist

These items are taken directly from Step 4 of the Flow7 Data Migration Project Checklist. Tick each one only when it is genuinely done.

**4A — Document all systems that will receive migrated data in a Summary Target Sheet**

- ☐ **4A4** — Verify admin and assigned user access to all systems
- ☐ **4A1** — Check samples in each area of the system(s)
- ☐ **4A2** — Load samples for import testing and complexity
- ☐ **4A3** — Export data from each area for Step 5, with field/column titles

*(The checklist lists access verification first in practice, even though it carries the 4A4 reference — you cannot check anything until you can get in.)*

**4B — Create a User Target Processing List**

- ☐ **4B1** — Create a list of the processes that are needed (use your Business Process List from Step 1C)
- ☐ **4B2** — Identify or map the user experience for those processes in the new system
- ☐ **4B3** — Document the processes into UAT test scripts (these will be used in Step 6)

> ▶ **Worked example — to be added**
>
> *A populated example of a Step 4A Summary Target Sheet — showing one or two target-system areas (likely Products and Customers) with sample data status, import-check results, user-process documentation references and reports — will be added here from a real client engagement.*

## Your Turn

You cannot fill in a whole target assessment from the page — that work happens in the system itself, with access and sample data. But you *can* make the decisions that direct it, and you can flush out the dangerous unknowns now.

**Exercise — 20 minutes, on the page.**

Pick **one** important target area — products, customers, orders, whichever matters most to your business. For that one area, answer:

1. **Can you get in?** Do you (or someone on your team) have working access to the new system for this area — and admin rights where they are needed?
2. **What does it insist on?** Name at least one field this area makes *mandatory* that your old system did not track or did not require. (If you do not know yet, that is your first task.)
3. **Have you tried an import?** Have you loaded even a small sample into this area to see whether it works — and roughly how long it took?
4. **How will a user do their job here?** In one or two plain sentences, describe the single most important thing a user must be able to do in this area after go-live.

If you cannot answer question 2 or 3, you have found exactly the work Step 4 exists to do — and you have found it now, which is the whole point.

**Then take it to the templates.**

The thinking happens on the page; the production work happens in the proper tools. Move your findings into the two Flow7 Step 4 sheets:

- The **Summary Target Sheet (4A)** — for the data side: one row per target area, recording sample data, import checks (with timings), process docs and reporting needs, plus the system's name, version, access and schema at the top.
- The **User Target Processing List (4B)** — for the people side: one row per process, with a note on the user experience and a record of whether it has been documented into a UAT script yet.

When you export data out of each target area for these sheets, **keep the field and column titles** — that export is the raw material you will map against in Chapter 8.

## What you have achieved in this chapter

You know your destination as well as you know your source. You have working access, sample imports that load, a documented loading order, a list of mandatory fields and their validation rules, and the user processes captured in draft UAT scripts. The next chapter brings the two ends together — your master set and your target system — through mapping, cleaning and sample-tested transformations.

## You're Ready to Move On When…

Step 4 is genuinely complete — and you are ready for Chapter 8, The Preparation Work (Mapping) — when **all** of these are true:

- You have **verified access** (admin and user, as needed) to every system that will receive migrated data.
- You have **checked the samples** in each target area and understand its mandatory fields, validation rules and limits.
- You have **run a sample import** into each area, so you know it works and roughly how long it takes — no untested imports are being carried into go-live.
- You have **exported data from each area with its field and column titles**, ready to map in Step 5.
- Your **User Target Processing List** captures the processes that matter (built from your Step 1 Business Process List), with the user experience identified and the key ones documented into draft **UAT scripts** for Step 6.
- You know **how you will report on day one** from the new system.

When those boxes are ticked, you know your destination as well as you know your source. You have one controlled set of data (Chapter 6) and a clear picture of exactly what the new system will accept and how people will use it (this chapter). In the next chapter you bring the two ends together — mapping, cleaning and transforming your master set so it fits the target you have just got to know.
