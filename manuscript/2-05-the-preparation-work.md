**CHAPTER 5**

# The Preparation Work

### *Step 5 of the Flow7 Data Migration System — Data Mapping and Cleaning*

**"This is my favourite bit: taking messy, scattered data and making it work properly."**

## Where You Are in Flow7

{{progress: 5}}

You have one controlled master set and you know exactly what the target system expects. Step 5 brings the two ends together. If the earlier chapters were about understanding, this one is about **doing**.

## In this chapter you will…

- Map every source field to its target field, area by area
- Write clear cleaning and transformation rules for every mismatch
- Resolve picklist mismatches with the system owner
- Load a cleaned sample to the target and check it with your own eyes
- Define the sample test data set for Chapter 6

## What you'll need

- Your master data set from Step 3 (the source side of the mapping)
- Your target exports, with field and column titles, from Step 4 (the target side)
- A mapping tool — Excel for most teams; Skyvia, Zoho DataPrep or SQL Server for larger jobs
- Real sample data from both source and target — not invented examples

## Why This Matters

A mapping document is the bridge between your master set and your target system: a written, agreed record of where every field goes, what needs to change about it, and what the result should look like.

Most first-attempt imports fail because that bridge does not exist. The data is there; the target is there; what is missing is the rule. A country field holding "GB" will not import into a target that expects "United Kingdom" — and the fix takes ten minutes once you know about it. A discount stored as "10" will land wrongly in a target that stores "0.1". Free text in a product code field stops an import dead. Each is a mismatch; each, once found, becomes a rule a colleague can follow.

Done well, the mapping document is also the most reused document in the whole project: testing uses it in Chapter 6, go-live runs against it in Chapter 7, and anyone auditing the migration later picks it up unchanged.

## What You Are Actually Doing

Step 5 matches the fields in your master set to the fields in your target system, and decides what needs cleaning or transforming so the data will both *fit* and *work* in the new system. It has three parts, done in order:

1. **5A — Set up your mapping.** Choose a tool, bring both field lists together, and make sure every source field has sample data next to it.
2. **5B — Map each field.** Match source fields to target fields, note every mismatch, and write the cleaning or transformation rule for each one.
3. **5C — Test your mapping.** Load cleaned samples into the target, check them with your own eyes, update your rules, and define the test data you will carry into Step 6.

Expect at least one round of revision after the first sample test. That is not a problem; it is the process working.

### Choosing your mapping tool

| Tool | Best for | Skill level |
|:-|:-|:-:|
| **Excel / Google Sheets** | Most small-to-mid migrations; easy to share; already familiar | Beginner |
| **Zoho DataPrep** | Automated cleaning rules; good for Zoho-based migrations | Low–intermediate |
| **Skyvia** | Cloud-to-cloud migrations; built-in mapping screens | Low–intermediate |
| **SQL Server (SSMS)** | Large, complex data sets; precise, repeatable transformations | Technical |

For most non-technical teams, **start in Excel**. It handles a full source-to-target mapping perfectly well. Move up only if the volume or complexity genuinely demands it — let the job, not the anxiety, decide.

### The five-column mapping sheet

The Flow7 Step 5 Simple Mapping Sheet has five columns, and every row fills all five. Use one sheet per area — customers, products, suppliers and so on — and keep them together in one Excel file.

| Source field | Sample (source) | Target field | Sample (target) | Clean and transform notes |
|:-:|:-:|:-:|:-:|:-:|
| The field name in your master set | A real value from your data | The field name in the target system | A real value from the target | What needs to change, and the rule for changing it |

> 🔑 **Key idea — always use real sample data.** Fill the sample columns with actual values from your master set and your Step 4 target export — never invented examples. Real samples show up problems that made-up data hides: a truncated address, an odd character, a number stored as text. If a field has no sample yet, load one before you map it. Mapping on field names alone is guessing.

### What you are looking for

The most common reasons data needs changing:

- **Data type** — text in the source, a number field in the target.
- **Field length** — a 500-character description going into a 100-character field.
- **Format** — "GB" when the target wants "United Kingdom"; "GBP" when it stores the currency code "826".
- **Dates and times** — one of the biggest mismatches of all, so check every date field on its own:
  - *Day or month first?* Is 03/04/2025 the 3rd of April or the 4th of March? UK and US systems disagree, and a wrong guess changes the date silently rather than failing.
  - *Dates stored as text*, or as numbers (Excel keeps dates as serial numbers, so 45,750 can turn up where a date should be).
  - *Two-digit years* — is "25" 2025 or 1925?
  - *Date versus date and time* — a date-only field in the source going into a date-and-time field in the target (or the reverse) can gain a midnight, lose the time, or shift by a day when time zones or British Summer Time are applied.
  - *Placeholder dates* such as 01/01/1900 standing in for "unknown" — decide whether they become blanks.
