**CHAPTER 6**

# Test Before You Trust

### *Step 6 of the Flow7 Data Migration System — Testing in the Target System(s)*

**Structured testing in a safe environment is what turns a migration plan into a migration result. Every issue you find here is one you have time to fix calmly — before go-live depends on it.**

## Where You Are in Flow7

{{progress: 6}}

Your data is mapped, cleaned and sample-confirmed. Step 6 is where you **prove the migration works — in a safe place, with real people, before anyone has to depend on it.**

## In this chapter you will…

- Build a UAT test script for every business process that must work in the new system
- Run those scripts in a test environment, not in the live system
- Check record counts, spot-check key records, and test the work users actually do
- Keep one central UAT Testing List — status, due date, resolution and severity for every issue
- Sign off go-live readiness from a measured position, not a hopeful one

## What you'll need

- Your User Target Processing List from Step 4 (every process to be tested)
- Your Business Process List from Step 1 (to check nothing important is missing)
- Your sample test data set from Step 5
- A non-live environment to test in — a development, test or "sandbox" copy, *not* the live system
- Access to the front end as well as the database

## Why This Matters

Once mapping is finished, it is tempting to feel finished. You are not. Mapping tells you what *should* happen. Testing tells you what *actually* happens when the cleaned data meets the new system, the new screens and the people who use them every day.

Three things only show up in testing:

- **Import errors** the mapping could not predict — a field that accepts the data on paper but rejects it in practice; a link between two records that does not survive the import; a value the target quietly shortens or reformats.
- **Process failures** — the data lands correctly, but a key task no longer works. Users cannot raise a sales order. Stock cannot be received. A report does not return what it used to.
- **User-experience surprises** — everything technically works, but a screen takes a minute to load, or a field everyone relies on is now three clicks deep. These pass every technical test and still fail the business.

The Flow7 Step 6 help notes are blunt about what is at stake: **the number and severity of issues found in testing decide whether the go-live date needs to move.** Testing is not a tick-box at the end — it is the gate that protects Step 7.

## What You Are Actually Doing

Step 6 has two halves, matching the two sheets in the Flow7 Step 6 template.

**A. A UAT test script for every process.** For each business process that must work in the new system, you write a short, structured script that a real user can follow and record results against. Every script uses the same nine fields, so results can be compared and traced:

1. **Test ID** — a unique reference, so the result can be tracked end to end
2. **Test case name** — a short descriptive name (e.g. *"Raise Sales Order"*)
3. **Description** — what is being tested, and why
4. **Test steps** — a clear, numbered list of actions to follow
5. **Test data** — the specific records or values to use, if any
6. **Expected result** — what should happen if the system works as intended
7. **Actual result** — what actually happened (filled in by the tester)
8. **Pass / fail** — the verdict
9. **User comments** — observations, screenshots or notes

The point of this structure is that *anyone* can follow it. A finance user runs the accounts scripts; a warehouse user runs the goods-in scripts. The tester does not need to be technical — the script tells them exactly what to do and what to look for.

**B. One central UAT Testing List.** Scripts produce results; results produce issues. The UAT Testing List is the single place where every issue is recorded, owned, tracked and closed. Each row carries the **Test ID** it came from, the **issue**, its **status** (*Open / In progress / To be tested / Closed*), a **due date**, the **resolution or escalation**, and its **severity** (*None / Minor / Serious / Critical*).

Status tells you whether an issue is moving; severity tells you whether you can live with it. Manage this list diligently — at any moment, it is what tells you whether you are ready to go live.

> 🔑 **Key idea — where the UAT scripts come from.** You do not start from scratch. You listed the processes back in Step 4, in the User Target Processing List. Have it to hand, and check it against your Step 1 Business Process List — in the help notes' words, *"just to cross check nothing has been missed that is important."*
>
> **Step 1C** (what the business actually does) → **Step 4B** (how it will work in the new system) → **Step 6A** (a UAT script for each process).
>
> A process missing from Step 4 will be missing a script — and so it will never be tested. That is the strongest practical reason not to skimp on Chapters 1 and 4.

## Key things to get right

Four disciplines turn testing into evidence rather than wishful thinking.

**1. Test the work, not just the data.** Counts and spot-checks prove that *something* arrived. UAT scripts prove a real user can do their real job — raise a sales order against a migrated customer, receive stock against a migrated product, run month-end on migrated transactions. Every business process needs a matching script.

**2. Write scripts anyone can run.** If a script is too vague for a non-technical user to follow, it is too vague. Go back and tighten it.

**3. Respect the target's display limits.** If the new system only shows a set number of records on screen, split your test loads to fit — otherwise you are testing things you cannot actually see.

**4. Sign off on what users see.** Users need to log in, use the system, and confirm it works for the job they do. Back-end checks alone are testing a story, not a system.

> ↩ **Tracking back.** A failed test often sends you back — to Step 5 to fix a mapping rule, to Step 3 because the master set was missing something, or to Step 4 because the target needs a setting changed. That is the loop working, not a sign something has gone wrong. Expect it, and build time for it.

## From the Field

### *Sage 50 → Sage X3: testing in two sandboxes*

By Step 6 the scale of the work was clear — 7,500+ product records, 1,500+ assembly instructions created from scratch, and warehouse and manufacturing rules that had lived in people's heads.

**Two environments, two jobs.** Testing ran in two sandboxes, both separate from the live X3 system the parent company used: a **development** environment and a **UAT** environment. I wrote my own data loading plan and rehearsed it repeatedly in both. Development was where the load was refined and the rough edges sanded down; UAT was where the users came in.

