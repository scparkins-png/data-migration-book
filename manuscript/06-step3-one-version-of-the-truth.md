**CHAPTER 6**

# One Version of the Truth

## Step 3 — Define Your Data Master

**"You're not keeping everything — you're keeping the right things."**

## Where You Are in Flow7

You have done the groundwork. In **Chapter 4** you found every data source, including the ones nobody mentioned at first. In **Chapter 5** you took an honest look at the state of that data — the duplicates, the blanks, the formatting that drifts from record to record.

Now comes the decision that holds the rest of the migration together: out of everything you have found, **what is the real, authoritative version you are going to move?** This is Step 3 — defining your Data Master, or as Flow7 calls it, your **"one source of the truth."**

## In this chapter you will…

- Define your Master List — every source that will feed the master data set
- Draw your Master Map — a visual of how those sources combine into one set
- Build the physical Master Data Set in a tool you can manage
- Set up change control so nothing enters the master without sign-off
- Decide your golden-record rules and your exclusion list

## What you'll need from earlier chapters

- Your Step 1 source inventory (Chapter 4)
- Your Step 2 quality assessment findings — including which source wins where they disagree (Chapter 5)
- A drawing tool of your choice (PowerPoint, Miro or Lucid) for the Master Map
- A working tool for the master set — Excel for most teams; SQL or low-cost cloud tools (Skyvia, Zoho DataPrep) for larger jobs

## Why This Matters

When the same information lives in more than one place, those places disagree. The price on the spreadsheet is not the price in the accounting system. The customer's address in the CRM is two house moves out of date. One list says you stock 7,000 products; the warehouse says otherwise.

You cannot move all of those versions into a new system and hope it sorts itself out. It will not. As the Flow7 Step 3 guidance puts it, without a defined master you end up with a migration that imports everything and leaves the business to untangle the conflicts afterwards — and that untangling never actually happens. The duplicates and contradictions simply become permanent features of the new system.

Defining the master **before** you move anything is how you stop that happening. You decide, on purpose and in advance, which source wins when two sources disagree, which records are coming and which are being left behind, and where the authoritative copy of each thing actually lives. Every later step — knowing your destination (Chapter 7), mapping (Chapter 8), testing (Chapter 9) — builds directly on this decision.

## What You Are Actually Doing

Step 3 turns the loose findings of Steps 1 and 2 into a single, controlled, named thing. Flow7 breaks it into four parts, and they run in order.

**A. The Master List.** A plain register that names every data source you have *decided* to use — the specific files, databases, views, exports and reports that will feed your migration. For each one you record three things: what it is (an Excel file, a SQL view, a saved search, a report), exactly where it lives (a URL, a file path, a physical location), and who owns it.

**B. The Master Map.** A simple picture showing how those sources combine into one master set. It is a "show the team" tool more than a technical artefact — you can draw it in PowerPoint, Miro or Lucidchart, whatever you already use. Its job is to let you walk your colleagues and stakeholders through the shape of the migration in one glance.

**C. The Master Data Set.** The real thing. This is where you stop planning and physically bring the sources together into one combined set, following your List and your Map. How you build it depends on your skills, budget and the size of the job — more on the tools below.

**D. Backups and version control.** Before anyone touches the master set, you make sure it is backed up and version-controlled, so a wrong move is recoverable rather than catastrophic.

Two ideas sit underneath all four parts:

- **The golden record.** Where a customer, product or supplier exists in several sources, you decide the rules for which version becomes the single authoritative record, and how the others are merged into it or discarded.
- **The exclusion list.** Just as important as what you keep is what you deliberately leave behind — stale records, test data, archived information that does not need to come across. You write these down *with the reason*, so the decision is recorded rather than rediscovered as an argument later.

### ▶ Your Master Can Be a Spreadsheet

If you have just read part C and quietly panicked at the word "database" — stop. **A master set is defined by structure and process, not by software.** What makes something a master is not the tool it lives in; it is that it has a clear structure (one row per record, consistent columns, and a reliable unique identifier you have created yourself), and a process around it (one named owner, change control, version control and backups). An Excel file with all of that is a far better master than a database without it.

For a non-technical business doing the migration itself, **Excel is the right place to start, and this workbook recommends it as your starter tool.** It is the thing you already know how to use, and it is entirely capable of holding your master set while you make the decisions that actually matter.

On the Sage 50 → X3 project I reached for a combination of Excel and SQL, not because Excel cannot be a master, but because of the *job* in front of us — the volume of records, the number of sources being linked, and the number of people touching the data at once. The database was simply my tool of choice; low-cost tools such as Skyvia or Zoho DataPrep would have done the work too.

