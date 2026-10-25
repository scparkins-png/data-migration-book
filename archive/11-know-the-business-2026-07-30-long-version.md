<!--
ARCHIVED — not part of the manuscript build.
Source: Google Doc 1iTZv2-4fzTaKqz9z-cJx4s5RZCl6TtuWUIC72HhY8H0 ("11-Don't Let a Data Migration Panic You-Know the Business"), created 30 July 2026.
Superseded on 3 August 2026 by the shorter capstone (manuscript/11-know-the-business.md) plus the front primer now inside Create Your Plan.
Kept because it holds material the newer version dropped: "In this chapter you will…", the full Terminology Translator section, the FULLNAME/OPTEDIN mapping table, the "Your Turn" exercise, and an editorial note about signposts in every step chapter.
-->

**CHAPTER 11**

# Know the Business

### *The way they work, and the words they use — the thread that runs through every step*

*"Same software family — must be simple."* That assumption did not survive contact with how the business actually worked.¹

## Where you are in Flow7

You have finished the seven steps. The data has moved, the counts reconcile, and people are working in the new system. So why is there a chapter *after* Go Live about knowing the business?

Because you could not have written this chapter at the start. Knowing a business — really knowing how it works and the language it uses — is not something you learn up front and then apply. It surfaces as the project moves: a little at Step 1, more at Step 2, and it keeps arriving right through to Go Live. This chapter gathers that thread into one place, gives you the tool to capture it (the Terminology Translator), and shows you why the understanding you now hold is one of the most valuable things the migration produced.

## In this chapter you will…

- See how business knowledge reveals itself step by step
- Learn to translate between what the business *says*, what the system *calls it*, and what it *actually is*
- Build a living translator you can hand to the next person

## Why this matters

Most migration advice tells you to understand the business before you start. It is good advice, and it is also impossible to fully act on. No one can sit down on day one and learn how a business really works — because most of how a business works is not written down. It lives in habits, in workarounds, in one person's head, and in words that mean one thing on the shop floor and another thing in the accounts office.

What you *can* do is stay alert to it. Every step of Flow7 is, quietly, a lesson about the business:

- **Step 1** teaches you where knowledge and data actually live — including the spreadsheet on someone's desktop and the process nobody documented.
- **Step 2** teaches you what the business has tolerated — the duplicates, the blanks, the "we just know that record is wrong."
- **Step 3** forces the business to decide what the *truth* actually is, often for the first time.
- **Step 4** exposes the gap between how they work now and what the new system assumes.
- **Step 5** is where language collides: the source calls it one thing, the target another, and someone has to say what it really is.
- **Steps 6 and 7** confirm whether you understood the business well enough for its people to keep working.

Knowing the business is not a step you complete. It is a lens you carry. This chapter is about grinding that lens.

## The two things you are really learning

Underneath every migration, you are learning a business in two ways at once.

**1. How they work — the process and the unwritten knowledge.** The order in which things happen, who does what, the exception everyone handles the same way without ever being told to, the "we always do it like this because of that one customer in 2019." This is the knowledge that does not export. It is also the knowledge that, if you fail to capture it, walks out of the door when someone leaves.

**2. What they call things — the terminology.** Every business speaks three dialects at once without noticing: the everyday words its people use, the labels its systems show, and the underlying process meaning that ties them together. When those three fall out of alignment, mapping breaks — and the failure is silent until it is expensive.

The rest of this chapter gives you a practical tool for the second, because terminology is where "knowing the business" becomes something you can actually write down.

## How the business reveals itself — a walk back through Flow7

This is the map to keep. Each earlier chapter should point forward to here; this is where the thread is tied together. Read it as *"what the project was teaching me about the business, whether I noticed at the time or not."*

| Step | What the business reveals about itself | The knowledge you should capture |
|:-|:-|:-|
| **1 — Sources** | Where data *and knowledge* really live; who the true experts are | Shadow systems; the undocumented process; the single points of failure |
| **2 — Quality** | What the business has quietly tolerated | Which records the team already distrusts, and why |
| **3 — Master** | What the business considers *true* when forced to choose | The rules that decide the authoritative version |
| **4 — Target** | The gap between how they work and how the new system expects them to | Processes the new system does not support as-is |
| **5 — Mapping** | The language of the business — and where it collides with the system | The terminology translator (see Appendix E) |
| **6 — Testing** | Whether your understanding matches theirs | The processes users actually run day to day |
| **7 — Go Live** | Whether the business can keep working on what you built | The knowledge now safely out of one person's head |

**Editorial note (to action across the book):** add a one-line signpost at the end of each step-chapter — e.g. *"Keep a note of what this step taught you about the business; you will consolidate it in Chapter 11."* This is what makes the chapter *referenced throughout* rather than tacked on the end.

## The Terminology Translator

Almost every hard problem in a migration is a **mapping** problem, and mapping breaks down when the same thing has three different names.

