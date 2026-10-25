**CHAPTER 4**

# Know Your Data Sources

### *Step 1 of the Flow7 Migration System*

*You have your plan. Now the real work begins — and it begins not by moving data, but by finding all of it. This chapter aligns to Step 1 of the Flow7 Migration System. Do not skip it because you think you already know where your data lives. That assumption is precisely the one this chapter exists to challenge.*

---

**"The migrations that succeed are the ones where the team knows exactly what they have, where it lives, and who owns it — before they touch a single record."**

---

## Where You Are in Flow7

Your project plan is in place (*Before You Start*), so you have agreed *what* you are migrating and *why*. Step 1 is the first numbered step of the Flow7 Migration System — it answers the next question: *do you actually know where all that data lives?*

---

## In this chapter you will…

- Find every place your business data lives — including the unofficial ones
- Record what each source is, who owns it, and how to get data out
- Set a priority for each source so you know what matters most
- Assess how easy or hard each export will be, and how long it will take
- Validate every source entry with the person who actually uses it

---

## What you'll need from earlier chapters

- A list of the people you can ask in each department
- Time on the diary to walk around (or video-call) the people who use the data each day

---

## Why This Matters

In the planning chapter you agreed *what* you are migrating to and *why*. This step answers the next question: **where does all that data actually live?**

With the plan set, **your first real task is a full inventory of your data sources** — every one named and owned. Get it right and you carry something solid into every step that follows: you know what to assess for quality, what to consolidate into the master set, what to map against the new system(s). By accounting for every source up front it helps align the business processes to the rest of the project and not miss anything. Now if later extra sources materialise and this can occur, then update the Data Source Inventory.

---

## What You Are Actually Doing

Step 1 — *Know Your Data Sources* — is the work of researching and recording **every place your business data currently lives**, in a simple inventory, alongside the supporting information that makes each source usable: who owns it, what version it is, how critical it is, and how hard it will be to get the data out.

That last point matters. "Knowing your sources" is not only a list of system names. For each source you are capturing three layers of information:

1. **What it is** — the system name, type, version, the category of data it holds, and the business process it serves.
2. **Who owns it** — the named person responsible for that data, and the person who actually understands its quirks day to day. These are often not the same person.
3. **How you get data out of it** — the export method, how easy that is, how long it takes, and how large the resulting file is.
4. **What business processes** create or work with that data

The Flow7 Step 1 tool splits this into two working sheets for exactly this reason: an **Inventory** sheet (the *what* and *who*) and an **Export Assessment** sheet (the *how*). A third sheet, the **Business Process List**, captures how data is added and any workarounds the team has built up over time.

Understanding business process, and both business and system terminology and how they match is crucial in a migration. See Chapter XXX

> 💡 **What counts as a "data source"?** More than you think. A data source is anywhere business information is stored or maintained, including: - Main business systems — CRM, ERP, accounting software - Departmental spreadsheets - Legacy systems you rarely use - Personal data stores on individual computers - Paper records that might need digitising, Emails - Backup files holding historical data

---

## Key things to get right

Four disciplines turn a good data source inventory into a complete one.

**1. Ask the people who use the data daily, not just management.** Department heads know their reporting systems. Front-line staff know the spreadsheets, the workarounds and the standalone tools that keep the work moving. The receptionist who quietly maintains a "do not call" list, the sales rep who keeps lead data in a personal spreadsheet, the warehouse manager who runs a stock notebook — these are real data sources, and they only surface if you ask.

**2. Be specific about names and versions.** "Microsoft Dynamics" is a description, not a system identification. "Dynamics NAV 2013, customised" is a system identification — and the tools, exports, and risks are completely different. Capture the exact name and version of every source. The migration tools, the export routes and the level of partner involvement all follow from the right answer here.

**3. Treat every system as in scope until you have explicitly excluded it.** Including paper. Including the database the warehouse uses that nobody had mentioned. Including the spreadsheet on the receptionist's laptop. If a source holds data anyone in the business relies on for the processes this migration should cover, it belongs on your list — even if the decision turns out to be *we are not migrating this*. A documented exclusion is fine. A missed source is not.

