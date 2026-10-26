**CHAPTER 4**

# Know Your Destination

### *Step 4 of the Flow7 Migration System — Know Your Target System(s)*

**A migration that respects what the target system actually expects — its mandatory fields, its formats, its loading order — imports cleanly first time. That is what this step builds for you.**

## Where You Are in Flow7

{{progress: 4}}

You have one controlled master set. Now you turn round and look the other way: Step 4 is about the system you are moving *into* — what it expects, what it will refuse, and how people will actually work in it once the data lands.

Why not look at the new system first? Because its demo data will work a charm, its workflows and sample documents will look perfect — but it is not *your* data. Understand your own data, processes and terminology first, and you will see the new system far more clearly.

## In this chapter you will…

- Get verified admin and user access to every system that will receive migrated data
- Document the destination, area by area — fields, formats, validation rules, limits
- Run sample imports and measure how long they take
- Export each area with its field titles, ready for mapping in Chapter 5
- Document the user processes that will be tested in Chapter 6

## What you'll need

- Your master data set from Step 3
- Your Business Process List from Step 1 — the starting point for the user-process side
- Working admin and user accounts in the target system

## Why This Matters

Knowing your destination as well as you know your source is what makes the migration import cleanly first time. Every new system has rules the old one never had — fields it insists on, formats it expects, validation it applies, an order things must be loaded in. None of that is a fault; it is simply how the new system works. Discover it now, on purpose, and each rule becomes a documented requirement your mapping in Chapter 5 will satisfy. Discover it during the migration window, and each one becomes an emergency.

There is a second reason, and it is easy to underrate. A migration is not only about data arriving in the right boxes. It is about people being able to do their jobs in the new system the morning after. So Step 4 has two halves: knowing what the system will *accept* (the data side) and knowing how users will *work* in it (the people side). Get both, and your testing in Chapter 6 has something solid to test against.

## What You Are Actually Doing

Step 4 uses two sheets, and they answer two different questions.

**4A — The Summary Target Sheet (the data side).** Your structured record of the destination system. At the top: the system's name, version, how you access it, where its help documentation lives, and a note of its data structure. Then, for each target area — products, customers, orders, finance and so on — you record:

- **Process / department** — which business process this area serves
- **Sample data?** — do you have sample data for this area? (Yes / No / To import)
- **Import check?** — have you tested an import, and how long did it take?
- **User process docs?** — is there documentation for how users work in this area?
- **Reports** — what reporting this area will need on day one

To fill it in, you get proper access, check each area against the real business processes, load sample data to test the import and gauge its complexity, and export each area *with its field and column titles* — that export is the raw material for mapping in Chapter 5.

**4B — The User Target Processing List (the people side).** How users will actually carry out their jobs in the new system. You do not start from a blank page: take your Business Process List from Step 1, and for each process record how it will work in the new system and whether it has been written up as a how-to yet. Do this *with your team*, not on your own.

This second sheet does quiet but important work: it is where your **User Acceptance Testing (UAT) scripts begin**. A documented process — "this is how a sales clerk raises an order in the new system" — becomes a test you can hand to a real user in Chapter 6.

> **Plain English — what is UAT?** *User Acceptance Testing* means letting the actual users — not the technical team — try to do their real jobs with the migrated data, and confirm it works for them. A "UAT script" is simply a written set of steps for them to follow, so the test is consistent and nothing important gets skipped. You are writing the first drafts now, while the processes are fresh in your mind.

## Key things to get right

Four disciplines turn a target system from an unknown into a documented destination.

**1. Get access to the front-end system.** You need to see what users see — not just what the database holds. A record that looks right in a table can look completely different on screen, where formatting, layout and the field that did not quite map all become visible. Confirm admin and user access early; it tends to take longer than anyone expects.

**2. Test the import templates first, before the data is fully cleaned.** Prove the *pipe* works on a representative sample before you fill it with months of cleaned data. It is the fastest way to surface the target's surprises — mandatory fields you had not spotted, validation rules that reject your formats, records that depend on other records.

**3. Work out the loading order.** Systems — ERPs especially — have dependencies: some records must exist before others can be created (suppliers before supplier products, customers before sales orders, locations before stock). Write the sequence down now, while you have time. At go-live it becomes the script everyone works to.

**4. Find a source for every mandatory field.** A mandatory field with no source value is a decision the business needs to make — a default, a calculation, or new data to be created — not a problem to discover at go-live.

