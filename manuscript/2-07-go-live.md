**CHAPTER 7**

# Go Live

## Step 7 — Deploy With Confidence

**A go-live that follows a written plan, runs in a planned sequence, and is validated by named people is a calm event — not a dramatic one. That is what this chapter sets up.**

## Where You Are in Flow7

You have done all seven steps. You found your data sources in **Chapter 1**. You assessed their condition honestly in **Chapter 2**. You defined your single master set in **Chapter 3**, understood the structure of your new system in **Chapter 4**, mapped everything across in **Chapter 5**, and put it all through rigorous testing in **Chapter 6**.

The gate into Step 7 is the confirmed go-live readiness sign-off you earned in Step 6. If you have that, you are ready. If you do not have it — if there are outstanding issues from testing that have not been resolved — you are not. Go back. The cost of fixing a problem in testing is a fraction of the cost of finding it in the live system.

What you are doing now is the final move: taking your cleaned, mapped, tested, signed-off data and loading it into the production system. Then — immediately and methodically — verifying that what went in matches what should have gone in.

In the cooking analogy that runs through Flow7: you have checked the recipe, sourced the ingredients, prepared your mise en place, and done a trial run. **This is the service.**

## In this chapter you will…

- Complete the final pre-migration checks across data, system and team readiness
- Execute the migration window in sequence, with logged times and a maintained error log
- Run immediate quality checks: record counts, spot-checks, critical process validation
- Hand the system over to users with clear support and issue-raising channels
- Manage the stabilisation period through to formal closure

## What you'll need from earlier chapters

- The signed-off go-live readiness from Chapter 6
- Your loading order from Chapter 4, refined through Chapter 5 mapping and Chapter 6 testing
- A rollback plan documented and accessible to everyone in the migration window
- Final record counts from Chapter 6 testing — these are what you reconcile against

## Why This Matters

A structured go-live turns the final move into a calm, validated event rather than a hopeful one. Everything you have built — the sources documented, the master set defined, the target understood, the mapping written, the testing completed and signed off — comes together here, in sequence, against a written plan. The migration window has a defined start, a defined end, and a defined order of operations. Validation happens immediately. Users get the system back with a clear channel for raising issues. Stabilisation has a defined close.

The discipline of Step 7 is what lets you walk away from go-live with a measured result rather than a feeling of relief. Every later question about the migration — what was loaded, when, by whom, against what counts — has a documented answer. And the same discipline is what protects the new system from inheriting unresolved issues into its first week of live use.

## What You Are Actually Doing

Step 7 has four distinct phases that run in sequence. Each one matters; none can be skipped.

**Phase 1 — Final Preparations (before the window opens)**

This is the last set of checks you run before anything moves. It covers three areas.

*Data readiness:* your final export from the source system has been taken, your backup of source data is stored in at least two secure locations, and all data work — quality, mapping, counts — has received a formal sign-off from the people responsible.

*System readiness:* the target system is installed, configured, and confirmed ready to receive data; a clean backup of the target system and its configuration exists in case a rollback is needed; all required access — for everyone who will need it during the migration — has been tested and confirmed; and if connected systems or integrations are involved, those connection points have been checked and confirmed ready.

*Team readiness:* everyone who has a role during the migration window knows who they are, what they are responsible for, and how to reach key contacts if something goes wrong. Users who are not directly involved have been told what to expect and when.

**Phase 2 — The Migration Window**

This is the execution phase. The window opens when the source system is locked — no new data entry, no processing — and it does not close until validation is complete.

The sequence matters. Log the start time. Lock the source system and confirm it is stopped. Begin the data transfer. Maintain an error log throughout. Do not assume a clean run; errors during import are common and expected — what matters is that they are caught and recorded.

Once the load is complete, run your immediate quality checks before anyone else touches the system:

- Verify record counts against the signed-off figures from your master data set. The same number of customers, products, orders — or whatever your critical entities are — should be present in the target system as were in your final export. Any discrepancy needs an explanation before you proceed.
- Spot-check a representative sample of individual records — not just that they arrived, but that the values in key fields are correct.
- Check that critical process data has transferred properly (the records the business could not function without).
- Confirm that system performance is behaving normally under the migrated data.

**Phase 3 — Post-Migration Validation (same day)**

Once the data checks pass, the focus shifts to the people who will use the system.

Confirm that all users can log in and that their permission levels are correct — that each person sees the data and functions appropriate to their role. Make quick-reference guides or UAT documentation available. Ensure everyone knows how and where to raise an issue if they find one; this channel needs to exist and be communicated clearly before users start their first session.

