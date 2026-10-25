**CHAPTER 8**

# The Preparation Work

## Step 5 — Data Mapping & Cleaning

**"This is my favourite bit. Taking messy, scattered data and making it work properly."** *— Stuart Parkins, Sage 50 to Sage X3 migration*

## Where You Are in Flow7

You have found your data (Chapter 4), assessed its quality honestly (Chapter 5), consolidated it into one authoritative master set (Chapter 6), and learned exactly what your target system expects (Chapter 7).

Now you connect those two ends of the journey together.

Step 5 is where you work through every source field and ask: where does this go in the new system — and what, if anything, needs to change about it before it gets there? The answers become a mapping document: a written set of instructions that tells everyone involved exactly what moves where and how. Without it, every import attempt is guesswork. With it, Step 6 testing has something solid to test against.

If the earlier chapters were all about understanding, this one is about **doing**.

## In this chapter you will…

- Map every source field to its target field, area by area
- Write clear cleaning and transformation rules for every mismatch
- Resolve picklist mismatches with the system owner
- Load a cleaned sample to the target and check it visually
- Define the sample test data set for Chapter 9 testing

## What you'll need from earlier chapters

- Your Master Data Set from Chapter 6 (the source side of the mapping)
- Your target export with field and column titles from Chapter 7 (the target side)
- A mapping tool — Excel for most teams; Skyvia, Zoho DataPrep or SSMS for larger jobs
- Real sample data from both source and target (not invented examples)

## Why This Matters

A clean mapping document is what turns a Master Data Set and a target system into a migration. It is the bridge between the two — a written, agreed record of every field that needs to change, exactly how it changes, and what the result should look like.

Most first-attempt imports fail because that bridge does not exist. The data is there; the target is there; what is missing is the rule. A "Country" field holding the value GB will not import into a target that expects United Kingdom — and the fix takes ten minutes once you know about it. Pricing stored as 10 for ten per cent will land wrongly in a target that stores 0.1. Free text sitting in a product code field stops imports entirely. Each of these is a mismatch — and each one, once identified, becomes a transformation rule a colleague can follow.

Step 5 is how you find them all, write the fix, and confirm the fix works on real sample data before any live record is touched. Done well, the mapping document is also the most reused artefact in the whole project: Chapter 9 testing references it, Chapter 10 go-live runs against it, and post-migration audit work picks it up unchanged.

## What You Are Actually Doing

Step 5 of the Flow7 Migration System is defined as matching specific fields or elements from the old or source system(s) to the new target system(s), and determining what data needs cleaning or transforming so it will both fit and work in the new system.

For data mapping you compare, match, and connect your Source Master Data Set from Step 3 to the target system's data and process areas from Step 4.

The step has three parts, run in order.

**5A — Set up your mapping.** Choose a tool, bring both field lists together, and ensure every source field has sample data next to it.

**5B — Map each field.** Match source fields to target fields, note every mismatch, and write the cleaning or transformation rule for each one.

**5C — Test your mapping.** Load cleaned samples to the target system, check them with your own eyes, update your rules based on what you find, and define the test data set you will carry into Step 6.

The process is **iterative** — expect at least one round of revision after the first sample test. That is not a problem; it is the process working as intended.

### Choosing Your Mapping Tool

Data mapping can get very involved, so choosing the right tool before you start saves you from rebuilding in the middle of the work. The choice depends on how technically comfortable you are and how large and complex your data is.

| Tool | Best for | Skill level |
|:-|:-|:-:|
| **Excel / Google Sheets** | Most small-to-mid migrations; easy to share with the team; already familiar | Beginner |
| **Zoho DataPrep** | Automated cleaning rules; good for Zoho-based migrations | Low–intermediate |
| **Skyvia** | Cloud-to-cloud migrations; built-in mapping interface | Low–intermediate |
| **SQL Server (SSMS)** | Large, complex data sets; precise transformations; repeatable ETL | Technical |

For most non-technical teams doing their own migration, **start in Excel**. It is the tool you know. It handles a full source-to-target mapping perfectly well. If the volume or complexity genuinely demands something more powerful, move up — but let the job, not the anxiety, drive that decision.

### The Five-Column Mapping Sheet

The Flow7 Step 5 Simple Mapping Sheet has five columns. Every field mapping row fills all five.