The person on the shop floor calls it a *"job"*. The old system's screen labels it a *Works Order*. The new ERP stores it as a *Manufacturing Order*. The plan calls it *"production demand."* All four are the same object — but if the person mapping fields does not know that, you get duplicated records, broken links, or data quietly dropped on the floor.

The Translator is a **three-language dictionary**. For each business area it lines up:

| Column | What it holds |
|:-|:-|
| **What the business says** | The everyday, departmental or shop-floor term the team uses out loud. |
| **What the system calls it** | The label you meet on a screen, in an export header, or in an ERP/CRM/accounting field. |
| **What it actually is** | The plain-English process or data meaning — the thing all the names point at. |

**The one rule to remember — same object, three names.** Before you create a new target field for something that "isn't in the new system", prove it is genuinely new — not the same object your source called by a different name. Most "extra" fields are duplicates in disguise.

The clearest example comes straight from the Flow7 Data Mapping workbook. One source customer file translated into the target like this:

| Source field (what the business exported) | Target field (what the new system wanted) | What it actually is |
|:-|:-|:-|
| FULLNAME ("Kimberly Smith") | *split into* First Name + Last Name | One field in the source, two in the target |
| POSTCODE | Mailing Postal Code | Same object, different label |
| TEL | Phone | Same object, different label |
| OPTEDIN ("Yes") | Email Opt Out ("False") | Same fact, **inverted logic** |

*Source: Flow7 Data Mapping workbook (DATA-MAPPING sheet), SP Data Consultancy Ltd.²*

Look at the last row. OPTEDIN = Yes and Email Opt Out = False mean the identical thing — but a careless mapping flips every marketing consent in the database. That single row is why terminology is worth a chapter.

The full domain-by-domain translator — Sales & Order Management, Purchasing, Manufacturing, Inventory & Logistics, Finance & Accounting, eCommerce, and Marketing & CRM — together with the **false-friends quick list** (Order, Account, CoA, Invoice, and the rest), is set out in full in **Appendix E: The Terminology Translator**. Keep it open beside you from Step 5 onwards.

## From the Field — Sage 50 to Sage X3

*Drawn from a real migration documented by Stuart Parkins: a successful manufacturer, recently bought out, moving from Sage 50 to Sage X3.³*

This project is the whole argument of the chapter in miniature. The assumption at the start — *"same software family, must be simple"* — was not a technology mistake. It was a *business-knowledge* mistake. The difficulty was never the software; it was everything the business knew but had never written down.

The knowledge was trapped in one person's head. The process that ran the operation had grown organically and was undocumented — it worked, but only because the people running it carried it in memory. Product codes had drifted into free text; stock did not match the warehouse. None of that appears in a data export. All of it is *business* knowledge, and it only came to light because the migration went looking.¹

By the end, that knowledge existed *outside* one person for the first time: in the master set, in the mapping rules, in the documented loading order, in the process notes. That is the quiet second product of every migration. You set out to move data; you finish having captured how the business actually works. Do not let that understanding evaporate the week after go-live — it is worth more than the software.

## Your Turn — build a living translator

You cannot write this on day one. You build it as the project teaches you. Start it at Step 5 and keep adding rows until go-live.

1. Take the **Business Process List** from Step 1 (checklist item 1C).
2. For each process, write the word the **team** uses, the label the **source system** shows, and the field the **target system** expects.
3. Flag every row where the three do not obviously match — those are your highest-risk mappings.
4. Add the unwritten knowledge as you meet it: the exception, the workaround, the "we only do that for one customer."

| Our word for it | Source system label | Target system field | Same object? (Y/N) | The unwritten bit |
|:-:|:-:|:-:|:-:|:-:|
|   |   |   |   |   |
|   |   |   |   |   |

Hand the finished sheet to whoever runs the system next. It is the cheapest insurance the business will ever buy against knowledge walking out of the door.

## What you have achieved

You have turned a migration into a record of how the business actually works — its processes, its exceptions, and the shared language that keeps its systems talking to each other. The data moved; the knowledge stayed. That is the difference between a business that survives a system change and one that quietly loses a piece of itself in the move.

## References

1. Stuart Parkins, *"A Case Study from a Sage 50 to Sage X3 Migration,"* stuartparkins.com, 28 October 2025 (originally published on the SPDATA website) — knowledge trapped in one person's head; undocumented organic process; product codes as free text; stock not matching the warehouse. https://www.stuartparkins.com/resources/post/a-case-study-from-a-sage-50-to-sage-x3-migration
2. Flow7 Data Mapping workbook (DATA-MAPPING and DATA SOURCES sheets), SP Data Consultancy Ltd — source of the FULLNAME / OPTEDIN translation examples.
3. Parkins, *Sage 50 to Sage X3 case study* — four BOM types; no recorded warehouse locations; "no BOMs at all"; data "created from scratch"; loading order. stuartparkins.com, 28 October 2025.

*Terminology in the Translator describes usage as it is commonly found across ERP, CRM, accounting and eCommerce systems; it is a general guide, not a specification for any one product. Rows drawn from the author's own project artefacts or the case study are cited above; all other examples are labelled "illustrative scenario." UK English throughout.*