Then run data verification again, this time with the business team rather than the technical team: compare totals and counts between old and new systems, have key users confirm that their data looks correct, and check that standard reports are producing expected results.

**Phase 4 — Stabilisation and Closure**

The stabilisation period begins on the day of go live and runs for at least the first four weeks, though how long it continues depends on how quickly the system settles. During this time: log and respond to all user questions and issues; keep system monitoring active for performance problems or unexpected errors; and run random data integrity spot-checks to verify that data continues to look correct as it is used.

Once the system has stabilised, migration closure follows. This has two components: a plan for the old system — what is its status, when will access be removed, what data (if any) needs to be archived — and a final migration report that documents the project, summarises the data, records what worked and what did not, and confirms the agreed success metrics.

## Key things to get right

Five disciplines turn the go-live from an anxious event into a managed one.

**1. Lock the source system before the window opens.** No new data entry, no processing in the source system from the moment loading begins. The error log, the counts, the timing all depend on a source that has stopped moving.

**2. Compare record counts at every stage.** Counts at the start (from your Chapter 6 sign-off), counts after each load, counts after the final cutover. A discrepancy at any stage signals something to investigate *before* the next load begins, not after the whole sequence has run.

**3. Watch the front end, not just the database.** Records that look right in a table can look wrong on the user's screen — formatting, layout, the field that did not quite map. Reserve time during validation to look at the system the way a user will.

**4. Have the rollback plan visible and named.** It is a contingency, not a sign of doubt — and it needs to be a calm decision, not improvised under pressure. Document it, name the decision-maker, and keep it accessible to everyone in the migration window. The discipline of having it is what makes it almost never needed.

**5. Treat stabilisation as a structured phase with a defined end.** Not "we'll see how it goes" — a named start, a named end, monitoring and spot-checks running throughout, an issue log that is open and owned. When the end date arrives, outstanding items become post-migration support items with named owners — not floating problems.

There is one technical discipline worth naming alongside these: in systems with dependencies (ERPs especially), respect the loading order. Records that depend on other records being present must be loaded after their dependencies. The order was worked out in Chapter 4, refined in Chapter 5 and proven in Chapter 6 — at go-live, you run the order, you do not improvise it.

## From the Field

### The Sage 50 to Sage X3 Migration: The Final Push

After months of data assessment, master set definition, mapping, and iterative testing in development and UAT sandboxes, the Sage 50 → Sage X3 migration reached go live. The company chose a full cutover over a long weekend — stop the old system, start processing in the new one, which was already live for the parent company.

The go live was not a single action. It was a structured sequence, and the data loading order was central to it. Because Sage X3 has strict dependency requirements — many records depend on other records already being present — there was a defined loading sequence that had been planned and tested in advance. In this migration, it ran as follows:

1. Suppliers and contacts
2. Customers, addresses, and contacts
3. Products — main records
4. Supplier products
5. Customer loan products
6. Locations
7. Product sites
8. Product costing
9. Bills of materials (four different types)
10. Work centres and operations
11. Purchase orders
12. Sales orders
13. Stock receipts
14. Financial data

Each load fed into the next. Some exported values from Sage X3 — such as the new Supplier IDs assigned by the target system — had to be written back into the master data set before the next dependent load could proceed. This is the kind of iteration that only becomes clear during testing; it is why the testing phase in Chapter 6 matters so much.

As soon as the Sage 50 team downed tools, the data loading plan was to hand and execution began. Key lessons from that go live are directly applicable to any migration:

**Record counts are your first and most repeated check.** Aligning record counts with the business team was a discipline throughout the project — not just at go live — and was repeated at multiple points during loading. Discrepancies at any stage signal that something needs investigation before the next load begins.

**Different team members are waiting on different data.** During a phased load, there are people ready to run checks and validations the moment their data category appears. They need to know the sequence, the expected timing, and who to report issues to. The go-live data plan is not just a technical document — it is a communication tool.

**Error checking in the target system has limits.** In Sage X3, the display interface was limited to 1,000 records at a time. For large data categories, this meant chunking data for error checking rather than reviewing it as a single set. This kind of system-specific constraint needs to be identified during testing — not discovered for the first time at go live.

**The pro tip that applies everywhere:** *get access to the front-end system. You need to see what users see.* Before go live, confirm that the data looks right from the user's perspective — not just from the database or import logs. What looks correct in a data file can look completely wrong once it is rendered in the interface.

## Your Checklist

The items below are the **Migration Go Live** tasks, taken directly from the *Flow7 Data Migration Project Plan Checklist* (SP Data Consultancy Ltd, V1.0). They are organised by the four phases described above.