**4. Validate every entry with the named owner.** A source nobody owns is a source nobody is responsible for. The Inventory sheet has a "validated with owner" column for this reason — once that column is ticked, both you and the owner have agreed what the source is, what it holds, and what the priority is.

---

## From the Field

### *Sage 50 → Sage X3: what Step 1 actually surfaced*

The case study running through this workbook follows a successful manufacturer that had been bought out and needed to move from **Sage 50 to Sage X3**. Everyone assumed it would be straightforward — two to three months at most. Same software family, healthy business, so the data must be fine. *Wrong on all counts.*

I was brought in as the ETL consultant — *Extract, Transform, Load*: the work of taking messy data out of old systems and making it work properly in new ones. Rather than take the "it'll be simple" assumption at face value, I applied the Flow7 method, starting with a proper look at the sources.

Here is what knowing the sources actually revealed:

- **Critical knowledge lived in people, not systems.** Product recipes and assembly instructions existed only in one or two long-term employees' heads — not in any system that could be exported.
- **Processes had grown organically with zero documentation.** New products were added daily with the bare minimum of information, following habits nobody had ever written down.
- **Getting the data out was potentially slow.** Working remotely over the company's VPN was painfully slow, but was required geographically for the team and costs, which made every export a longer job than anyone had budgeted for so we needed to replicate live data.

None of these are *data quality* problems in the narrow sense — those come in Chapter 2. They are *source* problems: things you can only plan around if you find them first. A migration plan built on "the data's in Sage 50, we'll just export it" would have hit every one of these as a nasty surprise.

**The lesson I keep coming back to:** *never accept data assumptions — have a look.* The businesses that succeed are the ones that invest the time upfront in understanding what they are working with, rather than assuming.

---

## Your Checklist

These items are taken directly from the **Sources — Know Your Data Sources** section of the Flow7 Data Migration Project Plan Checklist and the Step 1 source sheets. Work through them for your own project. The full versions, with status, owner and date columns, live in the downloadable Excel checklist.

**1A — Create your Data Source Inventory**

| ✓ | Task |
|:-:|:-|
| ☐ | Record the **System Name** for each source (internal or software name — e.g. NetSuite, Sage X3, document archive, Xero, HubSpot) |
| ☐ | Record the **System Type** (e.g. ERP, CRM, Excel, database, SQL database, accounting) |
| ☐ | Record the **Version** — the specific software version or build, to narrow things down (e.g. Enterprise, V1.13, Build 132.32.21) |
| ☐ | Record the **Category** of data (e.g. customer information, products, historical archive, financial) |
| ☐ | Record the **Process / department** the source serves (e.g. Sales, HR, Warehouse, Marketing, Invoices, Warranties) |
| ☐ | Set a **Business Priority** for each source — High / Medium / Low |
| ☐ | Assign a named **Owner / expert** for each system or process |
| ☐ | **Validate** each source entry *with its owner* — confirm it is agreed and correct |

**1B — Perform and document your Data Export Assessment**

| ✓ | Task |
|:-:|:-|
| ☐ | Carry the **System Name** forward and collate any **credentials** needed to access it |
| ☐ | Record the **Export Type** — manual (Excel / CSV / TXT) or automated (API / reports / database process) |
| ☐ | Add **Notes** to help the export (e.g. "use Sage X3 ZEXPORT1 template") |
| ☐ | Record the **Speed or duration** of export in general terms — Slow / Moderate / Fast |
| ☐ | Record **how easy** it is to export — Easy / Moderate / Hard |
| ☐ | Record the **time** a full export of each data set takes |
| ☐ | Record the **data size** of each export (TB / GB / MB) |

**1C — Create a Business Process List** *(optional but recommended)*

| ✓ | Task |
|:-:|:-|
| ☐ | Name each **Process** and the **Department** it belongs to |
| ☐ | Describe the process and any **workarounds** the team uses |
| ☐ | Record **how data is added** to the source |
| ☐ | Note any **special tags, filters, labels or notations** in use |
| ☐ | Set a **Business Priority** and name the **owner / expert** for the process |

---