- **Number and decimal storage** — a discount stored as "10" when the target expects "0.1". Multiplied across a price list, that is a serious problem on day one.
- **Picklists** — the target only accepts values from a fixed list, and your data holds values that are not on it.
- **Free text where a code belongs** — someone used the product code field as a notes column.
- **Missing mandatory values** — the target insists on a value your source simply does not have.
- **Different names for the same thing** — the source says TEL, the target says Phone; or one word, such as "Order", hides two different things. Check each one against the Terminology Translator (Appendix A) and record it on Worksheet A.1.

And one that is consistently overlooked: **documents.** Purchase orders, sales orders, invoices and statements all pull data fields. If a field appears on a printed or emailed document, it is in scope for the mapping.

### Handle picklists first

Picklist mismatches are the most underestimated problem in mapping, and they take the longest to resolve. If your data holds a value that is not on the target's list, the record fails with a hard error. Fixing it is rarely just a rule — you may need to:

- **add new values to the target**, which needs admin access and sometimes the system owner's or implementation partner's approval;
- **decide how old values map to existing ones** — that "Trade" becomes "Trade Customer" is a business decision, not a technical one;
- **apply that decision to every affected record.**

So map your picklist fields early: export the accepted values from the target, compare them with what your data actually holds, and start the conversation about the gaps straight away.

### Write rules someone else can follow

A good cleaning rule is precise enough for a colleague to apply without asking you.

| Vague | Good |
|:-|:-|
| "Fix the country field" | Replace "GB" with "United Kingdom" and "USA" with "United States"; leave other values unchanged; flag anything that is not a known country for manual review. |
| "Sort out the phone numbers" | Remove all spaces; make sure UK mobile numbers start "07"; flag any number with fewer than 10 digits for review before import. |
| "Fix the dates" | Source order dates are text in DD/MM/YYYY; convert to the target's YYYY-MM-DD format. Order time is not held in the source, so set it to 12:00 to stop time-zone shifts moving the date. Treat 01/01/1900 as blank. Flag any day above 12 that would be read as a month for manual review. |

Write the rules into the Clean and Transform Notes column, apply them in your mapping tool, and use the cleaned output for your sample test. Do not skip the test and go straight to a full load.

## Key things to get right

The five rules above, in one place — plus one that comes first of all.

**0. Get the structure right before the fields.** If your source has a single "Contact" record and the target has separate "People" and "Accounts", that difference governs everything else. Agree how the areas line up first; map fields second.

1. **Real sample data, every time** — never map on field names alone.
2. **Picklists first** — they need decisions, not just rules.
3. **Rules precise enough for someone else to follow.**
4. **Check the documents** that print or email your data.
5. **Test on a sample, and look at it on screen** — "imported without error" is a low bar; "looks right on the screen the user actually uses" is the right one.

## From the Field

### *Sage 50 → Sage X3: mapping into a far bigger system*

By Step 5 the scale of the mapping was clear. Sage X3 had a far more complex data structure than the Sage 50 setup the team had used for years. I needed to restructure product information for X3's requirements, create data, fields and categories that had never existed in Sage 50, and turn informal knowledge into proper structured records.

For the mapping itself I used Excel — why not? It was perfect for talking details through with the Sage 50 team, who used it every day anyway. One column held the Sage 50 fields from the master set; another held the X3 target fields. Starting from the implementation partner's import templates gave us a ready-made structure: the target fields were already defined, and the job was connecting the source data to them.

For the transformations I built three layers in SQL: **source views** (the Sage 50 data as it was), **transformation views** (where the cleaning rules ran) and **output views** shaped to match each X3 import template. Skyvia or Zoho DataPrep would have done the same job — and in Excel the logic is identical: source data, cleaned data, data ready to load. The tool changes; the principle does not.

The same team habit from Step 3 showed up again: the rules written for the new data files were not always followed. That is not a failure of the system — it is normal on any project involving people, and it is exactly why 5C exists. The sample test catches what the rules missed, before it reaches the live system.

## Your Checklist

