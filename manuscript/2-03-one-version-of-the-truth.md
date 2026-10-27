**CHAPTER 3**

# One Version of the Truth

### *Step 3 of the Flow7 Data Migration System — Define Your Data Master*

**"You're not keeping everything — you're keeping the right things."**

## Where You Are in Flow7

{{progress: 3}}

You know where your data lives and what condition it is in. Step 3 is the decision that holds the rest of the migration together: out of everything you have found, **what is the real, authoritative version you are going to move?** Flow7 calls this your **one source of the truth.**

## In this chapter you will…

- Define your Master List — every source that will feed the master data set
- Draw your Master Map — a picture of how those sources combine into one set
- Build the physical Master Data Set in a tool you can manage
- Decide your golden-record rules and your exclusion list
- Set up change control so nothing enters the master without sign-off

## What you'll need

- Your Step 1 source inventory
- Your Step 2 quality findings — including which source wins where they disagree
- A drawing tool you already use (PowerPoint, Miro or Lucidchart) for the Master Map
- A working tool for the master set — Excel for most teams; SQL or low-cost cloud tools (Skyvia, Zoho DataPrep) for larger jobs

## Why This Matters

When the same information lives in more than one place, those places disagree. The price on the spreadsheet is not the price in the accounting system. The customer's address in the CRM is two house moves out of date. The stock list says 40; the shelf says 28.

You cannot move all of those versions into a new system and hope it sorts itself out. It will not. Without a defined master, a migration imports everything and leaves the business to untangle the conflicts afterwards — and that untangling never actually happens. The duplicates and contradictions simply become permanent features of the new system.

Defining the master **before** you move anything stops that. You decide, on purpose and in advance, which source wins when two disagree, which records are coming and which are staying behind, and where the authoritative copy of each thing lives. Every later step builds directly on this decision.

## What You Are Actually Doing

Step 3 turns the findings of Steps 1 and 2 into a single, controlled, named thing. It has four parts, done in order:

1. **The Master List.** A plain register of every source you have *decided* to use — the specific files, databases, views, exports and reports. For each one: what it is, exactly where it lives (a file path, a web address, a physical location), and who owns it.
2. **The Master Map.** A simple picture showing how those sources combine into one master set. It is a "show the team" tool more than a technical one; its job is to let you walk colleagues through the shape of the migration in one glance.
3. **The Master Data Set.** The real thing — where you physically bring the sources together into one combined set, following your List and your Map.
4. **Backups and version control.** Before anyone touches the master set, make sure it is backed up and version-controlled, so a wrong move can be undone.

Two decisions sit underneath all four:

- **The golden record.** Where a customer, product or supplier exists in several sources, you decide the rules for which version becomes the single authoritative record, and how the others are merged into it or discarded.
- **The exclusion list.** Just as important as what you keep is what you deliberately leave behind — stale records, test data, archives that do not need to come across. Write each one down *with the reason*, so the decision is on record rather than rediscovered as an argument later.

> 🔑 **Key idea — your master can be a spreadsheet**
>
> If the word "database" just made you nervous — stop. **A master set is defined by structure and process, not by software.** What makes it a master is a clear structure (one row per record, consistent columns, and a unique ID you have created yourself) and a process around it (one named owner, change control, version control and backups). An Excel file with all of that is a far better master than a database without it.
>
> For a non-technical business doing its own migration, **Excel is the right place to start.** You already know how to use it, and it is entirely capable of holding your master set while you make the decisions that matter. Excel strains with scale and with lots of people editing at once — but that is a reason to move up when the *job* demands it, not a reason to avoid starting there.

## Key things to get right

Four disciplines keep the master set clean and useful.

**1. Create your own unique IDs.** Do not rely on SKUs, customer numbers or other source-system IDs as your unique identifier — they look unique and often are not. Generate your own (a simple sequence is fine) and carry it through every later step. At go-live, this is what lets you trace the new system's records back to your source records.

**2. Write down your golden-record rule before you merge.** "Address: Sage 50 wins over the spreadsheet" is a recorded decision; "we'll work it out as we go" is a fight waiting to happen. Write the rules into the Master List once, and agree them once.

**3. Write down what you are leaving behind, and why.** "Customers with no activity since 2018: excluded; kept in the source system for legal retention" is a decision that survives. "I think we agreed not to take those" is not.

**4. Change control is non-negotiable.** Nothing enters or changes in the master set without being logged and signed off. If a new source turns up later, the answer is not to absorb it quietly — it is to update the Master List and the master set properly, through your change-control process.

> ↩ **Tracking back.** Migrating data is not a straight line. As you map and test, you will sometimes find that a core piece of data is missing, or a quality problem is bigger than you thought. When that happens, come back here, add it to the master through change control, and then pick up where you left off. In my experience this is normal — and it produces a better result.

## From the Field

