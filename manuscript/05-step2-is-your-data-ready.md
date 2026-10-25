**CHAPTER 5**

# Is Your Data Ready?

### *Step 2 of the Flow7 Migration System — Assess Source Data Quality*

*You now know where your data lives (Chapter 4). This chapter is about finding out what condition it is actually in — honestly, and before you move a single record.*

**A proper data quality assessment turns a guess into a measured picture you can plan against — and that measured picture is what makes the next four chapters move forward with confidence.**

## Where You Are in Flow7

You found your data in Chapter 4 — every system, every spreadsheet, every paper record. Step 2 of the Flow7 Migration System is where you take an honest look at the *condition* of that data, before you move any of it.

In the cooking analogy, this is **checking what you are working with** — looking at each ingredient and deciding whether it is still good.

## In this chapter you will…

- Assess each priority source across the seven Flow7 data-quality dimensions
- Record real counts, growth rates, gaps and accuracy figures (not estimates)
- Identify duplicates, blanks and inconsistent formatting that need cleaning
- Decide which source holds the version of the truth where two disagree (this feeds straight into Chapter 6)
- Identify any critical knowledge that lives only in people's heads

## What you'll need from earlier chapters

- Your Step 1 source inventory (every priority source)
- Access to extract or view sample records from each priority source
- Time on the diary for an honest conversation about what the data is really like
- Confirmation of your compliance position before sampling personal data

## Why This Matters

A measured, honest picture of your data is one of the most useful things you can carry into the rest of the migration. With it, every later step works against known quantities: the master set knows what to consolidate, the mapping knows what needs cleaning, the testing knows what to test against, and the go-live counts have something firm to reconcile to. Without it, every later step has to keep stopping to find out what the data is *actually* like — and that is where time and budget disappear.

There is a second, quieter benefit. Most businesses are in better shape than they fear *and* worse shape than they assume. The point of Step 2 is not to pass judgement on the data; it is to replace assumption with measurement. On the case study running through this workbook — Sage 50 to Sage X3 for a manufacturer — the initial assumption was that the data must be fine because the business was doing well. The assessment found more than 7,000 product records needing clean-up, stock that did not match the warehouse, and sales orders containing free text where product codes should have been. None of that was a disaster; all of it was *useful* — because once it was measured, it could be planned for.

This chapter — Step 2 of Flow7 — is the structured way to take that measurement.

## What You Are Actually Doing

Step 2 has a deliberately plain name: **Assess Source Data Quality.** The official Flow7 description sets the goal clearly — you are trying to get *a holistic picture of the "state" of the data and the records as they are now in your source systems, and the user/departmental business processes that interact within those systems.*

Read that twice, because it contains the part people miss. Step 2 is not only about the data. It is about the **data and the processes that create it.** The Flow7 sheet states the principle directly: *"Data quality is inseparable from the business processes that create and maintain that data. Without understanding these processes, you risk migrating data without the context needed to use it effectively."*

So this stage builds directly on Chapter 4. You have your list of sources. Now, for each important one, you assess it across seven dimensions. These are the exact dimensions from the Flow7 Data Quality Assessment sheet:

**1. Process Name.** The business process the data belongs to — described in plain terms. *(For example: Sales Order Creation, Invoice Raising, Raise Customer Ticket.)* You assess data by process, not just by system, because that is how the business actually uses it.

**2. Counts By Type.** How many records of each type exist. *(For example: 4,000 sales orders, 300 accounts, 250 support tickets, 6,000 products.)* This number matters more than people expect — you will use it again at testing and go-live to confirm nothing was lost. NB.This is very likely a moving target requiring recounts at  key stages especially on Go Live. You need to know you have migrated all the data you had set out to move.

**3. Growth By Type.** How fast each record type is growing, over a defined period. *(For example: sales orders 15% per year, accounts 5% per year, support tickets 30% per year.)* A fast-growing dataset changes your timeline and your go live planning.

**4. Completeness versus Gaps.** How complete the data is across the fields that matter. *(For example: emails present in 60% of accounts, postcodes present in 47% of addresses.)* Gaps in key fields are where migrations quietly fail, especially if those gaps drive key processes for the business.E.g you cannot email a document for signature if no email is available. Sounds obvious I know!

