**CHAPTER 1**

# Know Your Data Sources

### *Step 1 of the Flow7 Migration System*

**"The migrations that succeed are the ones where the team knows exactly what they have, where it lives, and who owns it — before they touch a single record."**

## Where You Are in Flow7

{{progress: 1}}

Your plan is agreed, so you know *what* you are migrating and *why*. Step 1 asks the next question: do you actually know where all your data lives? Do not skip it because you think you already know — that assumption is exactly what this step tests.

## In this chapter you will…

- Find every place your business data lives — including the unofficial ones
- Record what each source is, who owns it, and how to get data out
- Set a priority for each source so you know what matters most
- Assess how easy or hard each export will be, and how long it will take
- Validate every source entry with the person who actually uses it

## What you'll need

- Your Outline Migration Statement and readiness assessment results (from *Create Your Plan*)
- A list of the people you can ask in each department
- Time in the diary to walk round (or video-call) the people who use the data each day

## Why This Matters

A complete list of your data sources is the foundation for everything that follows. With it, you know what to check for quality (Step 2), what to combine into your master set (Step 3) and what to map into the new system (Step 5). A source you find now is a line on a list; a source you find halfway through the migration is a re-plan.

> ↩ **Tracking back.** If an extra source turns up later — and it can — come back to your inventory, add it, and carry on. That is the method working, not failing.

## What You Are Actually Doing

Step 1 is the work of finding and recording **every place your business data currently lives**, in one simple inventory.

> 💡 **What counts as a "data source"?** More than you think. A data source is anywhere business information is stored or kept, including:
>
> - main business systems — CRM, ERP, accounting software
> - departmental spreadsheets
> - legacy systems you rarely use
> - personal data stores on individual computers
> - emails
> - paper records that might need digitising
> - backup files holding historical data

For each source you capture four things:

1. **What it is** — the system name, type and version, and the kind of data it holds.
2. **Who owns it** — the named person responsible for that data, and the person who actually understands its quirks day to day. These are often not the same person.
3. **How you get data out of it** — the export method, how easy that is, how long it takes, and how large the resulting file is.
4. **Which business processes use it** — how data gets added, and any workarounds the team has built up over time.

The Flow7 Step 1 templates give each of these a home: the **Inventory** sheet (what and who), the **Export Assessment** sheet (how) and the **Business Process List** (the processes).

The processes and the words your business uses matter as much as the data itself — see *Know the Business — and Its Language* in Create Your Plan.

## Key things to get right

Four disciplines turn a good data source inventory into a complete one.

**1. Ask the people who use the data daily, not just management.** Department heads know their reporting systems. Front-line staff know the spreadsheets, the workarounds and the standalone tools that keep the work moving. The receptionist who quietly maintains a "do not call" list, the sales rep who keeps lead data in a personal spreadsheet, the warehouse manager who runs a stock notebook — these are real data sources, and they only surface if you ask.

**2. Be specific about names and versions.** "Microsoft Dynamics" is a description, not a system identification. "Dynamics NAV 2013, customised" is a system identification — and the tools, exports, and risks are completely different. Capture the exact name and version of every source. The migration tools, the export routes and the level of partner involvement all follow from the right answer here.

**3. Treat every system as in scope until you have explicitly excluded it.** Including paper. Including the database the warehouse uses that nobody had mentioned. Including the spreadsheet on the receptionist's laptop. If a source holds data anyone in the business relies on for the processes this migration should cover, it belongs on your list — even if the decision turns out to be *we are not migrating this*. A documented exclusion is fine. A missed source is not.

**4. Validate every entry with the named owner.** A source nobody owns is a source nobody is responsible for. The Inventory sheet has a "validated with owner" column for this reason — once that column is ticked, both you and the owner have agreed what the source is, what it holds, and what the priority is.

## From the Field

### *Sage 50 → Sage X3: what Step 1 actually surfaced*

The case study running through this handbook follows a successful manufacturer that had been bought out and needed to move from **Sage 50 to Sage X3**. Everyone assumed it would be straightforward — two to three months at most. Same software family, healthy business, so the data must be fine. *Wrong on all counts.*