### *Sage 50 → Sage X3: building a master that didn't exist yet*

By Step 3, the assessment had already shown how much was hiding under the surface — more than 7,500 product records needing clean-up, and product recipes and assembly instructions that lived only in a few long-serving employees' heads.

So defining the master here was not just a matter of picking the best of several existing copies. Much of the authoritative data **did not exist yet** and had to be created from scratch. That makes it an honest example of Step 3: the master set as something you *build and control*, not just something you *select*.

Here is how it was assembled:

- A Sage 50 backup was loaded into a **local copy of Sage 50** on a development machine — which also solved the painfully slow remote connection from Step 1.
- Data tables were extracted from that local copy into Excel.
- Everything was imported into a **local SQL database** with proper checks; this became the controlled home of the master set. (SQL was simply my tool of choice — Skyvia or Zoho DataPrep would have done the job too.)
- For data that did not exist anywhere, **new Excel collection files were created with clear rules** and shared with the team to fill in.
- SQL **views** then shaped the master data into outputs matching the new system's import templates, ready for mapping in Step 5.

And the change-control rule? *The team didn't always follow the rules for the new data files — "but that's people for you!"* Even with a tightly designed master set, the leak this step guards against still happened. That is exactly why change control belongs in Step 3, not as an afterthought.

It is also why I created our own unique ID for every record. When records landed in Sage X3 they were given new IDs, and ours was the only reliable way to trace each one back to where it came from.

## Your Checklist

The essentials for Step 3. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 3A | List every source that will feed the master — what it is, where it lives and who owns it | ☐ |
| 3A | Write down your change-control rule and make sure the whole team knows it | ☐ |
| 3B | Draw your Master Map and walk the team through it | ☐ |
| 3C | Build the master set from your listed sources, with your own unique ID for every record | ☐ |
| 3C | Record your golden-record rules and your exclusion list (with reasons), then produce sample outputs | ☐ |
| 3D | Back up the sources and put the master set under version control | ☐ |

> 📋 **Worked example — Sage 50 → Sage X3, Master Map**
>
> *The Master Map page from the Step 3 template, drawn from the case study. Four agreed data sources feed the central Master Set through SQL views; the red boxes are sources identified but not yet defined or agreed.*

{{figure: fig-c3-01 | Figure 3.1 — Sage 50 to Sage X3 Master Map, showing four agreed data sources combining into the central Master Set via SQL views}}

*Figure 3.1 — Sage 50 to Sage X3 Master Map, showing four agreed data sources combining into the central Master Set via SQL views*

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

*The Master Map made the shape of the migration visible in one glance — sources on the left, the master set in the middle, outputs on the right — and the red boxes were the visible record of what still needed deciding.*

## Your Turn

You do not need a database to make the core Step 3 decisions. Make them for one entity first, straight into the template.

### Exercise 3.1 — One Entity, Four Decisions

Pick **one** important data entity — your customers, your products, your suppliers, whichever matters most. For that one entity, answer:

1. **Which sources hold it?** List every place it currently lives (from your Step 1 inventory).
2. **Which source wins?** If two sources disagree about the same record, which one is the authority — and why?
3. **What are you leaving behind?** Name at least one category of record you will *not* migrate, and the reason.
4. **Who owns it?** Name the one person responsible for this data under change control.

If you cannot answer question 2 yet, that is a finding, not a failure — it tells you exactly which conversation to have next.

**Where to record it:** your Step 3 *Define Your Data Master* template. Your answers to questions 2 and 4 become the change-control rule at the top of the Master List.

> 📄 **Your template.** Flow7 Step 3 — *Define Your Data Master* (Master List, with your change-control rule written at the top), plus your Master Map in whichever drawing tool you prefer. Progress is tracked in the *Flow7 Data Migration Project Plan Checklist*. Download at **stuartparkins.com**.

## What you have achieved in this chapter

You have one defined, controlled, owned source of the truth. Every record that will be migrated lives in the master set; every record that will not is on the exclusion list with a reason. Change control protects what you have built.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Your Master List names every source, with its location and a named owner | ☐ |
| A change-control rule is written down and the team knows it: nothing enters or changes in the master without sign-off | ☐ |
| Your Master Map exists and you have walked the team through it | ☐ |
| The master set has been built from the listed sources, with your own unique ID for every record, and you have produced sample outputs | ☐ |
| Your golden-record rules and exclusion list are recorded decisions, not opinions in someone's head | ☐ |
| The sources and the master set are backed up and under version control | ☐ |

**If you cannot tick every box, finish building your master before moving on.** Everything that follows is mapped, tested and loaded from this set.

**Next:** Chapter 4 — turn round and get to know the system you are moving *into*.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: what it considers true when forced to choose, and the rules that now decide the authoritative version. You will pull these notes together in the closing chapter, *Know the Business*.