| Source Field / Name | Sample Data (Source) | Target Field Name | Sample Data (Target) | Clean & Transform Notes |
|:-:|:-:|:-:|:-:|:-:|
| The field name as it appears in your master set | A real sample value from your data | The field name in the target system | A real sample value from the target | What needs to change, and the rule for changing it |

You use **one sheet per module or area** — customers, products, suppliers, and so on. At the top of each sheet you record which area it covers. Keep all sheets in one workbook so the mapping stays together.

### ▶ Always Use Real Sample Data

Do not fill the Sample Data columns with invented examples or column descriptions. Use actual values taken from your master set and from the target system export you produced in Step 4. Real samples immediately show up problems that invented data hides — a truncated address, an unexpected character, a number formatted as text. You will not see those in a made-up example.

If a source field has no sample data yet, load some before you proceed. Mapping decisions made on field names alone are guesses.

### What You Are Looking For — Types of Mismatch

Data may need changing for many reasons. The Flow7 Step 5 guidance lists the most common.

**Field data type** — a text field in the source, a number field in the target; the target will reject a text value in a numeric column.

**Field length** — the target has a character limit the source routinely exceeds. Your 500-character product description gets truncated to 100 characters on import.

**Format differences** — dates as DD/MM/YYYY in your source, YYYY-MM-DD required by the target. Country values as "GB" when the target needs "United Kingdom". Currency codes as "GBP" when the target stores the numeric code "826".

**Number and decimal storage** — a discount percentage stored as "10" in the source, when the target expects "0.1". A pricing error like this multiplied across a product catalogue is a serious problem on day one.

**Picklist mismatches** — the target field only accepts values from a fixed list. Your source data has values that are not on that list. The records will fail to import.

**Free text where a code is needed** — someone used a product code field as an extra notes column. The target expects a structured code; it gets narrative text.

**Missing mandatory fields** — the target will not accept a record without a value in a required field. Your source has nothing to put there.

### Do Not Forget Documents

The Flow7 guidance makes this point explicitly, because it is consistently overlooked: check the documents that pull data fields — purchase orders, sales orders, invoices, statements. If a field appears in a printed or emailed document, it is in scope for the mapping. It is easy to notice that an address field needs cleaning; it is less obvious that the field is also displayed on every invoice your customers receive.

### Picklist Mismatches — Handle These First

Picklist mismatches deserve their own warning because they are the most consistently underestimated problem in data mapping, and they take longer to resolve than any other type.

A picklist field only accepts values from a list configured in the target system. If your source data holds a value that is not on that list, the record will fail — not silently and in a way you can fix later, but with a hard error on import.

Resolving a picklist mismatch is not just a matter of writing a transformation rule. You may need to:

- **Add new values to the target system** — which requires admin access and, in some cases, approval from the system owner or implementation partner.
- **Map old values to existing target values** — deciding, for example, that "Trade" in the source becomes "Trade Customer" in the target. That is a business decision, not a technical one.
- **Remap every affected record** — once the rule is agreed, it has to be applied to the data.

All of that takes time. Map your picklist fields early. Export the accepted values from your target system and compare them directly to the actual values in your source data. Note every gap and start the resolution conversation immediately.

### Writing Cleaning Rules

Once you have documented each mismatch, you turn those notes into cleaning rules — specific, written instructions for how a field should be changed.

A good rule is precise enough for someone else to follow.

**Vague:** "Fix the country field"

**Good:** Country field — replace all instances of "GB" with "United Kingdom"; replace "USA" with "United States"; leave all other values unchanged. Any value not matching a known country name to be flagged for manual review.

**Vague:** "Sort out the phone numbers"

**Good:** Phone field — remove all spaces; ensure all UK mobile numbers begin with "07"; flag any number with fewer than 10 digits for manual review before import.

Once rules are written, apply them to your data in the mapping tool, then use the cleaned output for the sample test in Step 5C. Do not skip the test and move straight to the full load.

## Key things to get right

Five disciplines turn the mapping work from a mechanical exercise into a reliable bridge between source and target.

**1. Always use real sample data, not invented examples.** Real samples surface the problems that invented data hides — truncated values, unexpected characters, format quirks, the rogue free-text entry someone made three years ago. Load samples from both sides before you start; mapping decisions made on field names alone are guesses.

**2. Handle picklists first.** Picklist mismatches take longer to resolve than any other type of mismatch because they often involve a business decision *and* a system change, not just a transformation rule. Map your picklist fields early, export the accepted target values, compare them to your source data, and start the resolution conversation with the system owner immediately.