> **Plain English — what is a "mandatory field"?** A box the new system *insists* is filled in before it will save a record. If "warehouse location" is mandatory for every product, every product without one will be rejected — however clean the rest of its data. The same goes for **validation rules** (the system's checks on what is acceptable, such as a date format or a value from an approved list) and **field limits** (how much a field will hold, such as a maximum text length).

## From the Field

### *Sage 50 → Sage X3: where "same software family" met reality*

Step 4 is where this project's "same software family, must be simple" assumption finally broke. Sage X3 was a far more sophisticated system than the Sage 50 setup it was replacing, and getting to know it threw up requirements the source had never carried:

- **It demanded data Sage 50 never tracked.** There were no warehouse locations in Sage 50, and no Bills of Materials (assembly instructions) at all — yet X3 needed both. Much of the target's required data did not exist anywhere and had to be created from scratch.
- **The screen had a hard display limit.** X3 would only show 1,000 records at a time, so we split the data into chunks for error-checking rather than loading and reviewing everything at once.
- **Loading order mattered.** Records had to go in a set sequence — suppliers and contacts first, financial data last — because later loads depended on earlier ones. (The full sequence is in Chapter 7.)

> ↩ **Tracking back.** Some fields that X3 created — such as new supplier IDs — had to be exported *back* into the master set before the next load could run. A classic example of tracking back: a Step 4 discovery sent us back to Step 3, then forward again.

I had one advantage worth admitting: I had worked with the parent company before and already understood their X3 setup. You cannot rely on luck like that — which is exactly why Step 4 exists, to capture that knowledge on purpose.

## Your Checklist

The essentials for Step 4. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 4A | Get verified admin and user access to every system that will receive data | ☐ |
| 4A | Check sample data in each area, and note its mandatory fields, validation rules and limits | ☐ |
| 4A | Load samples to test each import, and record how long it takes | ☐ |
| 4A | Export each area with its field and column titles, ready for mapping | ☐ |
| 4B | List the processes the business needs, starting from your Step 1 Business Process List | ☐ |
| 4B | Work out how each process will run in the new system, and draft its UAT test script | ☐ |

> 📋 **Worked example — illustrative scenario**
>
> *The same kitchenware wholesaler from Chapter 1, now looking at its new cloud ERP. Two rows of its Summary Target Sheet after the first week. The business is invented; the kinds of findings are typical.*

| Target area | Process / department | Sample data? | Import check? | User process docs? | Reports needed day one |
|:-|:-|:-|:-|:-|:-|
| Products | Product set-up / Warehouse | Yes — 50 products | Yes — 50 rows in 4 min, **but 12 rejected**: "Bin location" is mandatory and our data has none | No — warehouse to write how-to for receiving stock | Stock on hand by location |
| Customers | Account set-up / Sales | Yes — 100 customers | Yes — 100 rows in 2 min; first and last name are separate fields in the new system | Draft — "raise a quote" written with the sales team | Aged debtors, top 20 customers |

*Two findings in one week: a mandatory field with no source (bin locations — the paper stock notebook from Chapter 1 suddenly matters), and a name field that will need splitting in Step 5. Both are now written down, with a week to spare instead of an hour.*

## Your Turn

You cannot fill in a whole target assessment from the page — that happens in the system itself. But you can flush out the dangerous unknowns now.

### Exercise 4.1 — One Target Area, Four Questions

Pick **one** important target area — products, customers, orders, whichever matters most. For that one area, answer:

1. **Can you get in?** Do you (or someone on your team) have working access — with admin rights where they are needed?
2. **What does it insist on?** Name at least one field this area makes *mandatory* that your old system did not track or did not require. If you do not know yet, that is your first task.
3. **Have you tried an import?** Have you loaded even a small sample, and roughly how long did it take?
4. **How will a user do their job here?** In one or two plain sentences, describe the most important thing a user must be able to do in this area after go-live.

If you cannot answer question 2 or 3, you have found exactly the work Step 4 exists to do — and found it now, which is the whole point.

{{worksheet: 4.1 | One target area, four questions}}

> 📄 **Your template.** Flow7 Step 4 — *Summary Target Sheet* (4A) and *User Target Processing List* (4B), with progress tracked in the *Flow7 Data Migration Project Plan Checklist*. When you export each target area, keep the field and column titles — you will map against them in Chapter 5. Worksheet 4.1 is in the worksheet pack. Download at **stuartparkins.com**.

## What you have achieved in this chapter

You know your destination as well as you know your source. You have working access, sample imports that load, a documented loading order, a list of mandatory fields and their rules, and the key user processes captured in draft UAT scripts.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| You have verified admin and user access to every system that will receive data | ☐ |
| You understand each target area's mandatory fields, validation rules and limits | ☐ |
| You have run a sample import into each area and know roughly how long it takes | ☐ |
| You have exported each area with its field and column titles, ready to map | ☐ |
| Your loading order is written down | ☐ |
| Your key user processes are listed, with draft UAT scripts — and you know how you will report on day one | ☐ |

**If you cannot tick every box, keep getting to know the target before you map.** An untested import carried into go-live is a surprise waiting to happen.

**Next:** Chapter 5 — bring the two ends together: map, clean and transform your master set to fit the target.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: where the way people work today does not fit the way the new system expects them to work. You will pull these notes together in the closing chapter, *Know the Business*.
