**CHAPTER 7**

# Go Live

### *Step 7 of the Flow7 Data Migration System — Migration Go Live*

**A go-live that follows a written plan, runs in a rehearsed order and is checked by named people is a calm event, not a dramatic one. That is what this chapter sets up.**

## Where You Are in Flow7

{{progress: 7}}

Your migration is tested and signed off. Step 7 is where you **load it into the live system, prove it arrived intact, and see the business safely through its first weeks on the new system.**

## In this chapter you will…

- Run the final checks on your data, your systems and your team before anything moves
- Open the migration window: lock the old system, load in your rehearsed order, and log every error
- Make a recorded go/no-go decision, with a rollback plan to hand
- Hand the system to users, with one clear way to raise issues
- Run a stabilisation period with a defined end, then close the project formally

## What you'll need

- Your go-live readiness sign-off from Step 6 — no sign-off, no go-live
- Your loading order from Step 4, rehearsed in Step 6
- The signed-off record counts from your master set (Step 3), to reconcile against
- Your UAT Testing List from Step 6, which carries on as the go-live issue log
- A rollback plan, written down and agreed before the window opens

## Why This Matters

Most go-live problems are not caused by the load itself. They come from having no plan for the hours and weeks *after* it — no agreed checks, nobody responsible for the numbers, no clear way for users to report what looks wrong, and no rollback plan if something critical goes wrong.

Without that structure, the migration simply ends and people hope. Nobody checks the counts. Users raise problems informally with whoever is nearby, so nobody can tell an odd one-off from the first sign of something systemic. Errors drift into live use and become harder to unpick every day.

Step 7 gives go-live a spine: checks before the switch, a set order during it, immediate validation after it, and a stabilisation period that bridges the gap to business as usual. If you have done Steps 1 to 6 properly, it is the shortest step of all — and the calmest.

## What You Are Actually Doing

Step 7 runs in five stages, in this order. They match sections 7A to 7E of the Flow7 Project Plan Checklist.

**7A — Final preparations (before the window opens).** The last checks before anything moves, in three areas:
- *Data:* the final export is taken, a full backup of the source data is stored in two secure places, and all the data work — quality, mapping, counts — is signed off.
- *Systems:* the new system is set up and ready, it has a clean backup in case you need to roll back, everyone who needs access during the window has tested it, and any connected systems are ready for the change.
- *People:* everyone with a role in the window knows what it is and how to reach the others. Everyone else knows when the switch happens and what to expect.

**7B — The migration window.** The window opens when the old system is locked — no new entries, no processing — and it does not close until the checks are done. Log the start time. Confirm the old system has stopped. Load the data in your rehearsed order, keeping an error log throughout. Errors are normal; what matters is that every one is caught and written down.

When the loading is complete, and before anyone else uses the system, run the quick checks:
- **Record counts** match the signed-off figures — the same number of customers, products, orders and so on. Any difference needs an explanation before you go further.
- **Spot-checks** on a sample of records show the right values in the key fields, not just that the records exist.
- **Critical data** — the records the business cannot run without — has arrived intact.
- **Performance** is normal with the full data loaded.

**7C — The go/no-go decision.** Before users are let in, the project lead, the business owner and whoever is responsible for the technical side confirm three things: the data is intact, the system is stable, and support is ready. Then someone with the authority to do so records a formal go or no-go. The rollback plan stays to hand until that decision is made.

**7D — Validation with users (the same day).** Now the business takes over the checking. Confirm every user can log in and sees the right data and functions for their role. Make the quick-reference guides from your UAT scripts available. Tell everyone how and where to raise an issue *before* their first session. Then have key users reconcile totals between the old and new systems, confirm their own data looks right, and run their standard reports.

**7E — Stabilisation and closure.** Stabilisation starts on go-live day and runs for at least four weeks — longer if the system takes time to settle. Throughout it, log and answer every user question, keep an eye on performance, and run random spot-checks to confirm the data stays right as people use it. When the system has settled, close the project: agree what happens to the old system (its status, when access is removed, what is archived), and write a final migration report recording what moved, what worked, what didn't, and whether you met the success measures in your Outline Migration Statement.

> 🔑 **Key idea.** Go-live is not the finish line. It is the start of the validation period. The project ends at closure — when the stabilisation period has run its course, the old system has a documented status, and the final report is written.

## Key things to get right

Four disciplines turn go-live from an anxious event into a managed one.

**1. Lock the old system before you load.** From the moment loading begins, nothing new goes into the old system. Your counts, your error log and your timings all depend on a source that has stopped moving.

**2. Reconcile counts after every load, not just at the end.** In a system with dependencies, each load feeds the next. A difference caught after the customer load is a five-minute fix; the same difference found after orders have been loaded against those customers is a long night.

**3. Agree the rollback plan before the window opens.** Write down what would make you stop, who makes that call, and the steps to reverse. A rollback plan is a professional contingency, not a sign of doubt — and it means a hard decision under pressure is made against a plan rather than improvised.

**4. Give stabilisation a named end.** Not "we'll see how it goes": a start date, an end date, an issue log that is open and owned, and spot-checks throughout. When the end date arrives, anything still open becomes a support item with a named owner. Nothing is left floating.

> 👁 **Watch out.** At go-live you *run* the loading order — you do not improvise it. The order was worked out in Step 4 and rehearsed in Step 6. If something forces a change on the night, that is a go/no-go question, not a quick tweak.

## From the Field

### *Sage 50 → Sage X3: the final push*

After months of assessment, master-set work, mapping and repeated testing in the development and UAT sandboxes, the Sage 50 to Sage X3 migration reached go-live. The company chose a full cutover over a long weekend: stop the old system, then start processing in the new one, which was already live for the parent company.