The essentials for Step 5. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 5A | Choose your mapping tool, and list every source and target field by area | ☐ |
| 5A | Make sure every source field has real sample data, and prioritise the mandatory and critical fields | ☐ |
| 5B | Match each source field to its target field and describe any mismatch | ☐ |
| 5B | Write a cleaning or transformation rule for every mismatch — picklists and mandatory fields first | ☐ |
| 5C | Load cleaned samples into the target, check them on screen, and update your rules | ☐ |
| 5C | Define the sample test data set you will use in Step 6 | ☐ |

> 📋 **Worked example — Sage 50 → Sage X3, five mapping rows**
>
> *Drawn from the case study. Five real mismatch types from the Sage 50 → X3 mapping, written as they would appear in the Step 5 Simple Mapping Sheet.*

| Source field | Sample (source) | Target field | Sample (target) | Clean and transform notes |
|:-|:-|:-|:-|:-|
| Country | GB | Country | United Kingdom | **Format / value mismatch.** Replace ISO 2-letter codes with full country names. GB → United Kingdom; US → United States; flag any other value for manual review. |
| DiscountRate | 10 (meaning 10%) | DiscountRate | 0.1 | **Decimal-storage mismatch.** Source stores percentages as whole numbers; target stores decimals. Divide all values by 100 on import. Business rule: no discount above 0.5 (50%) without sign-off. |
| Customer Type | Trade | CustomerCategory | Trade Customer | **Picklist mismatch.** Trade → Trade Customer; Retail → Retail Customer; Wholesale → Trade Customer (Wholesale). Any *new* target value to be confirmed with the system admin before import. |
| WarehouseLocation | *(empty)* | WarehouseLocation | MAIN-A1 | **Mandatory target field with no source value.** The field did not exist in Sage 50 but is mandatory in X3. Default to MAIN-A1 for all stocked products on the initial load; allocate proper locations in the post-go-live stock take. *A recorded business decision, not a cleaning rule.* |
| ProductCode | WIDGET-123 / blue, with extra stop on 12/11 | ProductCode | WIDGET-123 | **Free text in a structured field.** Strip everything after the first space and move the narrative into ProductNotes. Flag any code that does not start with letters followed by "-" for manual review. |

*Five rows, five of the most common mismatch types: format, decimal storage, picklist, missing mandatory data, and free text in a structured field. Real mappings run to dozens or hundreds of rows — the pattern is the same.*

## Your Turn

Two quick exercises before you open your mapping tool. Pick the one area that matters most — for most businesses, customers or products.

### Exercise 5.1 — Your Five Most Problematic Fields

List the five fields in that area where you already suspect trouble, with your best guess at what the problem is. For each one, ask:

- Is it a format, value, type or structural issue?
- Can a simple rule fix it, or does someone need to make a decision first?
- Is the source data actually there — or does it need to be created?
- Does this field appear on any document (invoice, purchase order, statement)?

{{worksheet: 5.1 | Five most problematic fields}}

### Exercise 5.2 — Your Picklist Gaps

Name every field in that area where the target only accepts values from a fixed list. For each one, pull the accepted values from the target, compare them with what your data actually holds, and note the gaps. Each gap is a conversation to start now.

{{worksheet: 5.2 | Picklist gaps}}

> 📄 **Your template.** Flow7 Step 5 — *Simple Mapping Sheet* (one sheet per area, five columns, real samples from both sides), with progress tracked in the *Flow7 Data Migration Project Plan Checklist*. Complete the full mapping for your first area before moving to the next. Worksheets 5.1 and 5.2 are in the worksheet pack. Download at **stuartparkins.com**.

## What you have achieved in this chapter

Every source field has a target. Every mismatch has a written rule. Every picklist is resolved or escalated. A cleaned sample has loaded into the target and passed your eye check, and your Step 6 test data is defined.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Every source field has been mapped to a target — or deliberately excluded | ☐ |
| Every mismatch has a written cleaning or transformation rule | ☐ |
| Every mandatory target field has a source value, or a recorded decision where none exists | ☐ |
| Every picklist mismatch is identified and its resolution agreed | ☐ |
| Fields that appear on documents (invoices, orders, statements) are included | ☐ |
| A cleaned sample has loaded and been checked **on screen**, your rules are updated, and your Step 6 test data is defined | ☐ |

**If you cannot tick every box, do not move on.** Step 6 tests what you have built here — gaps in the mapping become gaps in the testing, and then surprises in production.

**Next:** Chapter 6 — put the whole mapping through structured testing, with a clear pass or fail for every check.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: the words it uses for things, and where they collide with the new system. Add every mismatch to your Terminology Translator. You will pull these notes together in the closing chapter, *Know the Business*.