**3. Write rules precisely enough for someone else to follow.** "Fix the country field" is a wish; "replace GB with United Kingdom, US with United States, leave all other values unchanged, flag anything unrecognised for manual review" is a rule. Cleaning rules belong in the Clean & Transform Notes column of the mapping sheet, written precisely the first time.

**4. Check documents that pull data fields.** Invoices, purchase orders, statements, customer-facing emails — fields that appear in a printed or emailed document are in scope for the mapping. Step 5 guidance flags this directly because it is consistently overlooked.

**5. Test on a sample before the full load.** Load cleaned sample data into the target system and *look at it* — in the user interface, not just in the import log. "Imported without error" is a low bar; "looks right on the screen the user actually uses" is the right bar.

There is a final, structural discipline worth naming: confirm how the modules align before you map any fields. If your source has a single "Contact" module and your target has separate "People" and "Accounts" modules, that structural difference governs everything that follows. Get the structure right first; map the fields second.

## From the Field — Sage 50 to Sage X3

*The following is drawn from a real migration documented by Stuart Parkins: a successful manufacturer, recently bought out, moving from Sage 50 to Sage X3.*

By the time this project reached Step 5, the scale of the mapping challenge was understood. Sage X3 had a significantly more complex data structure than the Sage 50 setup the team had relied on for years. The work was, in my own words at the time:

*Sage X3 was completely different from the simple Sage 50 setup. I needed to restructure product information for X3's complex requirements, create data, fields and categories that did not exist in Sage 50, and convert informal knowledge into proper structured records.*

For the high-level mapping work the tool of choice was straightforward. I used Excel — why not? It was perfect for discussing details with the Sage 50 team, and they were using it daily anyway. Column B held the Sage 50 tables (the master data set) and Column K held the X3 target fields.

Starting from the import templates the implementation partner provided gave us a ready-made structure: the target fields were already defined, and the mapping work was connecting the source data to them.

For the transformation work I built an ETL structure using SQL — source views (data from the Sage 50 tables), transformation views (where the cleaning rules ran), and output views shaped to match the Sage X3 import template requirements. Low-cost tools such as Skyvia or Zoho DataPrep would have done the same job. For non-technical teams using Excel, the three-stage logic is identical — source data, transformed/cleaned data, output ready to load. The tool is different; the principle is the same.

One practical lesson from this project: the team did not always follow the rules written for the new data collection files. That is people for you — and it is not a failure of the system. It is a normal feature of any project involving multiple people, and it is precisely why Step 5C exists. The sample test catches what the rules missed before it reaches the live system.

## Your Checklist

These items are taken directly from Step 5 of the Flow7 Data Migration Project Plan Checklist (SP Data Consultancy Ltd, V1.0). Tick each one only when it is genuinely done.

**5A — Set up your mapping**

- ☐ **5A** — Choose your data mapping tool (Excel, Google Sheets, Zoho DataPrep, Skyvia, or similar)
- ☐ **5A1** — Connect to or list all fields from your Master Set (Step 3) by area, module, department, or process
- ☐ **5A2** — Ensure every source field has sample data — load samples if any are missing
- ☐ **5A3** — Create an initial source priority for the fields to be mapped — start with mandatory and critical fields
- ☐ **5A4** — Connect to or list all target system fields (Step 4) by area, module, department, or process

**5B — Map each field**

- ☐ **5B1** — Match each master set (source) field to its corresponding target field
- ☐ **5B2** — Write a brief description of any data mismatch for each field pair
- ☐ **5B3** — Create cleaning and transformation rules in your mapping tool for each mismatch
- ☐ **5B4** — Prioritise crucial and mandatory fields — clean these first

**5C — Test the cleaning and mapping**

- ☐ **5C1** — Load cleaned samples to the target system and check them visually — look at the data in the interface, not just the import log
- ☐ **5C2** — Revisit and update your mapping and cleaning rules based on what the sample test reveals
- ☐ **5C3** — Define and specify your sample test data set for Step 6 — these are the confirmed, cleaned records you will use in structured testing

> ▶ **Worked example — Sage 50 → Sage X3, five mapping rows**
>
> *Drawn from the case study. Five real mismatch types from the Sage 50 → X3 mapping work, written exactly as they would appear in the Step 5 Simple Mapping Sheet (Source · Sample · Target · Sample · Clean & Transform Notes).*