**Chunking what we could see.** X3's screens only showed 1,000 records at a time, so we split each load into chunks for error-checking — that way, what landed in the system could actually be inspected by eye.

**The loop ran several times.** A failed test fed an update to the master set (Step 3), which fed an updated mapping (Step 5), which fed the next round of tests. Even so, because we rehearsed so often, the total load time for go-live could be estimated quite accurately.

**Proving the new IDs.** Once records load into X3 they get new internal IDs. Part of testing was proving that every new ID could be traced back to the unique ID we had created ourselves in Step 3 — *not* to SKUs or customer numbers, which look unique but often are not. That link became essential at go-live; testing was where it was proven.

## Your Checklist

The essentials for Step 6. The full task list, with status, owner and date columns, is in the Flow7 Data Migration Project Plan Checklist.

| Ref | Task | ✓ |
|:-:|:-|:-:|
| 6A | Check your Step 4 process list against your Step 1 Business Process List, so nothing is missing | ☐ |
| 6A | Write a UAT script (all nine fields) for every process, and run process training for the critical ones | ☐ |
| 6A | Load your sample test data into a non-live environment and check the record counts | ☐ |
| 6A | Spot-check records on screen, and check the links between them (customer to orders, product to stock) | ☐ |
| 6B | Log every issue in the UAT Testing List with status, due date, resolution and severity — and review it daily with the team | ☐ |
| 6B | Close every critical and serious issue, or agree a dated plan for it, before any go-live decision | ☐ |

> 📋 **Worked example — UAT-001 Login Functionality**
>
> *The UAT Test Sheet page from the Step 6 template, drawn from a real test run. It uses the same nine fields as every UAT script, so results can be compared across scripts and testers.*

{{figure: fig-c6-01 | Figure 6.1 — UAT-001 Login Functionality, the worked example from the Step 6 UAT Test Sheet template}}

*Figure 6.1 — UAT-001 Login Functionality, the worked example from the Step 6 UAT Test Sheet template*

*Source: Flow7 Step 6 — Testing in the Target System(s), Help Notes Part A (SP Data Consultancy Ltd, V1.0).*

The same test restated in table form:

| Field | Value |
|:-|:-|
| Test ID | UAT-001 |
| Test case name | Login Functionality |
| Description | Verify that a user can log in with valid credentials |
| Test steps | 1. Go to the login page<br>2. Enter valid username and password<br>3. Click "Login" |
| Test data | Username: testuser · Password: Test@123 |
| Expected result | User is successfully logged in and the dashboard is displayed |
| Actual result | Logged in and the dashboard displayed |
| Pass / fail | PASS |
| User comments | Dashboard was very slow to load and the user details were not formatted — a data issue but successful business process |

*Note the user comment. The script passed: the user logged in and reached the dashboard. But the tester also recorded two things worth following up — a slow dashboard and unformatted user details. That is exactly what the comments field is for. The issues go on the UAT Testing List at low severity: go-live is not blocked, but they are recorded, owned and tracked.*

## Your Turn

### Exercise 6.1 — Draft One UAT Script

Pick **one** process from your Step 4 User Target Processing List — ideally one the business cannot run without, such as *"Raise a sales order"*, *"Receive stock against a purchase order"* or *"Create a new customer"*. Draft its UAT script:

1. Give it a **Test ID** and a short **test case name**.
2. Write a one-line **description** — what is being tested, and why.
3. Write the **test steps**, numbered, the way you would explain them to a new starter.
4. Name the **test data** the tester will use.
5. Write the **expected result**.

Leave the actual result, pass/fail and comments blank — they are for the tester.

If you struggled to write the test steps, that is a useful finding: the process was not yet documented in enough detail in Step 4. Go back, fix it there, and the script will almost write itself.

**Where to record it:** a Step 6A *UAT Test Sheet*, which already has all nine fields.

> 📄 **Your template.** Flow7 Step 6 — *UAT Test Sheet* (one per process) and *UAT Testing List* (your single issue log — consider the Excel version if issues grow), with progress tracked in the *Flow7 Data Migration Project Plan Checklist*. Download at **stuartparkins.com**.

## What you have achieved in this chapter

Every business process that must work in the new system has a UAT script, and every script has been run by a real user. Issues are owned, dated and severity-rated. Critical and serious issues are closed or have an accepted, dated plan. And a recorded sign-off — a decision, not an assumption — says the business is ready to go live with the data and processes as tested.

## You're Ready to Move On When…

| Gate | ✓ |
|:-|:-:|
| Every process on your Step 4 list has a UAT script that has been run in a non-live environment, with results recorded | ☐ |
| Your UAT Testing List is up to date, with a status, due date, resolution and severity for every issue | ☐ |
| Every critical and serious issue is closed, or has a dated plan the project sponsor has accepted | ☐ |
| Users have logged in, used the system on screen, and confirmed it works for their jobs | ☐ |
| Your data loading plan has been rehearsed enough to estimate the live load time with confidence | ☐ |
| A recorded user-acceptance sign-off says the business is ready to go live | ☐ |

**If you cannot tick every box, do not set the go-live date in stone.** Every important risk should now be measured; the ones that remain should be known, owned and accepted.

**Next:** Chapter 7 — take the prepared, tested, signed-off migration and run it for real.

> ▶ **Know the business.** Before you move on, note what this step taught you about the business: where your understanding of a process differed from the way users actually run it. You will pull these notes together in the closing chapter, *Know the Business*.
