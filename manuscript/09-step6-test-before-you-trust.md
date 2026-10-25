**CHAPTER 9**

# Test Before You Trust

## Step 6 — Testing in the Target System(s)

**Structured testing in a safe environment is what turns a migration plan into a migration result. Every issue you find here is one you have time to fix calmly — before go-live depends on it.**

## Where You Are in Flow7

You have come a long way. In **Chapter 4** you found every data source. In **Chapter 5** you faced what condition the data was actually in. In **Chapter 6** you built your one source of the truth. In **Chapter 7** you learned what your destination system will actually accept — and you wrote down, in the User Target Processing List, every business process that will need to work in the new system. In **Chapter 8** you mapped the master to the target, cleaned what needed cleaning, and produced sample data ready for the next step.

That next step is this one. Step 6 is where you **prove the migration works — in a safe place, with real people, before anyone has to depend on it.**

In the cooking analogy that runs through Flow7, Steps 1–5 were about ingredients, prep and recipe. **Step 6 is the tasting.** You make a small batch first. You let the people who actually eat it tell you whether it is right. You fix what is wrong. *Then* you serve it to the guests.

## In this chapter you will…

- Build a UAT test script for every business process that must work in the new system
- Run those scripts in a DEV or UAT sandbox, not in production
- Verify record counts, spot-check key records, test the workflows users actually do
- Manage a central UAT Testing List — Status, Due Date, Owner, Severity for every issue
- Sign off go-live readiness from a measured position, not a hopeful one

## What you'll need from earlier chapters

- Your Step 4B User Target Processing List (every process to be tested)
- Your Step 1C Business Process List (cross-check that nothing important is missing)
- Your Step 5C3 sample test data set (the cleaned, confirmed records to load)
- A non-live environment to test in — DEV or UAT or sandbox, *not* the live system
- Access to the front-end as well as the database

## Why This Matters

There is a temptation, once mapping is finished, to feel finished. You are not finished. Mapping tells you what *should* happen. Testing tells you what *actually* happens when the cleaned data hits the new system, the new screens, and the people who have to use them every day.

Three things only show up in testing:

- **Import errors** that the mapping document could not predict — a field that accepts the data on paper but rejects it in practice; a relationship between two records that does not survive the import; a value that the target system silently truncates or reformats.
- **Process failures** — the data lands correctly but a key workflow no longer works. Users cannot raise a sales order. Stock cannot be received. A report does not return what it used to.
- **User-experience surprises** — the data is there, the process technically works, but the screen takes a minute to load, or a field that everyone relies on is now buried three clicks deep. These do not fail any technical test, but they fail the business.

Step 6 is the structured way to find all three before they reach a live system. The Flow7 Step 6 help notes are blunt about what is at stake: **the amount and severity of issues found in testing is a deciding factor in whether the go-live date needs to be pushed back.** Testing is therefore not a tick-box at the end — it is the gate that protects Step 7.

## What You Are Actually Doing

Step 6 has two halves that work together, and they map onto the two sheets in the Flow7 Step 6 template.

**A. User Acceptance Test (UAT) Scripts — one per process.**

For every business process that must work in the new system, you write a short, structured script that a real user can follow and record results against. Each script has the same fields, every time, so that results are comparable and traceable:

- **Test ID** — a unique identifier, so the result can be tracked end-to-end.
- **Test Case Name** — a brief, descriptive name (e.g. *"Login Functionality"*, *"Raise Sales Order"*).
- **Description** — what is being tested and why.
- **Test Steps** — a clear, numbered list of actions for the tester to follow.
- **Test Data** — the specific record(s) or values needed for the test, if any.
- **Expected Result** — what should happen if the system works as intended.
- **Actual Result** — what *actually* happened, filled in by the tester.
- **Pass / Fail** — the verdict.
- **User Comments** — space for observations, screenshots, or notes (e.g. *"Dashboard was very slow to load… data issue but successful business process"*).