Work through each section in sequence. Do not proceed to Phase 2 until every Phase 1 item is confirmed.

### 7A — Pre-Migration Final Preparations

**7A1 — Data Readiness**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7A1.1 | Final data export completed — all source data has been extracted and is ready for transfer | ☐ |   |
| 7A1.2 | Data backup created — full backup of source system data stored in secure location(s); two locations recommended | ☐ |   |
| 7A1.3 | Data sign-off confirmed — all data work completed: quality, mapping, counts | ☐ |   |

**7A2 — System Readiness**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7A2.1 | New system confirmed installed, configured, and ready to receive data | ☐ |   |
| 7A2.2 | Target system backed up — clean copy in place in case rollback is required | ☐ |   |
| 7A2.3 | System and software access tested for all those who need it during migration | ☐ |   |
| 7A2.4 | If integrations apply — integration points checked; connected systems ready for the change | ☐ |   |

**7A3 — Team Preparation**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7A3.1 | Migration team assembled — all key people are available and know their roles | ☐ |   |
| 7A3.2 | Communication plan active — users have been notified about timing and what to expect | ☐ |   |
| 7A3.3 | Emergency contacts confirmed — key personnel contact information is current and accessible | ☐ |   |

### 7B — During the Migration Window

**7B1 — The Migration Process**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7B1.1 | Progress monitoring active (manual or automatic) — track migration status and watch for errors | ☐ |   |
| 7B1.2 | Migration start time logged — document exactly when the process begins | ☐ |   |
| 7B1.3 | Source system locked and STOP PROCESSING confirmed — no new data entry during migration | ☐ |   |
| 7B1.4 | Data transfer initiated — data moving from old system to new | ☐ |   |
| 7B1.5 | Error log maintained — all issues or problems occurring during the window are documented | ☐ |   |

**7B2 — Quality Checks**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7B2.1 | Record counts verified against signed-off data — same number of customers, orders, products, etc. confirmed | ☐ |   |
| 7B2.2 | Sample data spot-checked — key records reviewed to confirm data looks correct | ☐ |   |
| 7B2.3 | Critical process data validated — most important information confirmed transferred properly | ☐ |   |
| 7B2.4 | System performance checked — new system responding normally with migrated data | ☐ |   |

### 7C — Go-Live Decision Point

**7C1 — Final Approval Criteria**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7C1.1 | Support readiness confirmed — help resources available for user assistance | ☐ |   |
| 7C1.2 | Data integrity confirmed — all critical data successfully transferred and verified | ☐ |   |
| 7C1.3 | System stability demonstrated — new system performing reliably under normal load | ☐ |   |
| 7C1.4 | User acceptance achieved — key stakeholders approve the migrated data and system | ☐ |   |
| 7C1.5 | Rollback capability maintained — ability to reverse migration if serious issues arise | ☐ |   |
| 7C1.6 | Rollback plan to hand — everyone knows the steps to reverse the migration if needed | ☐ |   |

**7C2 — Go-Live Authorisation**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7C2.1 | Project manager approval — migration lead confirms readiness | ☐ |   |
| 7C2.2 | Business owner sign-off — department heads approve proceeding | ☐ |   |
| 7C2.3 | Technical lead confirmation — IT confirms system stability and performance | ☐ |   |
| 7C2.4 | Final go/no-go decision made — formal decision to proceed with go live recorded | ☐ |   |

### 7D — Post-Migration Validation

**7D1 — User Readiness**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7D1.1 | User communication sent — users notified that migration is complete and system is ready | ☐ |   |
| 7D1.2 | User login verification — confirm all users can access the system normally | ☐ |   |
| 7D1.3 | Permission levels checked — ensure users see appropriate data and functions for their roles | ☐ |   |
| 7D1.4 | Quick-reference guides or UAT documentation made available to users | ☐ |   |
| 7D1.5 | Follow-up training sessions scheduled if needed | ☐ |   |
| 7D1.6 | All users know how and where to raise issues — reporting channel confirmed and communicated | ☐ |   |

**7D2 — Data Verification**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7D2.1 | Full data reconciliation complete — totals and counts compared between old and new systems | ☐ |   |
| 7D2.2 | Business-critical data verified — most important records confirmed complete and accurate | ☐ |   |
| 7D2.3 | User acceptance testing revisited — key users confirm their data looks correct and processes flow | ☐ |   |
| 7D2.4 | Reports and analytics verified — standard reports confirmed to show expected results | ☐ |   |

**7D3 — System Functionality**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7D3.1 | Core features tested — main system functions verified with migrated data | ☐ |   |
| 7D3.2 | Integration testing completed — connected systems verified as working with new data | ☐ |   |