**5. Accuracy error %.** How *correct* the data is — which is not the same as whether a field is filled in. A field can be 100% complete and 30% wrong. *(For example: tax codes 20% error, postcodes 10%, sort codes 30%, ISO currency codes 5%.) Many old systems allow free text or never had preselected values so information though filled in may be wrong.*

**6. Consistency.** Whether the same information matches across different systems and records — and, where it does not, which source holds the version you should trust. *(The sheet flags this directly: note which system has the correct data, because this decision feeds straight into Step 3 — defining your master data set.)*

**7. Process Documents.** The names of any process and governance documents that describe how this data is created and maintained. If none exist, that itself is a finding — it usually means the knowledge lives in someone's head, which is a migration risk in its own right.

Alongside these seven, the assessment sheet also captures the **department**, the **owner or expert** for each system or process (their initials), and the **total data size** (TB / GB / MB).

> ▶ **Completeness vs Accuracy — the distinction that saves you**
>
> These two get confused constantly, so fix the difference in your mind now:
>
> - **Completeness** asks: *is the field filled in?*
> - **Accuracy** asks: *is what's in the field correct?*
>
> A customer record can have a phone number in every row (100% complete) where a third of those numbers are wrong or  incomplete, e.g. missing a leading '0' , or (and this annoys me), multiple numbers in a field for one number usually separated with a comma or a note (33% inaccurate). Checking only completeness gives you false confidence. You need both.

## Key things to get right

Four disciplines turn an assessment from "we looked at it" into a useful, measured picture.

**1. Measure completeness and accuracy separately.** A field can be filled in everywhere (100% complete) and still be wrong in a third of cases (33% inaccurate). Checking only completeness gives you false confidence. The Step 2 sheet has both columns for a reason — record both numbers.

**2. Sample randomly, not selectively.** Twenty records from the top of a list are twenty records that someone has curated, or that happen to be the most recent and best-maintained. A random sample tells you the truth about the whole dataset. If you cannot pull a truly random sample, take small samples from different points in the data.

**3. Get the record counts now.** Counts taken at this point — customers, products, orders, suppliers, transactions — become your reference figure for testing in Chapter 9 and for go-live reconciliation in Chapter 10. Capture them now, even if some of the data will be cleaned or excluded later. You will use these numbers again and update them in live systems.

**4. Document what lives in people's heads.** If a process only works because one or two long-serving staff know how it works, that is a finding worth recording — not because it is a problem, but because it is data that will need to be turned into structured records before migration. The Step 2 Process Documents column captures this directly.

> ⚠️ **A note before you assess personal data**
>
> If the data you are about to examine includes personal data (customer details, employee records, contact information), confirm your UK GDPR position before you start digging through records and pulling samples. You should already have addressed this in your project plan (see *Before You Start*). If you have not, do so now — assessing data quality means looking at real records, and that is processing.

## From the Field

### The Sage 50 to Sage X3 Migration: The Reality Check

When I was brought in as the ETL consultant on the Sage 50 → Sage X3 migration, the client's expectation was straightforward: same software family, successful business, two to three months. I knew from experience not to take that at face value, and applied the Flow7 method — starting, as always, with assessment.

Here is what the assessment surfaced once I had extracted the initial data and the real picture emerged:

**Product data problems:**

- More than 7,000 product records that needed serious clean-up
- No product assembly instructions required for a large percentageof the 7000 (Bills of Materials — the structured component lists needed to make a product) recorded anywhere
- Different product types each missing crucial data
- Critical knowledge trapped in the heads of a few long-serving employees

**Missing and unreliable information:**

- Sage X3 required large amounts of data that Sage 50 simply never tracked
- No recorded warehouse locations in Sage 50
- Stock levels in Sage 50 that did not match what was physically in the warehouse
- Sales and purchase orders containing random free text instead of proper product codes

**Process problems:**

- Processes that had grown organically over years, with zero documentation
- New products added daily with only the bare minimum of information and not linked to any Boms.

In short: not exactly migration-ready.

The most striking finding was this: most of the work was not data cleaning. It needed people to create entirely new information from scratch. More than 1,500 assembly instructions had to be created where none had existed before, and these in turn needed new products defined for the new system to work.