The point of this structure is that *anyone* can follow it. A finance user can run the AR scripts; a warehouse user can run the goods-receipt scripts. The tester does not need to be technical — the script tells them exactly what to do and what to look for.

**B. The UAT Testing List — one central issue log.**

The scripts produce results. The results produce issues. The UAT Testing List is the single, central document where every raised issue is recorded, owned, tracked and closed. Each row carries:

- **Test ID** — linking back to the UAT script the issue came from.
- **Issue** — what is wrong.
- **Status** — *Open / In Progress / To Be Tested / Closed*.
- **Due Date** — when the fix or response is expected.
- **Resolution / Escalation** — what is being done about it and who needs to know.
- **Severity** — *None / Minor / Serious / Critical*.

The status and severity columns do most of the work. Status tells you whether the issue is moving; severity tells you whether it can be lived with. **Manage this list diligently** — the Flow7 help notes put it exactly that way, because this list is what tells you, at any point, whether you are ready to go live or not.

### ▶ Where the UAT Scripts Come From

You do not write the UAT scripts from scratch in Chapter 9. You wrote the *list of processes* back in **Chapter 7**, in the **User Target Processing List (Step 4B)** — every target-system process that needs testing and a "how to" documenting.

Step 6 instructs you, in its own help notes, to **have that completed Step 4B list to hand**, and to **cross-check it against the Business Process List you built in Step 1 (1C)**, "*just to cross check nothing has been missed that is important*."

The chain runs:

**Step 1C** *(Business Process List — what the business actually does)* → **Step 4B** *(User Target Processing List — how those processes will work in the new system)* → **Step 6A** *(a UAT script per process)*.

If a process is missing from 4B, it will be missing a UAT script, and it will be untested. This is why Step 6 sends you back to those earlier documents before you write a single script — and it is the strongest practical argument for not skimping on Chapters 1 and 4.

## Key things to get right

Five disciplines turn testing into measured evidence rather than wishful thinking.

**1. Test the workflows, not just the data.** Counts and spot-checks prove that *something* arrived. UAT scripts prove that a real user can do their real job — raise a sales order against the migrated customer, receive stock against the migrated product, run month-end against the migrated transactions. The Step 6 guidance is explicit that every business process needs a matching UAT script.

**2. Anyone should be able to run a UAT script.** A finance user runs the AR scripts, a warehouse user runs the goods-receipt scripts, a sales user runs the order-entry scripts. The script tells them exactly what to do and what to look for. If a script is too vague for a non-technical user to follow, it is too vague — go back and tighten it.

**3. Chunk the data when the target has display limits.** Sage X3 shows 1,000 records at a time. If your target has a similar limit, the test plan must respect it — otherwise you are testing things you cannot actually see in the interface.

**4. Iterate without alarm.** A failed test often sends you back to Step 5 (fix a mapping rule), Step 3 (the master set was missing something), or Step 4 (the target needs a setting changed). That is the loop working as intended, not a sign anything has gone wrong. Expect it; build time for it.

**5. Get front-end sign-off, not just back-end sign-off.** Users need to log in, use the system, and confirm it works for the job they actually do. Testing without front-end access is testing a story, not a system.

## From the Field — Sage 50 to Sage X3

*The following is drawn from a real migration documented by Stuart Parkins: a successful manufacturer, recently bought out, moving from Sage 50 to Sage X3.*

By the time this project reached Step 6, the assessment had already exposed the scale of the work — 7,500+ product records, 1,500+ assembly instructions to create from scratch, and warehouse and manufacturing rules that had lived in people's heads. The case study is unusually clear about what Step 6 actually looked like in practice.

**The environments mattered.** The work happened in two sandboxes — a **DEV** environment and a **UAT** environment — separate from the live X3 used by the parent company. I created my own personal Data Loading Plan and tested it multiple times as we went through both. DEV was where the load was iterated and the rough edges sanded; UAT was where the users came in.