### 7E — Post Go-Live Monitoring and Closure

**7E1 — First Four Weeks (duration may vary depending on stability)**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7E1.1 | User support tracking active — all user questions and problems logged and responded to | ☐ |   |
| 7E1.2 | System monitoring active — watching for performance issues or errors | ☐ |   |
| 7E1.3 | Data integrity spot-checks running — random verification that data remains accurate | ☐ |   |

**7E2 — Migration Closure**

| Ref | Task | ✓ | Notes |
|:-:|:-|:-:|:-:|
| 7E2.1 | Source system close-down plan created — plan and announcement of old system status in place | ☐ |   |
| 7E2.2 | Final migration report completed — migration documented, data summary, processes, issues, and success metrics recorded | ☐ |   |

> ▶ **Worked example — to be added**
>
> *A populated example of a go-live data loading plan — showing load sequence, dependencies, expected record counts and named responsibilities — will be added here from a real client engagement. (The Sage 50 → Sage X3 loading order in the From the Field section above is the closest existing example: suppliers and contacts → customers and addresses → products → supplier and loan products → locations → product sites → product costing → Bills of Materials → work centres → purchase orders → sales orders → stock receipts → financial data.)*

## Your Turn

### Exercise 7.1 — Write Your Loading Plan

Before your migration window opens, write out the sequence in which data will be loaded into the target system. Even a simple migration with one or two data types needs this documented. For systems with dependencies — where one record must exist before another can be created — the order is not optional.

Use the table below. Add rows as needed.

| Load order | Data type / entity | Depends on | Expected record count | Who is responsible |
|:-:|:-:|:-:|:-:|:-:|
| 1 |   |   |   |   |
| 2 |   |   |   |   |
| 3 |   |   |   |   |
| 4 |   |   |   |   |
| 5 |   |   |   |   |

### Exercise 7.2 — Define Your Rollback Trigger

Before the migration window opens, agree and document the answer to this question: *at what point would we stop and roll back?*

Write it here so that the decision is made calmly in advance, not under pressure during the window.

**We would trigger a rollback if:**

{{write-in}}

**The person who makes that call is:**

{{write-in}}

**The rollback steps are (or are documented at):**

{{write-in}}

### Exercise 7.3 — Set Up Your Issue Log

Create a simple issue log before users access the new system. This does not need to be complex — a shared spreadsheet works. The minimum columns are:

| Issue # | Raised by | Date | Description | Severity (H/M/L) | Status | Owner | Resolved date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   |   |   |   |   |   |   |   |

**➔ Your full go-live execution is supported by the** ***Flow7 Data Migration Project Plan Checklist*** **— the Excel workbook that accompanies this handbook. Step 7 covers all five phases in detail, with status, date, and owner columns for every task. Download it at: stuartparkins.com**

## What you have achieved in this chapter

Your migration is live. Counts match. Users have access and a clear channel for raising issues. The issue log is open and owned. The stabilisation period has a defined end. When that end arrives, the final migration report closes the project formally — and the new system carries your cleaned, mapped, tested, signed-off data into the work it was bought to do.

## You're Ready to Move On When…

Step 7 is complete — and your migration project is formally closed — when all of the following are true:

| Gate | ✓ |
|:-|:-:|
| The migration window completed and all load steps executed | ☐ |
| Record counts in the target system match the signed-off figures from the master data set | ☐ |
| Spot-checks on critical records passed | ☐ |
| All users have confirmed access and their data looks correct | ☐ |
| The issue log is open, monitored, and has named owners for every open item | ☐ |
| The stabilisation period has run to its agreed end point | ☐ |
| The source system has a documented status and a named close-down plan | ☐ |
| The final migration report has been written and signed off | ☐ |
| Outstanding issues are either resolved or formally accepted and documented | ☐ |

**When you can tick all of these, the migration is done.**

If there are issues still open when the stabilisation period ends, they do not disappear — they become post-migration support items with named owners. Document them, assign them, and track them to resolution. Do not leave them floating.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: the knowledge that now lives in documents and data rather than in one person's head. You will pull all of these notes together in the next chapter, *Know the Business*.

## Looking Further

Step 7 is the final step of a data migration, but it is not the limit of what Flow7 can do.

The same seven steps — sources, quality, master, target, mapping, testing, go live — apply to every type of data project: not just migrations, but reporting and analytics builds, workflow automation projects, and AI implementations. The questions at each step change to fit the work; the sequence and the discipline do not.

If you are interested in how Flow7 extends beyond migration, the *7 Steps for Any Data Project* reference sheet, available at stuartparkins.com, outlines how the framework applies across all four project types.