**The detail worth copying:** the management team was — understandably — sceptical about both the timeline and the claimed state of the data. Rather than argue, I ran tests to show exactly how long the cleaning actually took, by the staff doing it, with each completed product (SKU) flagged as it was finished. That gave everyone an easy progress number to track, and it helped the staff too, who were fitting the clean-up around their day jobs.

That is Step 2 working as intended: not a one-off audit, but evidence that turns "the data's probably fine" into a measured, agreed picture everyone can plan around.

## Your Checklist

The items below are the **Data Quality Assessment** tasks, taken directly from the *Flow7 Data Migration Project Plan Checklist* (SP Data Consultancy Ltd, V1.0) and the *7 Steps for Any Data Project* framework checklist. They map exactly to the columns on the Step 2 Data Quality Assessment sheet.

Work through each item **for every priority source** you identified in Chapter 4 — not just one. Mark an item complete only when it is genuinely done, with a number or a note recorded against it, not when you intend to do it.

The three columns on the right match the format of the downloadable Flow7 project checklist: **Status**, **Due/Done date**, and **Owner**.

### 2A — Perform and Record the Data Quality Assessment (By Process & Source)

| Ref | Task | Status | Due/Done | Owner |
|:-:|:-|:-:|:-:|:-:|
| 2A1 | Record the **Process Name** — a descriptive name for the business process the data belongs to |   |   |   |
| 2A2 | Record **Counts By Type** — the record count for each specific type within the process |   |   |   |
| 2A3 | Record **Growth By Type** — the percentage growth of each type over a defined period |   |   |   |
| 2A4 | Record **Completeness versus Gaps** — how complete the data is across key fields |   |   |   |
| 2A5 | Record **Accuracy error %** — how accurate the data is across key fields |   |   |   |
| 2A6 | Record **Consistency** — is the same information consistent across systems and records, and which source is correct? |   |   |   |
| 2A7 | Record **Process Documents** — the names of any process and governance documents |   |   |   |

### 2A (supporting captures from the assessment sheet)

| Ref | Task | Status | Due/Done | Owner |
|:-:|:-|:-:|:-:|:-:|
| 2A-i | Record the **Department** for each process assessed |   |   |   |
| 2A-ii | Record the **Owner / Expert** of each system or process (their initials) |   |   |   |
| 2A-iii | Record the **Total Data Size** across sources (TB / GB / MB) |   |   |   |

### From the framework checklist — the questions Step 2 must answer

| Ref | Question to satisfy | Status | Due/Done | Owner |
|:-:|:-|:-:|:-:|:-:|
| Q1 | Have you checked for **duplicates, blanks and inconsistent formatting** in key fields? |   |   |   |
| Q2 | Do you know **which records are current** and which are out of date or redundant? |   |   |   |
| Q3 | Is the data **consistent across sources** — or does the same information appear differently in different places? |   |   |   |
| Q4 | Have you **documented what needs cleaning** before the project proceeds? |   |   |   |

> ▶ **Worked example — Sage 50 → Sage X3, Product Master assessment**
>
> *Drawn from the case study. One row of the Step 2 Data Quality Assessment sheet, showing how the seven dimensions look once measured against real data.*

| Dimension | What we measured |
|:-|:-|
| **Process Name** | Product Master maintenance |
| **Department** | Operations / Warehouse |
| **Counts by Type** | 7,000+ active product records; ~1,500 assembly instructions *required* (none yet existed); 4 types of Bill of Materials needed |
| **Growth by Type** | ~5% net annual growth in active product count |
| **Completeness vs Gaps** | Product code: 100% complete. Description: 100% complete. **Warehouse location: 100% gap** (field did not exist in Sage 50). **Bills of Materials: 100% gap** (knowledge held by long-serving staff, not in any system). |
| **Accuracy %** | Stock-on-hand vs physical warehouse: ~20% discrepancy. Product codes used on sales/purchase orders: significant free-text contamination (no clean count, several percent). |
| **Consistency** | Sage 50 was the only digital source — but where Sage 50 disagreed with the physical warehouse for stock-on-hand, the warehouse was the authoritative source for the master. |
| **Process Documents** | None held centrally. Product setup, BOM logic and recipe knowledge held informally by two long-serving employees. |
| **Total Data Size** | ~330MB across the relevant Sage 50 tables (well within Excel-handleable range for sample analysis). |
| **Owner / Expert** | Operations Manager (initials redacted) for product setup; Production Supervisor for BOMs and assembly knowledge. |