As soon as the Sage 50 team downed tools, the data loading plan was to hand and loading began. Because X3 has strict dependencies, the order had been planned in Step 4 and rehearsed in testing. It ran like this:

1. Suppliers and contacts
2. Customers, addresses and contacts
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

Each load fed the next. Some values X3 created along the way — such as the new supplier IDs — had to be written back into the master set before the next load could run. Because we had rehearsed that round trip in testing, on the night it was routine.

Two lessons from that weekend apply to any go-live:

**Record counts were the first and most repeated check.** We agreed the counts with the business team before the weekend and checked them after every load, not just at the end. Any difference was investigated before the next load began.

**Different people were waiting for different data.** During a phased load, people were ready to check their area the moment it landed — the purchasing team after supplier products, finance after the financial data. They needed to know the order, the rough timings, and who to report problems to. The loading plan was not just a technical document; it was the weekend's communication plan.

## Your Checklist

The essentials for Step 7. The full task list — about forty tasks across 7A to 7E, with status, owner and date columns — is in the Flow7 Data Migration Project Plan Checklist. Work through it in order: don't open the window until every 7A task is done.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 7A | Take the final export, back up the source data in two places, and back up the new system so you can roll back | ☐ |
| 7A | Confirm the migration team, their roles and contacts, and tell users when the switch happens | ☐ |
| 7B | Lock the old system, log the start time, load in your rehearsed order, and keep an error log | ☐ |
| 7B | Reconcile record counts after each load, and spot-check key records on screen | ☐ |
| 7C | Record a formal go/no-go decision, with the rollback plan to hand until it is made | ☐ |
| 7D | Confirm user logins and permissions, share the quick-reference guides, and tell everyone how to raise issues | ☐ |
| 7E | Run stabilisation to its agreed end, then agree the old system's status and write the final migration report | ☐ |

> 📋 **Worked example — illustrative scenario**
>
> *The kitchenware wholesaler from Chapters 1 and 4, going live on its new cloud ERP over a weekend. This is its loading plan, with what happened on the night. The business is invented; the kinds of findings are typical.*

| Order | What is loaded | Depends on | Expected count | Loaded | Who checks it |
|:-:|:-|:-|:-:|:-:|:-|
| 1 | Suppliers | — | 86 | 86 | Purchasing |
| 2 | Customers and addresses | — | 1,240 | **1,238** | Sales Manager |
| 3 | Products, with bin locations | Suppliers | 3,150 | 3,150 | Warehouse Supervisor |
| 4 | Customer prices | Customers, products | 9,400 | 9,400 | Sales Manager |
| 5 | Opening stock | Products | 3,150 | 3,150 | Warehouse Supervisor |
| 6 | Open sales orders | Customers, products | 212 | 212 | Office Manager |
| 7 | Opening balances | Customers, suppliers | 1,326 | 1,326 | Finance Manager |

*One difference on the night: two customers short after load 2. The error log showed both were rejected for a missing postcode — new accounts set up in the final week, after the last test load. The Sales Manager supplied the postcodes, the two records were loaded, and the count matched before load 3 began. Because the counts were checked after each load, the fix took ten minutes. Found after load 4, it would have meant rejected prices too.*

## Your Turn

### Exercise 7.1 — Write Your Loading Plan

Write out the order in which your data will be loaded. Even a simple migration with two kinds of data needs this written down. For each load, note:

1. **What** is being loaded.
2. **What it depends on** — what must already be in the system.
3. **The expected record count**, from your signed-off master set.
4. **Who checks it** the moment it lands.

If you cannot fill in the "depends on" column, go back to your Step 4 notes — that is where the loading order was worked out.

**Where to record it:** your Step 7 *Data Migration Go-Live Plan*.

### Exercise 7.2 — Define Your Rollback Trigger

Agree the answers to three questions before the window opens, so the decision is made calmly and not under pressure:

1. **What would make us stop and roll back?** Be specific — for example, a critical load that fails twice, or counts that cannot be reconciled by a set time.
2. **Who makes that call?**
3. **Where are the rollback steps written down?**

**Where to record it:** the top of the same Go-Live Plan, so everyone in the migration window can see it.

> 📄 **Your template.** Flow7 Step 7 — *Data Migration Go-Live Plan* (your loading plan and rollback trigger), *Migration Go-Live Monitoring* (the stabilisation weeks) and the one-page *Migration Go-Live Dashboard*. The *Flow7 Data Migration Project Plan Checklist* covers all five stages of Step 7 (7A to 7E) in full, with status, owner and date columns. For the issue log, keep using your Step 6 *UAT Testing List* — same columns, same severity scale — so that go-live issues sit alongside the ones you found in testing. Download at **stuartparkins.com**.

## What you have achieved in this chapter

Your migration is live. The counts match the signed-off figures. Users have access and know how to raise an issue. The issue log is open and owned, and the stabilisation period has a defined end. When it ends, the final migration report closes the project — and the new system carries your cleaned, mapped, tested data into the work it was bought to do.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Every load has run, and the record counts match the signed-off figures | ☐ |
| A formal go/no-go decision was recorded before users were let in | ☐ |
| Users have confirmed they can log in and that their data looks right | ☐ |
| The stabilisation period has run to its agreed end, with every open issue owned | ☐ |
| The old system has a documented status and a close-down plan | ☐ |
| The final migration report is written and signed off | ☐ |

**When you can tick every box, the migration is done.** Anything still open becomes a post-migration support item with a named owner — tracked to resolution, not left floating.

**Next:** Part Three — *Know the Business*, where you pull together what the whole project taught you about how the business works and the language it uses.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: the knowledge that now lives in documents and data rather than in one person's head. You will pull all of these notes together in the next chapter.
