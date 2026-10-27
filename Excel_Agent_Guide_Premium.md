# Copilot in Excel — Participant Exercise Guide
### Formulas & Pivot Tables for Branch Operations
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `Ops_Copilot_Demo.xlsx`

> **Premium licence required.** This guide uses Copilot inside Excel (Agent / Edit with Copilot), which needs a paid Microsoft 365 Copilot licence. On M365 Copilot (Basic), use `Excel_Chat_Guide.md` instead. It produces the same results.

---

## Before You Begin

- Use **Copilot agent** to open the agent in the Copilot panel
- Add `Ops_Copilot_Demo.xlsx` from OneDrive
- Keep the Copilot panel open throughout all exercises
- The file has **25 rows of branch operations data** — one sheet, no formula columns yet
- Columns N–Q are intentionally blank — you will fill these using Copilot

### Dataset Overview

| Column | Field | Description |
|--------|-------|-------------|
| A | Case ID | Unique case reference (BOP-001 to BOP-025) |
| B | Branch Name | Branch where case was raised |
| C | Branch Code | Short branch identifier |
| D | Zone | West / Central |
| E | Service Type | Account Opening, Loan Disbursal, KYC Update, FD Booking, Closure Request |
| F | Case Owner | Staff member handling the case |
| G | Case Received Date | When the case was logged |
| H | Case Closed Date | When it was resolved (blank if still open) |
| I | TAT (Days) | Actual turnaround time in days |
| J | SLA Limit (Days) | Benchmark TAT for that service type |
| K | Customer Segment | Retail, SME, Corporate, HNI |
| L | Priority | Normal, High, Urgent |
| M | Status | Closed, Pending, Escalated |
| **N–Q** | *(blank)* | **You will add these using Copilot** |

---

## Exercise 1 — Add a Formula Column: Escalation Flag

### Your Turn
Type into the Copilot panel:

```
In column N, add a formula that flags each case as "Escalate" or
"OK" based on its Priority and Status:
- "Escalate" if Priority is "Urgent" OR Status is "Escalated"
- "OK" for all other cases
Label the column "Escalation Flag". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(OR(L3="Urgent",M3="Escalated"),"Escalate","OK")
```
Copilot will name the column, write the formula, and fill it down to N27.

---

## Exercise 2 — Add a Formula Column: SLA Breach

### Your Turn
Type into the Copilot panel:

```
In column O, add a formula that checks whether each case breached
its SLA. Compare the TAT in column I against the SLA Limit in
column J. If TAT is greater than the SLA Limit, return "Breach".
Otherwise return "On Time". If TAT is blank (case still open),
return "Pending".
Label the column "SLA Breach". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","Pending",IF(I3>J3,"Breach","On Time"))
```

---

## Exercise 3 — Add a Formula Column: Pending Days

### Your Turn
Type into the Copilot panel:

```
In column P, calculate the number of days each case has been
open. If the case is already closed (column H has a date), return 0.
If the case is still open, return the number of days since it was
received (column G) up to today.
Label the column "Pending Days". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(H3<>"",0,TODAY()-DATEVALUE(G3))
```
Cases with a closed date show 0. Open cases show how many days they've been waiting.

---

## Exercise 4 — Add a Formula Column: TAT Category

### Your Turn
Type into the Copilot panel:

```
In column Q, classify each closed case into a TAT performance
category based on how the actual TAT (column I) compares to the
SLA Limit (column J):
- "Fast" if TAT is 50% or less of the SLA Limit
- "Within SLA" if TAT is within the SLA Limit
- "Moderate Breach" if TAT exceeds SLA by up to 50%
- "Critical Breach" if TAT exceeds SLA by more than 50%
- "Pending" if TAT is blank
Label the column "TAT Category". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","Pending",IF(I3<=J3*0.5,"Fast",IF(I3<=J3,"Within SLA",IF(I3<=J3*1.5,"Moderate Breach","Critical Breach"))))
```

---

## Exercise 5 — Ask Copilot to Explain a Formula

### Your Turn
Copy the formula from cell **Q3** and paste it into the Copilot panel:

```
Explain this formula to me in simple terms. What does each part do?
```

### What Copilot Will Explain
> *"This formula first checks if the TAT in I3 is blank — if so, the case is still Pending. Then it checks if TAT is at most half the SLA limit, which means the team was very Fast. Next it checks if TAT is within the full SLA Limit — that's Within SLA. If TAT went over the limit but not by more than 50%, it's a Moderate Breach. Anything beyond 150% of the SLA Limit is a Critical Breach. Each IF only runs when the previous condition wasn't true."*

---

## Exercise 6 — Create a Pivot Table: Cases by Service Type and Status

### Your Turn
Type into the Copilot panel:

```
Create a pivot table that shows the count of cases for each
Service Type, broken down by Status (Closed, Pending, Escalated).
I want to see which services have the most unresolved or escalated
cases.
```

### What Copilot Will Produce
A new sheet with a Pivot Table:
- **Rows:** Service Type (Account Opening, Loan Disbursal, KYC Update, FD Booking, Closure Request)
- **Columns:** Status (Closed, Pending, Escalated)
- **Values:** Count of Case ID

---

## Exercise 7 — Create a Pivot Table: Average TAT by Case Owner

### Your Turn
Type into the Copilot panel:

```
Now create a pivot table showing the average TAT in days for each
Case Owner, broken down by Service Type. I want to identify which
staff members or service types are taking the longest to resolve.
```

### What Copilot Will Produce
- **Rows:** Case Owner (Neha Joshi, Rahul Mehta, Priya Desai, Amit Kulkarni, Sunita Rao, Ravi Patil)
- **Columns:** Service Type
- **Values:** Average of TAT (Days)

> **Discussion Point:** Which owner has the highest average TAT on Loan Disbursals? Which service type consistently breaches SLA?

---

## Exercise 8 — Bonus: Ask Copilot for Insights

### Your Turn
Type into the Copilot panel:

```
Look at the data in this sheet. Which branches have the most SLA
breaches? Summarise the key risk areas for the Branch Ops team
in 3 bullet points.
```

### What to Expect
Copilot will scan the data and generate a natural-language summary — no formula needed. This shows how Copilot moves from *calculation* to *analysis* to *insight* within the same Excel session.

---

*Bajaj Finance Limited | AI Academy — Branch Operations | Microsoft Copilot Training Programme*