**Where Excel does strain** is scale and concurrency: hundreds of thousands of rows, complex joins across many sources, or lots of people editing the same file at the same time. Note that this is a *process* problem — how do you hold change control when ten people have the file open? — not a sign that Excel was the wrong choice. Start in Excel; move to a bigger tool only when the job, not the nerves, demands it.

## Key things to get right

Five disciplines keep the master set clean and useful.

**1. Excel is the right starter tool for non-technical teams.** A master set is defined by structure and process, not by software. If you can hold one row per record, with consistent columns and a unique identifier you have created yourself, Excel is the master. Move up to SQL, DataPrep or another tool only when the *job* — volume, concurrency, complexity — genuinely demands it.

**2. Create your own unique IDs.** Do not rely on SKUs, customer numbers or other source-system IDs as your unique identifier — they look unique and often are not. Generate your own (a simple sequence is fine) and carry it across every later step. At go-live, this is what lets you map new target-system IDs back to source records.

**3. Write down your golden-record rule before you merge.** "Address: Sage 50 wins over the spreadsheet" is a recorded decision; "we'll work it out as we go" is a fight waiting to happen. The conflict-resolution rules belong in the Master List, written down once, agreed once.

**4. Write down what you are leaving behind, with the reason.** The exclusion list is as important as the inclusion list — and the *reason* matters as much as the list itself. "Customers with no activity since 2018: excluded; archived in source system for legal retention" is a decision that survives. "I think we agreed not to take those" is not.

**5. Change control is non-negotiable.** Nothing enters or changes in the master set without being logged and signed off. If a new source emerges during a later step (it happens, especially in Steps 4 and 5), the answer is not to absorb it quietly — it is to update the Master List and the master set properly, through your change-control process.

## From the Field — Sage 50 to Sage X3

*The following is drawn from a real migration…*

*B*y the time this project reached Step 3, the assessment had already exposed how much work was hiding under the surface: more than 7,000 product records needing clean-up, stock figures that did not match the warehouse, sales and purchase orders with random text where product codes should have been, and — most awkward of all — critical knowledge such as product recipes and assembly instructions that lived in a few long-term employees' heads rather than in any system at all.

So defining a master set here was not simply a matter of picking the best of several existing copies. Much of the authoritative data **did not exist yet** and had to be created from scratch — informal, in-people's-heads knowledge converted into proper structured records. That makes this a particularly honest example of Step 3, because it shows the master set as something you *build and control*, not just something you *select*.

Here is how the master set was actually assembled:

- A Sage 50 backup was loaded into a **local copy of Sage 50** on a development machine — solving a real Step 1 problem, the painfully slow remote VPN connection to the live system.
- Data tables were extracted from that local Sage 50 into Excel (an extract file nicknamed "SQLLINK").
- Everything was imported into a **local SQL database** with proper checks — this became the controlled environment for the master set. (SQL was simply my tool of choice; low-cost cloud tools such as Skyvia or Zoho DataPrep would have done the job too.)
- For the data that did not exist anywhere, **new Excel data-collection files were created with clear rules** and placed on the partner company's SharePoint for the team to populate.
- SQL **views** were then built to shape the master data into outputs matching the target system's import templates — ready for mapping in Step 5.

And the change-control warning from earlier in this chapter? *The team didn't always follow the rules for the new data files — "but that's people for you!"* Even an experienced practitioner with a tightly designed master set ran into exactly the leak this step is meant to guard against. That is precisely why the change-control process is part of Step 3 and not an afterthought.

One more practical lesson worth carrying forward: when records eventually land in the new system they are given **new IDs**. So part of building a usable master set is creating your *own* reliable unique identifier for each record in the source — and not trusting things that merely *look* unique, such as product SKUs or customer numbers, which often are not.

## Your Checklist

These items are taken directly from Step 3 of the Flow7 Data Migration Project Checklist. Tick each one only when it is genuinely done.

**3A — Create the Master List**

- ☐ **3A1** — Name each data source file that will be used (e.g. XLSX / SQL / view / saved search / report)
- ☐ **3A2** — Record its location with the specifics needed to access it (URL / path / physical location)
- ☐ **3A3** — Assign and record an owner for each source — the person responsible for it under change control
- ☐ **3A4** — Document the change-control process for the sources, and make it clear to the whole team

**3B — Draw the Master Map**

- ☐ **3B1** — Choose a drawing tool (e.g. PowerPoint, Miro, Lucidchart)
- ☐ **3B2** — Create a visual Master Map showing how the sources feed the master set

**3C — Build the physical Master Set**

- ☐ **3C1** — Outline the master-set plan to the team and stakeholders
- ☐ **3C2** — Using your Master Map, collect and link the sources together as defined
- ☐ **3C3** — Output some data samples for each area (or the full set, depending on your plan)