*This single row drove the realistic timeline for the whole project: assessment turned an assumed three-month migration into a planned five-month migration, with the extra two months budgeted for new data creation rather than data cleaning. The figures themselves are not the lesson; the lesson is that having the figures changed every decision that followed.*

## Your Turn

You do not assess every record by hand — nobody does, and you do not need to. The practical technique is **sampling**: pull a small set of records, check them carefully, and use what you find as an indicator of the whole.

### Exercise 5.1 — The 20-Record Spot-Check

Pick **one** important data source from your Chapter 4 inventory (start with your highest-priority one). Pull a sample of **10 to 20 records** from it — ideally a *random* spread, not the first twenty and not your best customers. Then complete the table below.

**Why random matters:** if you check only the records you know well, you will check the ones most likely to be clean. A random sample tells you the truth about the whole dataset.

**Source being assessed:** {{write-in}}

**Number of records sampled:** {{write-in-short}}

| Check | What you found | Rough % |
|:-|:-:|:-:|
| **Blanks** — key fields left empty |   |   |
| **Duplicates** — the same record appearing more than once |   |   |
| **Formatting** — same data written different ways (e.g. "St." vs "Street", dates as DD/MM vs MM/DD) |   |   |
| **Accuracy** — values that are filled in but wrong, outdated, or implausible |   |   |
| **Stale records** — entries clearly no longer current |   |   |

### Exercise 5.2 — The "Whose Head Is It In?" Test

For your priority source, answer these two questions honestly:

**1. If the one person who understands this data best left tomorrow, what knowledge would walk out of the door with them?**

{{write-in}}

**2. Is there a written process document for how this data is created and maintained? (Y / N)**

{{write-in}}

If the answer to question 2 is "No," and question 1 produced a long list, you have found one of the most common — and most dangerous — findings in any migration: **critical knowledge that exists only in people's heads.** Flag it now. In the case study, exactly this gap is what turned a three-month estimate into a five-month project.

### Now Go to the Full Template

The exercises above are a starting sample to build your instincts. The real assessment — every priority process, every count, every gap and accuracy figure — belongs in the proper tool: the **Flow7 Step 2 Data Quality Assessment sheet**, with the supporting rows (2A1–2A7) tracked in the **Flow7 Data Migration Project Plan Checklist** Excel workbook.

Record a real number or note against every dimension, for every source that matters. The blank assessment grid is built exactly for this — one row per process, the seven dimensions across the columns, plus department, owner and total data size.

Download the templates at: **stuartparkins.com**

## What you have achieved in this chapter

You have a measured, honest picture of your data — process by process, source by source. Duplicates, gaps, accuracy issues and inconsistencies between sources are named and quantified. Where two sources disagree, you know which one holds the truth. Critical knowledge that lives only in people's heads is identified and flagged. The work you did here drives the next step directly: defining the single master data set everything will be migrated from.

## You're Ready to Move On When…

You are ready to move from assessing your data to Chapter 6 — defining your single version of the truth — when all of the following are true. Do not proceed until every item can be ticked honestly.

| Gate | ✓ |
|:-|:-:|
| Every priority data source has been assessed across the seven Step 2 dimensions, with real numbers or notes recorded — not estimates from memory | ☐ |
| You have an accurate **record count** for each key data type (you will need these again at testing and go-live) | ☐ |
| Completeness and accuracy have been measured **separately** for your key fields | ☐ |
| Duplicates, blanks and inconsistent formatting have been checked and quantified | ☐ |
| You know which records are current and which are stale or redundant | ☐ |
| Where the same data exists in more than one source, you have noted **which source is correct** (this feeds directly into Step 3) | ☐ |
| Any critical knowledge that lives only in people's heads has been identified and flagged | ☐ |
| A documented list of **what needs cleaning** exists before any further work begins | ☐ |
| The total data size and the owner/expert for each source have been recorded | ☐ |

**If you cannot tick all of these, go back and finish your assessment before moving on.**

Remember the central lesson of this step: a migration does not improve data, it relocates it. The work you do here — the honest, sometimes uncomfortable look at what you actually have — is what stops you paying to install your old problems in an expensive new system.

As the case study proves, the businesses that succeed are the ones that invest the time upfront to understand the true data picture, *before* committing to timelines and budgets.