> 📋 **Worked example — to be added**
>
> *A populated example of a Step 1 Data Sources Inventory (1A) and Export Assessment (1B) will be added here from a real client engagement (anonymised). It will show how to capture system name, version, category, owner and export details for half a dozen sources of mixed type — main ERP, departmental spreadsheets, a legacy database, and a paper record.*

---

## Your Turn

The exercises below are quick, on-the-page starting points. The full production version of this work belongs in the Flow7 templates or your own version— see *Now Go to the Full Template*, below.

### Exercise 1.1 — Run a Five-Minute Source Brainstorm

Before you organise anything, simply list every place data might live. Do not filter — write down everything, including the unofficial spreadsheets and the "we don't really use that any more" systems. Your initial Readiness assessment will have a few for starters, but you likely will find more, when speaking to your team.

| # | Where data might live | Department / who uses it |
|:-:|:-:|:-:|
| 1 |   |   |
| 2 |   |   |
| 3 |   |   |
| 4 |   |   |
| 5 |   |   |
| 6 |   |   |
| 7 |   |   |
| 8 |   |   |

**Prompt to push past the obvious:** for each department — Sales, Finance, Operations, HR, Warehouse, Customer Service — ask *"what do you keep that isn't in the main system?"* The honest answers go in the table above.

### Exercise 1.2 — Mini-Inventory for Your Top Three Sources

Take the three highest-priority sources from Exercise 1.1 and capture the core inventory detail. This is a scaled-down version of the real Inventory sheet.

| Source | System type | Version (be specific) | Data category | Owner (named person) | Priority (H/M/L) |
|:-:|:-:|:-:|:-:|:-:|:-:|
|   |   |   |   |   |   |
|   |   |   |   |   |   |
|   |   |   |   |   |   |

If you cannot fill the **Version** or **Owner** columns for any source, that is a finding, not a gap to ignore. Note who you need to ask, and add it to your actions.

### Exercise 1.3 — One-Line Export Reality Check

For your single most important source, answer one question honestly:

**"If I had to export everything from this source today, how would I do it, how long would it take, and who has the login?"**

Write the answer here:

{{write-in}}

If you cannot answer all three parts, you have just found the first job for your Export Assessment.

---

### Now Go to the Full Template

The exercises above are your warm-up. Your real source inventory belongs in the **Flow7 Step 1 source sheets** and the **Flow7 Data Migration Project Plan Checklist** — the Excel workbook that accompanies this book. Between them they give you:

- The full **Data Sources Inventory** sheet (Step 1A)
- The **Data Source Export Assessment** sheet (Step 1B)
- The **Business Process List** sheet (Step 1C)
- Status, owner, priority and validation columns for every row

Download the templates at: **stuartparkins.com**

---

## What you have achieved in this chapter

You have a complete, named, prioritised inventory of every data source that matters. Each source has an owner, an export method, an estimated time and difficulty, and a place in the queue. Where the data lives is no longer guesswork — it is documented. The next chapter takes this inventory and works out the *condition* of what you have found.

---

## You're Ready to Move On When…

You are ready to move from finding your sources to assessing their quality (Chapter 5) when all of the following are true. Be honest — a missed source here costs far more later.

| Gate | ✓ |
|:-|:-:|
| Every system, spreadsheet, database and paper store that holds in-scope data has been listed | ☐ |
| You have asked frontline staff — not just management — and chased down unofficial sources | ☐ |
| Each source has an exact name and version recorded, not a generic description | ☐ |
| Each source has a named owner, and each entry has been validated *with* that owner | ☐ |
| Each source has a business priority assigned | ☐ |
| You know, for each source, how the data will be exported, how long it takes and who has access | ☐ |
| Your inventory is stored somewhere the whole team can see and add to | ☐ |
| You have aligned core/critical business processes to the data sources that currently run or create the data. | ☐ |

**If you cannot tick every box, do not start assessing or moving data yet.** An undiscovered source does not become less of a problem once the migration is under way — it becomes a more expensive one. Proper source investigation can feel like delay, but in practice it reduces overall project time, because it stops the surprises that force you to re-plan .

You know where the data lives and what makes up that data.In the next chapter, you check how good that data is?