**3D — Back up the sources**

- ☐ **3D1** — Create a backup plan for the data sources
- ☐ **3D2** — Set up version control for the master set

> ▶ **Worked example — Sage 50 → Sage X3, Master Map**
>
> *The full Master Map page from the Step 3 template, drawn from the case study. Four agreed data sources feed the central Master Set through SQL views; the red boxes are sources identified but not yet defined or agreed.*

{{figure: fig-06-02 | Figure 6.2 — Sage 50 to Sage X3 Master Map, showing four agreed data sources combining into the central Master Set via SQL views}}

*Figure 6.2 — Sage 50 to Sage X3 Master Map, showing four agreed data sources combining into the central Master Set via SQL views*

*Source: Flow7 Step 3 — Define Your Data Master, Help Notes Part B (SP Data Consultancy Ltd, V1.0).*

The diagram restated in table form:

| Element | What it is | Source / nature |
|:-|:-|:-|
| Source 1 — S50 DATA | Sage 50 database backup | Internal database |
| Source 2 — PRODUCT MASTER xls | Curated product data | Company file |
| Source 3 — BOM MASTER xls | Assembly instructions (Bills of Materials) | Company file — created in this project |
| Source 4 — ROUTINGS csv | Manufacturing routing data | Company file — created in this project |
| The Master Set | SQL views combining all four sources | Local SQL Server |
| Outputs | Suppliers · Customers · Products (with Sites, Costs, Routes) · BOMs · Sales Orders · Purchase Orders · Opening Balances | Master Set views, shaped for Sage X3 import templates |
| Red boxes (SO X REF, PO X REF, STOCK) | Sources identified but not yet defined or agreed | Open items pending change-control sign-off |

*The Master Map made the shape of the migration visible to the team in one glance — sources on the left, the master set in the middle, outputs and target on the right — and the red boxes were the visible record of what still needed to be decided.*

## Your Turn

You do not need a SQL database or special software to make the core Step 3 decisions. You need to make them on paper first, then move the real work into the proper tools.

**Exercise — 15 minutes, on the page.**

Pick **one** important data entity for your migration — your customers, your products, your suppliers, whichever matters most. For that one entity, write down:

1. **Which sources hold it?** List every place this entity currently lives (pull these from your Chapter 4 inventory).
   {{write-in}}
2. **Which source wins?** If two sources disagree about the same record, which one is the authoritative version — and why?
   {{write-in}}
3. **What are you leaving behind?** Name at least one category of record for this entity that you will *not* migrate (e.g. customers with no activity in five years), and the reason.
   {{write-in}}
4. **Who owns it?** Name the single person responsible for this source under change control.
   {{write-in}}

If you cannot answer question 2 yet, that is a finding, not a failure — it tells you exactly which conversation to have before you go further.

**Then take it to the template.**

The thinking happens on the page; the production work happens in the proper tool. Move your decisions into the **Flow7 Step 3 — Define Your Data Master** template, which gives you the full Master List (source name, location, owner) ready to fill in for every source, not just one. Build your Master Map alongside it in whatever drawing tool you prefer, and write your change-control rule at the top of the Master List so everyone can see it.

I will mention this a few times. Migrating data is not a straight line. Flow 7 is the path but as more information is gathered and understood you may track back to revisit a source or data quality issue, to then return to the point you discovered it.This often happens when mapping and transforming data for the new system or testing a process,  only to discover a core set of data is required to complete task.This in my experience is normal and provides for a better outcome.

## What you have achieved in this chapter

You have one defined, controlled, owned source of the truth. Every record that will be migrated lives in the Master Data Set; every record that will not is on the exclusion list with a reason. Change control protects what you have built. The next chapter turns to the other end of the journey — the system the data is moving into — and works out exactly what it will accept and how people will use it.

## You're Ready to Move On When…

Step 3 is genuinely complete — and you are ready for Chapter 7, Know Your Destination — when **all** of these are true:

- Your **Master List** names every source, with its location and a named owner.
- A **change-control process** is written down and the team knows the rule: nothing enters or changes in the master set without sign-off.
- Your **Master Map** exists and you have walked the team and stakeholders through it.
- The **physical master set** has been built from the defined sources, and you have produced sample outputs from it.
- Your **golden-record rules** (which version wins) and your **exclusion list** (what you are leaving behind, and why) are recorded decisions, not opinions in someone's head.
- The sources and master set are **backed up and under version control**.

When those boxes are ticked, you have your one source of the truth. In the next chapter you turn to the other end of the journey — the system you are moving *into* — and find out what it will actually accept.