I was brought in as the ETL consultant — *Extract, Transform, Load*: the work of taking messy data out of old systems and making it work properly in new ones. Rather than take the "it'll be simple" assumption at face value, I applied the Flow7 method, starting with a proper look at the sources.

Here is what knowing the sources actually revealed:

- **Critical knowledge lived in people, not systems.** Product recipes and assembly instructions existed only in one or two long-term employees' heads — not in any system that could be exported.
- **Processes had grown organically with zero documentation.** New products were added daily with the bare minimum of information, following habits nobody had ever written down.
- **Getting the data out was slow.** The team had to work remotely over the company's VPN, and it was painfully slow. Every export took longer than anyone had budgeted for, so we set up a local copy of the data to work from.

None of these are *data quality* problems in the narrow sense — those come in Chapter 2. They are *source* problems: things you can only plan around if you find them first. A migration plan built on "the data's in Sage 50, we'll just export it" would have hit every one of these as a nasty surprise.

**The lesson I keep coming back to:** *never accept data assumptions — have a look.* The businesses that succeed are the ones that invest the time upfront in understanding what they are working with, rather than assuming.

## Your Checklist

The essentials for Step 1. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 1A | List every source — systems, spreadsheets, paper records, backups — including the unofficial ones | ☐ |
| 1A | Record the exact name and version of each source | ☐ |
| 1A | Give each source a named owner and a priority (High / Medium / Low) | ☐ |
| 1A | Check each entry with its owner and mark it validated | ☐ |
| 1B | For each source, record how to export it, how long that takes, how big the file is and who has the login | ☐ |
| 1C | List the business processes behind each source, including any workarounds *(recommended)* | ☐ |

> 📋 **Worked example — to be added**
>
> *A populated example of a Step 1 Data Sources Inventory (1A) and Export Assessment (1B) will be added here from a real client engagement (anonymised). It will show how to capture system name, version, category, owner and export details for half a dozen sources of mixed type — main ERP, departmental spreadsheets, a legacy database, and a paper record.*

## Your Turn

Two quick exercises to start on the page. Your real inventory goes in the template.

### Exercise 1.1 — Run a Five-Minute Source Brainstorm

Before you organise anything, simply list every place data might live. Do not filter — write down everything, including the unofficial spreadsheets and the "we don't really use that any more" systems. Your readiness assessment will have given you a few to start with; you will find more when you talk to your team.

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

**Push past the obvious:** for each department — Sales, Finance, Operations, HR, Warehouse, Customer Service — ask *"what do you keep that isn't in the main system?"* The honest answers go in the table above.

### Exercise 1.2 — One-Line Export Reality Check

For your single most important source, answer one question honestly:

**"If I had to export everything from this source today, how would I do it, how long would it take, and who has the login?"**

{{write-in}}

If you cannot answer all three parts, you have just found the first job for your Export Assessment.

> 📄 **Your template.** Flow7 Step 1 — *Data Sources Inventory* (1A), *Export Assessment* (1B) and *Business Process List* (1C), with progress tracked in the *Flow7 Data Migration Project Plan Checklist*. Download at **stuartparkins.com**.

## What you have achieved in this chapter

You have a complete, named, prioritised inventory of every data source that matters. Each source has an owner, an export method, an estimated time and difficulty, and a place in the queue. Where the data lives is no longer guesswork — it is documented.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Every in-scope source is on the list — including the unofficial ones you found by asking frontline staff | ☐ |
| Each source has its exact name and version recorded, not a generic description | ☐ |
| Each source has a named owner and a priority, and the owner has validated the entry | ☐ |
| You know how each source will be exported, how long it takes and who has access | ☐ |
| You have linked your critical business processes to the sources that run them | ☐ |
| The inventory is stored where the whole team can see and add to it | ☐ |

**If you cannot tick every box, do not start assessing or moving data yet.** A source you have not found does not get smaller once the migration is under way — it gets more expensive.

**Next:** Chapter 2 — how good is the data you have found?

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: the shadow systems, the undocumented processes, and the people who really hold the knowledge. You will pull these notes together in the closing chapter, *Know the Business*.
