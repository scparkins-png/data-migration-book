**CHAPTER 2**

# Is Your Data Ready?

### *Step 2 of the Flow7 Migration System — Assess Source Data Quality*

**"A migration does not improve your data. It relocates it."**

## Where You Are in Flow7

{{progress: 2}}

You know where your data lives. Step 2 is where you take an honest look at the *condition* of that data — before you move any of it.

## In this chapter you will…

- Assess each priority source across the seven Flow7 data-quality dimensions
- Record real counts, growth rates, gaps and accuracy figures (not estimates)
- Identify duplicates, blanks and inconsistent formatting that need cleaning
- Decide which source holds the truth where two disagree
- Identify any critical knowledge that lives only in people's heads

## What you'll need

- Your Step 1 source inventory (every priority source)
- Access to extract or view sample records from each priority source
- Time in the diary for an honest conversation about what the data is really like
- Confirmation of your compliance position before sampling personal data

## Why This Matters

A measured, honest picture of your data is one of the most useful things you can carry into the rest of the migration. With it, every later step works against known quantities: the master set knows what to consolidate, the mapping knows what needs cleaning, the testing knows what to test against, and the go-live counts have something firm to reconcile to. Without it, every later step has to keep stopping to find out what the data is *actually* like — and that is where time and budget disappear.

There is a second, quieter benefit. Most businesses are in better shape than they fear *and* worse shape than they assume. The point of Step 2 is not to pass judgement on the data; it is to replace assumption with measurement. Once a problem is measured, it can be planned for.

## What You Are Actually Doing

Step 2 is about getting a true picture of the data **and the processes that create it**. The Flow7 sheet puts the principle directly: *"Data quality is inseparable from the business processes that create and maintain that data. Without understanding these processes, you risk migrating data without the context needed to use it effectively."*

So for each important source from your Step 1 inventory, you assess it across seven dimensions — the same seven columns as the Flow7 Data Quality Assessment sheet:

| Dimension | What it asks | Example |
|:-|:-|:-|
| **1. Process name** | Which business process does this data belong to? | Sales Order Creation, Invoice Raising, Raise Customer Ticket |
| **2. Counts by type** | How many records of each type are there? | 4,000 sales orders, 300 accounts, 6,000 products |
| **3. Growth by type** | How fast is each type growing? | Sales orders up 15% a year, support tickets up 30% |
| **4. Completeness** | Are the key fields filled in? | Emails in 60% of accounts; postcodes in 47% of addresses |
| **5. Accuracy** | Is what is in the field correct? | Tax codes 20% wrong; sort codes 30% wrong |
| **6. Consistency** | Does the same information match across systems — and which one is right? | A customer's address differs between the CRM and the accounts system |
| **7. Process documents** | Is there anything written down about how this data is created and kept? | "None" is a finding in itself |

A few notes on using them:

- **Assess by process, not just by system.** That is how the business actually uses the data.
- **Counts are a moving target.** You will use them again at testing and go-live to prove nothing was lost, so expect to recount at key stages — especially on go-live day.
- **Gaps bite hardest when they drive a process.** You cannot email a document for signature if there is no email address. Obvious, I know — and still missed.
- **A full field can still be wrong.** Many older systems allowed free text where a fixed list belonged.
- **Consistency feeds straight into Step 3.** Where two sources disagree, note which one is correct; that decision becomes part of your master set.

The sheet also records the **department**, the **owner or expert** (their initials) and the **total data size** (TB / GB / MB) for each process.

> ▶ **Completeness vs accuracy — the distinction that saves you**
>
> These two get confused constantly, so fix the difference in your mind now:
>
> - **Completeness** asks: *is the field filled in?*
> - **Accuracy** asks: *is what's in the field correct?*
>
> A customer record can have a phone number in every row (100% complete) where a third of those numbers are wrong or incomplete — a missing leading "0", or (and this annoys me) several numbers crammed into one field, separated by a comma or a note (33% inaccurate). Checking only completeness gives you false confidence. The Step 2 sheet has a column for each: record both numbers.

## Key things to get right

Three disciplines turn an assessment from "we looked at it" into a useful, measured picture.

**1. Sample randomly, not selectively.** Twenty records from the top of a list are twenty records that someone has curated, or that happen to be the most recent and best-maintained. A random sample tells you the truth about the whole dataset. If you cannot pull a truly random sample, take small samples from different points in the data.

**2. Get the record counts now.** Counts taken at this point — customers, products, orders, suppliers, transactions — become your reference figure for testing in Chapter 6 and for go-live reconciliation in Chapter 7. Capture them now, even if some of the data will be cleaned or excluded later.

**3. Document what lives in people's heads.** If a process only works because one or two long-serving staff know how it works, that is a finding worth recording — not because it is a problem, but because it is data that will need to be turned into structured records before migration. The Process Documents column captures this directly.

> ⚠️ **Before you assess personal data**
>
> If the data you are about to examine includes personal data (customer details, employee records, contact information), confirm your UK GDPR position before you start pulling samples. You should already have flagged this in *Create Your Plan*. If you have not, do so now — assessing data quality means looking at real records, and that is processing.

## From the Field

### *Sage 50 → Sage X3: the reality check*

The client expected two to three months. I applied the Flow7 method anyway, starting with assessment — and once I had extracted the initial data, the real picture emerged. More than 7,500 product records needed serious clean-up. Stock in Sage 50 did not match what was physically in the warehouse. Sales and purchase orders held random free text where product codes should have been. The worked example below shows one of those assessments in full.

The most striking finding was this: most of the work was not data cleaning at all. It needed people to create entirely new information from scratch. More than 1,500 assembly instructions had to be created where none had existed before, and these in turn needed new products defined for the new system to work.