**Test the import templates first, before anything else.** I always test the import templates first — making sure they actually work with every data set — because early testing is crucial. The lesson here is small but important: do not wait until you have a perfectly cleaned data set before you try to load anything. Prove the *pipe* works on a representative sample before you fill it.

**Chunking for error-checking.** Sage X3's GUI was limited to displaying 1,000 records at a time, which sounds like a screen quirk but was a real testing constraint. The team **chunked the data for error checking** so that what landed in the system could actually be inspected by eye. The principle generalises beyond X3: if your target system has a display or import limit, your test plan must respect it, or you will be testing things you cannot actually see.

**Iteration was expected, not a surprise.** Although the data loading tests were a moving target, the total load time could still be estimated quite accurately. ETL is iterative by nature — if you follow a similar approach to Flow7 you may reassess new data, then add or combine it into the master data set and feed it through to testing. Translating that into Flow7 language: a failed test fed an update to the master set in Step 3, which fed an updated mapping in Step 5, which fed the next round of tests in Step 6. The loop ran several times before any test came out clean.

**Front-end access was non-negotiable.** Get access to the front-end system. You need to see what users see. It is one thing to confirm a record exists in the database; it is another thing entirely to see how it renders on the screen the user actually uses. Testing without front-end access is testing a story, not a system.

One more practical lesson from the same project that lands squarely in Step 6: **map the new IDs back to the old ones.** Once records are loaded into Sage X3 they receive new internal IDs. Part of the testing was confirming that those new IDs could be tied back to the **self-created unique identifiers from the source system** that had been built into the master set in Step 3 — *not* to SKUs or customer numbers, which appear unique but often are not. That mapping became essential at go-live in Chapter 10; testing was where it was proven.

## Your Checklist

These items are taken directly from Step 6 of the Flow7 Data Migration Project Checklist. Tick each one only when it is genuinely done.

**6A — Create and assign UAT testing sheets**

- ☐ **6A1** — Run process training for critical business processes

**6B — Create a UAT Testing List (issue log)**

- ☐ **6B1** — Manage issues daily and feed back to the team and owners

In practice — drawing on the Step 6 help notes that sit behind these line items — completing 6A and 6B means you can also confirm the following:

- ☐ You have your **Step 4B User Target Processing List** to hand and have cross-checked it against your **Step 1C Business Process List** so nothing important is missing.
- ☐ Every process on that list has a **matching UAT Test Sheet** with the eight standard fields filled in (Test ID, Test Case Name, Description, Test Steps, Test Data, Expected, Actual, Pass/Fail, Comments).
- ☐ Your **Sample Test Data** from Step 5C3 has been loaded into a non-live environment (DEV/UAT/sandbox).
- ☐ **Record counts** for each test load have been validated against expectations.
- ☐ **Spot-checks** on individual records have been completed in the front-end system, not only in the database.
- ☐ **Relationships and links** between records (e.g. customer ↔︎ orders, product ↔︎ stock) have been verified.
- ☐ The **UAT Testing List** is open, owned, and every raised issue has a Status, Due Date, Resolution/Escalation note and Severity rating.
- ☐ **Critical and Serious** issues are either closed or have an agreed plan, dated, before any go-live decision.

> ▶ **Worked example — UAT-001 Login Functionality**
>
> *The full UAT Test Sheet page from the Step 6 template, drawn from a real test run. The fields are the same eight every UAT script uses — Test ID, Test Case Name, Description, Test Steps, Test Data, Expected, Actual, Pass/Fail, User Comments — so every result is comparable across scripts and across testers.*

{{figure: fig-09-01 | Figure 9.1 — UAT-001 Login Functionality, the worked example from the Step 6 UAT Test Sheet template}}

*Figure 9.1 — UAT-001 Login Functionality, the worked example from the Step 6 UAT Test Sheet template*

*Source: Flow7 Step 6 — Testing in the Target System(s), Help Notes Part A (SP Data Consultancy Ltd, V1.0).*

The same test restated in table form:

| Field | Value |
|:-|:-|
| Test ID | UAT-001 |
| Test Case Name | Login Functionality |
| Description | Verify that a user can log in with valid credentials |
| Test Steps | 1. Go to the login page<br>2. Enter valid username and password<br>3. Click "Login" |
| Test Data | Username: testuser · Password: Test@123 |
| Expected Result | User is successfully logged in and the dashboard is displayed |
| Actual Result | Logged in and the dashboard displayed |
| Pass / Fail | PASS |
| User Comments | Dashboard was very slow to load and the user details were not formatted — a data issue but successful business process |

*Note the User Comment. The script passed: the user logged in and reached the dashboard. But the tester also recorded two issues worth following up — slow dashboard performance and unformatted user details. That is exactly what the User Comments field is for. The PASS goes on the issue list at a low severity; the migration is not blocked, but the issues are recorded, owned and tracked through Chapter 10 stabilisation.*

## Your Turn

Step 6 thinking happens on the page; Step 6 production work happens in the proper tools — the UAT Test Sheet template and the UAT Testing List template, both downloadable.

**Exercise — 20 minutes, on the page.**

Pick **one** business process from your Step 4B User Target Processing List — ideally a critical one that the business cannot operate without (e.g. *"Raise a sales order"*, *"Receive stock against a purchase order"*, *"Create a new customer"*). For that one process, draft a UAT script in the boxes below.

**Test ID:** {{write-in}}

**Test Case Name:** {{write-in}}

**Description** — what is being tested and why:

{{write-in-box}}

**Test Steps** — numbered, the way you would tell a new starter:

{{write-in-box}}

**Test Data** — the specific record(s) or values the tester will use:

{{write-in-box}}

**Expected Result** — what should happen if everything is working:

{{write-in-box}}

**Actual Result** *(left blank — for the tester to complete)*

**Pass / Fail** *(left blank — for the tester to complete)*

**User Comments** *(left blank — for the tester to complete)*

If you struggled to write the Test Steps, that is a useful finding: it usually means the process from Step 4B was not yet documented in enough detail. Go back, fix it there, and the script will write itself.

**Then take it to the templates.**

Move this draft script into the **Flow7 Step 6 — UAT Test Sheet** template, and create one for every other process on your Step 4B list. Open a fresh copy of the **Flow7 Step 6 — UAT Testing List** template and use it as your single issue log, with daily updates to Status and Severity. If issues grow in number, the help notes' own advice applies: *"create copies (consider an Excel version if issues grow!)"* — exactly the situation the spreadsheet version of the template exists for.

## What you have achieved in this chapter

Every business process that must work in the new system has a UAT script, and every script has been run by a real user. Issues are owned, dated and severity-rated. Critical and serious issues are closed or have an accepted plan with a date. A recorded user-acceptance sign-off exists — a decision, not an assumption — that the business is ready to go live with the data and the processes as tested. Chapter 10 takes that sign-off and runs the migration for real.

## You're Ready to Move On When…

Step 6 is genuinely complete — and you are ready for **Chapter 10, Go Live** — when **all** of these are true:

- Every process on your **Step 4B User Target Processing List** has a matching **UAT Test Sheet** that has been executed in a non-live environment, with **Actual Result** and **Pass/Fail** filled in.
- Your **UAT Testing List** is up to date, with every issue carrying a Status, Due Date, Resolution/Escalation and Severity.
- All **Critical** and **Serious** issues are either Closed or have an agreed, dated plan that the project sponsor has accepted.
- You have **front-end** sign-off, not just back-end sign-off — users have logged in, used the system, and confirmed it works for the job they do.
- Your **data loading plan** has been rehearsed in DEV/UAT enough times that you can estimate the live load time with confidence.
- A **user acceptance sign-off** exists — a recorded decision, not an assumption — that the business is ready to go live with the data and the processes as tested.

When those boxes are ticked, Step 6 has done its job: every important risk has been measured, and the ones that remain are known, owned and accepted. The next chapter takes that prepared, tested, signed-off migration and runs it for real.