| Source Field | Sample (Source) | Target Field | Sample (Target) | Clean & Transform Notes |
|:-|:-|:-|:-|:-|
| Country | GB | Country | United Kingdom | **Format / value mismatch.** Replace ISO 2-letter codes with full country names. GB → United Kingdom; US → United States; flag any other value for manual review. |
| DiscountRate | 10 (meaning 10 %) | DiscountRate | 0.1 | **Decimal-storage mismatch.** Source stores percentages as whole numbers; target stores as decimals. Divide all values by 100 on import. Validate against business rule: no discount above 0.5 (50 %) without sign-off. |
| Customer Type | Trade | CustomerCategory | Trade Customer | **Picklist mismatch.** Map source values to target picklist: Trade → Trade Customer; Retail → Retail Customer; Wholesale → Trade Customer (Wholesale). Any *new* target value to be confirmed with system admin before import. |
| WarehouseLocation | *(empty)* | WarehouseLocation | MAIN-A1 | **Mandatory target field with no source value.** Source field did not exist in Sage 50; target field is mandatory in Sage X3. Default to MAIN-A1 for all stocked products on initial load; allocate proper locations as part of post-go-live stock take. *Business decision recorded; not a clean-up rule.* |
| ProductCode | WIDGET-123 / blue, with extra stop on 12/11 | ProductCode | WIDGET-123 | **Free text contaminating a structured field.** Strip everything after the first space. Move the trailing narrative into the ProductNotes field. Flag any code that does not start with letters followed by - for manual review. |

*These five rows cover the five most common mismatch families — format, decimal storage, picklist, missing mandatory data, free text in a structured field. Most real mappings are dozens to hundreds of rows; the pattern is the same.*

## Your Turn

The thinking happens on the page; the production work happens in the proper tool.

**Exercise — 20 minutes, before you open your mapping tool.**

Pick the one area that matters most in your migration — for most businesses this is either customers or products. For that one area, complete the following before touching any fields.

**1. List the five fields you expect to be most problematic.**

These are the fields where you already suspect a mismatch, a format difference, or missing data. Write them down now, with your best guess at what the problem is.

| Field name | What you think the problem might be |
|:-:|:-:|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |

For each one, ask:

- Is it a format issue, a value issue, a type issue, or a structural issue?
- Can it be fixed with a simple rule, or does someone need to make a decision first?
- Is the source data actually there — or does it need to be created?
- Does this field appear in any document (invoice, PO, statement)?

**2. List your picklist fields for this area.**

Name every field in this area where the target system only accepts values from a fixed list. For each one, pull the accepted values from the target and compare them to what your source data actually contains. Note the gaps.

| Picklist field | Values in source | Values accepted by target | Gaps to resolve |
|:-:|:-:|:-:|:-:|
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |

**Then take it to the template.**

Move your decisions into the **Flow7 Step 5 Simple Mapping Sheet** — one sheet per area, five columns, real sample data from both sides. Complete the full mapping for this first area before moving to any other.

The Step 5 mapping sheet and the full project checklist are available to download at spdata.co.uk.

## What you have achieved in this chapter

Every source field has a target. Every mismatch has a written rule. Every picklist is resolved or escalated. A cleaned sample has loaded into the target system and passed your eye check. Your Step 6 test data set is defined and named. The next chapter puts the whole mapping through structured testing — deliberately, methodically, with a clear pass/fail criterion for every check.

## You're Ready to Move On When…

Step 5 is genuinely complete — and you are ready for Chapter 9, Test Before You Trust — when **all** of these are true:

- Every source field has been listed and assessed against the target.
- Every mismatch has a written cleaning or transformation rule.
- All mandatory target fields have a confirmed source value — or a recorded decision about what to do where source data does not exist.
- All picklist mismatches have been identified and a resolution agreed.
- Cleaned sample data has been loaded to the target system and checked **visually** — not just confirmed as "imported without error."
- Your mapping document has been updated to reflect what the sample test revealed.
- Documents (invoices, purchase orders, statements) have been checked — every field that appears in a document is included in the mapping.
- Your Step 6 test data set is defined: you know exactly which records you will use for structured testing and why.

If any of these is unresolved, do not proceed. Step 6 tests what you have built here. If the mapping is incomplete, the testing will be too — and the gaps will surface in production rather than in a controlled environment.

When those boxes are ticked, your data is cleaned, mapped, and sample-confirmed. In the next chapter you put it through structured testing — deliberately, methodically, and with a clear pass/fail criterion for every check.