**The detail worth copying:** the management team was — understandably — sceptical about both the timeline and the claimed state of the data. Rather than argue, I ran tests to show exactly how long the cleaning actually took, by the staff doing it, with each completed product (SKU) flagged as it was finished. That gave everyone an easy progress number to track, and it helped the staff too, who were fitting the clean-up around their day jobs.

That is Step 2 working as intended: not a one-off audit, but evidence that turns "the data's probably fine" into a measured, agreed picture everyone can plan around.

## Your Checklist

The essentials for Step 2, for **every** priority source — not just one. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 2A | Name the business process each source serves, with its department and owner or expert | ☐ |
| 2A | Count the records of each type, note how fast each is growing, and record the total data size | ☐ |
| 2A | Measure completeness and accuracy separately for the key fields | ☐ |
| 2A | Check for duplicates, blanks, inconsistent formatting and out-of-date records | ☐ |
| 2A | Where sources disagree, note which one is correct | ☐ |
| 2A | List what needs cleaning — and any process knowledge that lives only in people's heads | ☐ |

> ▶ **Worked example — Sage 50 → Sage X3, Product Master assessment**
>
> *Drawn from the case study. One row of the Step 2 Data Quality Assessment sheet, showing how the seven dimensions look once measured against real data.*

| Dimension | What we measured |
|:-|:-|
| **Process name** | Product Master maintenance |
| **Department** | Operations / Warehouse |
| **Counts by type** | 7,500+ active product records; about 1,500 assembly instructions *required* (none yet existed); 4 types of Bill of Materials needed |
| **Growth by type** | About 5% net annual growth in active product count |
| **Completeness** | Product code: 100% complete. Description: 100% complete. **Warehouse location: 100% gap** (field did not exist in Sage 50). **Bills of Materials: 100% gap** (knowledge held by long-serving staff, not in any system). |
| **Accuracy** | Stock on hand vs physical warehouse: about 20% discrepancy. Product codes used on sales and purchase orders: significant free-text contamination (no clean count, several percent). |
| **Consistency** | Sage 50 was the only digital source — but where Sage 50 disagreed with the physical warehouse for stock on hand, the warehouse was the authoritative source for the master. |
| **Process documents** | None held centrally. Product setup, BOM logic and recipe knowledge held informally by two long-serving employees. |
| **Total data size** | About 330 MB across the relevant Sage 50 tables (well within what Excel can handle for sample analysis). |
| **Owner / expert** | Operations Manager (initials redacted) for product setup; Production Supervisor for BOMs and assembly knowledge. |

*This single row drove the realistic timeline for the whole project: assessment turned an assumed three-month migration into a planned five-month migration, with the extra two months budgeted for new data creation rather than data cleaning. The figures themselves are not the lesson; the lesson is that having the figures changed every decision that followed.*

## Your Turn

You do not assess every record by hand — nobody does. The practical technique is **sampling**: pull a small set of records, check them carefully, and use what you find as an indicator of the whole. Record your findings on Worksheets 2.1 and 2.2 in your worksheet pack.

### Exercise 2.1 — The 20-Record Spot-Check

Pick **one** important source from your Step 1 inventory — start with your highest priority. Pull a sample of **10 to 20 records**: a *random* spread, not the first twenty and not your best customers. For that sample, count and note:

- **Blanks** — key fields left empty
- **Duplicates** — the same record appearing more than once
- **Formatting** — the same data written different ways ("St." vs "Street", dates as DD/MM vs MM/DD)
- **Accuracy** — values that are filled in but wrong, out of date, or implausible
- **Stale records** — entries clearly no longer current

A rough percentage for each is enough at this stage.

{{worksheet: 2.1 | 20-record spot-check}}

### Exercise 2.2 — The "Whose Head Is It In?" Test

For your priority source, answer two questions honestly:

1. If the one person who understands this data best left tomorrow, what knowledge would walk out of the door with them?
2. Is there a written process document for how this data is created and maintained?

If the answer to the second is "no" and the first produced a long list, you have found one of the most common — and most dangerous — findings in any migration: **critical knowledge that exists only in people's heads.** Flag it now. In the case study, exactly this gap is what turned a three-month estimate into a five-month project.

{{worksheet: 2.2 | Whose head is it in?}}

> 📄 **Your template.** Flow7 Step 2 — *Data Quality Assessment* sheet (one row per process, the seven dimensions across the columns), with progress tracked in the *Flow7 Data Migration Project Plan Checklist*. Worksheets 2.1 and 2.2 are in the worksheet pack. Download at **stuartparkins.com**.

## What you have achieved in this chapter

You have a measured, honest picture of your data — process by process, source by source. Duplicates, gaps, accuracy issues and inconsistencies between sources are named and quantified. Where two sources disagree, you know which one holds the truth. Critical knowledge that lives only in people's heads is identified and flagged.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Every priority source has been assessed on all seven dimensions, with real numbers — not estimates from memory | ☐ |
| You have a record count for each key data type (you will need it again at testing and go-live) | ☐ |
| Completeness and accuracy have been measured **separately** for the key fields | ☐ |
| Duplicates, blanks, formatting problems and stale records have been checked and counted | ☐ |
| Where sources disagree, you know which one is correct | ☐ |
| What needs cleaning — and any knowledge held only in people's heads — is written down | ☐ |

**If you cannot tick every box, finish your assessment before moving on.** Skipping it is how businesses pay to install their old problems in an expensive new system.

**Next:** Chapter 3 — out of everything you have found, which version is the truth?

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: what it has quietly tolerated — the records the team already distrusts, and why. You will pull these notes together in the closing chapter, *Know the Business*.
