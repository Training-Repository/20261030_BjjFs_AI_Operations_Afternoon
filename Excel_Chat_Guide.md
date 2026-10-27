# Excel with M365 Copilot (Basic) — No Agent Required
### Formulas & Pivot Tables for Branch Operations, using M365 Copilot chat + Meta-Prompting
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `Ops_Copilot_Demo.xlsx`
**Companion guides:** `MetaPrompting_Guide.md` · `Excel_Agent_Guide_Premium.md` (Agent version)

---

## Who This Guide Is For

`Excel_Agent_Guide_Premium.md` uses **Edit with Copilot** in Excel, which used to be called Agent Mode. In that mode Copilot writes formulas into your cells and builds pivot tables for you, and it needs a **paid Microsoft 365 Copilot licence**.

This guide produces **the same eight results** with **M365 Copilot (Basic) only**:

- **Copilot does the thinking.** It writes the formula, explains the logic and gives you the pivot layout.
- **You do the clicking.** You paste the formula and build the pivot in Excel yourself, which takes about 30 seconds per exercise.

### Which one do you have?

Check the label on Copilot in the Microsoft 365 app or in Excel:

| Label you see | What works for you |
|---|---|
| **M365 Copilot (Premium)** | Either guide. The Agent guide is faster. |
| **M365 Copilot (Basic)** | **This guide.** Run the prompts in M365 Copilot chat (the M365 Copilot app or `m365copilot.com`). Copilot will not edit the workbook for you. |

---

## How Every Exercise Works

```
Step 1 → Paste the Excel Meta Prompt with that exercise's TASK filled in
Step 2 → Read the Working Prompt Copilot generates
Step 3 → Attach Ops_Copilot_Demo.xlsx and run the Working Prompt
Step 4 → Apply Copilot's answer in Excel yourself (paste formula / build pivot)
Step 5 → Verify against the expected numbers in this guide
```

> 💡 **Why Step 5 matters:** without an agent, nobody checks the result but you. The expected numbers below let you spot a wrong formula in seconds.

---

## Before You Begin

1. Open `Ops_Copilot_Demo.xlsx` in **Excel** (desktop or web) and go to the **Branch Ops Data** sheet.
2. Open **M365 Copilot chat** in a second window, either the M365 Copilot app or `m365copilot.com`.
3. Keep both windows side by side.

### What's in the file

- Row 1 is a title and **row 2 holds the headers**. **Data runs in rows 3–27** (25 cases, BOP-001 to BOP-025). Rows 28–29 are a blank row and a note.
- Columns **N–Q already have headers** (`➕ Escalation Flag`, `➕ SLA Breach`, `➕ Pending Days`, `➕ TAT Category`) and empty cells below them. You will fill those cells.
- ⚠️ **Case Received Date (G) and Case Closed Date (H) are stored as text**, for example `1 Jun 2026`, not as real Excel dates. This matters in Exercise 3.
- The workbook also has three ready-made summary sheets (`Pivot - …`). **Build your own pivots on a new sheet** and check them against the expected results in this guide.

| Column | Field | Column | Field |
|---|---|---|---|
| A | Case ID | H | Case Closed Date *(blank if open)* |
| B | Branch Name | I | TAT (Days) *(blank if open)* |
| C | Branch Code | J | SLA Limit (Days) |
| D | Zone | K | Customer Segment |
| E | Service Type | L | Priority (Normal / High / Urgent) |
| F | Case Owner | M | Status (Closed / Pending / Escalated) |
| G | Case Received Date | N–Q | **You fill these** |

---

## ⚡ The Excel Meta Prompt — Your Starting Point

This follows the RTCFT pattern from `MetaPrompting_Guide.md`, adapted for Excel. The file layout is already filled in, so for each exercise you only replace **[TASK]**.

```
Act as a Microsoft Copilot prompt expert specialising in Excel for branch operations.

Role:    I am a Branch Operations Analyst at Bajaj Finance Limited. I use M365 Copilot chat,
         which cannot edit my workbook — I will apply the result in Excel myself.
Task:    I need to: [TASK]
Context: Sheet "Branch Ops Data" in Ops_Copilot_Demo.xlsx.
         Headers are in row 2; data is in rows 3 to 27 (25 cases).
         Columns: A Case ID, B Branch Name, D Zone, E Service Type, F Case Owner,
         G Case Received Date, H Case Closed Date, I TAT (Days), J SLA Limit (Days),
         K Customer Segment, L Priority, M Status.
         Dates in G and H are stored as TEXT like "1 Jun 2026". Open cases have blank H and I.
Format:  The prompt must ask Copilot for:
         1. The exact result (formula for row 3, or pivot/table layout) ready to copy
         2. Step-by-step instructions to apply it manually in Excel
         3. How to handle blanks and text dates
         4. A quick way to verify the result is correct
Tone:    Clear and step-by-step, for an operations user who is not an Excel expert.

Write me a detailed, ready-to-use Copilot prompt I can use in M365 Copilot chat with this file attached.
```

> ✏️ **Short on time?** Once you've done this for Exercise 1, you can reuse the Working Prompt Copilot gave you and swap in the new task for the later exercises.

---

---

# Exercise 1 — Formula Column: Escalation Flag (N)
**Time:** ~8 minutes

### Step 1 — [TASK] to paste into the Meta Prompt
```
write a formula for column N ("Escalation Flag") that returns "Escalate" if Priority (L) is
"Urgent" OR Status (M) is "Escalated", otherwise "OK", for rows 3 to 27
```

### Step 2 — Check the Working Prompt
- [ ] Does it mention row 3 and filling down to row 27?
- [ ] Does it ask for manual steps and a verification check?

### Step 3 — Attach the file and run
Attach `Ops_Copilot_Demo.xlsx` → paste the Working Prompt → send.

### Step 4 — Apply in Excel
1. Click **N3** and paste the formula Copilot gave you.
2. Fill it down to **N27**: select **N3:N27** and press **Ctrl + D**, or double-click the fill handle at the bottom-right corner of N3.

### Step 5 — Verify
Type this in any empty cell, such as **U3**:
```excel
=COUNTIF(N3:N27,"Escalate")
```
**Expected: 6** (BOP-005, 006, 010, 016, 017, 021). The other 19 rows show **OK**.

<details><summary>Reference formula (open only if stuck)</summary>

```excel
=IF(OR(L3="Urgent",M3="Escalated"),"Escalate","OK")
```
</details>

> **Discussion Point:** Which service types and customer segments attract Urgent or Escalated status? Are Corporate and HNI cases getting the fast-track attention they need?

---

# Exercise 2 — Formula Column: SLA Breach (O)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column O ("SLA Breach") that returns "Pending" if TAT (I) is blank,
"Breach" if TAT is greater than SLA Limit (J), otherwise "On Time", for rows 3 to 27
```

### Steps 2–4
Same as Exercise 1, but paste in **O3** and fill down to **O27**.

### Step 5 — Verify
```excel
=COUNTIF(O3:O27,"Breach")
```
**Expected: 10 Breach · 8 On Time · 7 Pending.**
- **Why 7 Pending when column M shows only 5?** The 2 Escalated cases are also still open, so their TAT is blank too.

<details><summary>Reference formula</summary>

```excel
=IF(I3="","Pending",IF(I3>J3,"Breach","On Time"))
```
</details>

> **Discussion Point:** Loan Disbursal accounts for 6 of the 10 breaches. What drives that pattern: credit bureau checks, document gaps or approval hand-offs?

---

# Exercise 3 — Formula Column: Pending Days (P) ⚠️ the text-date trap
**Time:** ~10 minutes

### Step 1 — [TASK]
```
write a formula for column P ("Pending Days") that returns 0 if the case is closed
(Case Closed Date H is not blank), otherwise the number of days from the Case Received
Date (G) to today. Remember G is stored as text like "1 Jun 2026". Rows 3 to 27.
```

### Steps 2–4
Paste in **P3** and fill down to **P27**.

### Step 5 — Verify
- **18 rows show 0**, one for each closed case.
- **7 rows show a number of days**: BOP-003, 006, 008, 011, 017, 019, 023.
  - Each value is today's date minus the Case Received Date. For example, BOP-003 was received on 2 Jun 2026, so its value is the number of days from 2 Jun 2026 to today. BOP-011 (27 May 2026) is the longest-open case and shows the largest number.
  - Every value goes up by one each day, because the formula uses `TODAY()`.

### ❗ If you see `#VALUE!` on the open rows
Your Excel could not read the text date. This depends on your regional settings. Tell Copilot:
```
The formula returns #VALUE! for open rows because DATEVALUE cannot read "1 Jun 2026" in my
regional settings. Give me a version that builds the date from the text without DATEVALUE.
```

<details><summary>Reference formulas</summary>

Try this first. It works in most English regional settings:
```excel
=IF(H3<>"",0,TODAY()-DATEVALUE(G3))
```
This version works in any regional setting:
```excel
=IF(H3<>"",0,TODAY()-DATE(RIGHT(G3,4),MATCH(MID(G3,FIND(" ",G3)+1,3),{"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"},0),LEFT(G3,FIND(" ",G3)-1)))
```
If the result shows as a date instead of a number, set the column format to **Number**.
</details>

> **Lesson:** Copilot's first formula is a *draft*. When a formula errors, don't fix it by hand. Paste the error back into M365 Copilot chat along with the reason.

> **Discussion Point:** Which open cases have waited the longest? Are they concentrated in one owner, branch or service type?

---

# Exercise 4 — Formula Column: TAT Category (Q)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column Q ("TAT Category") that returns: "Pending" if TAT (I) is blank;
"Fast" if TAT is 50% or less of SLA Limit (J); "Within SLA" if TAT is within the SLA Limit;
"Moderate Breach" if TAT exceeds SLA by up to 50%; "Critical Breach" if more than 50%.
Rows 3 to 27.
```

### Steps 2–4
Paste in **Q3** and fill down to **Q27**.

### Step 5 — Verify
**Expected: 8 Within SLA · 5 Moderate Breach · 5 Critical Breach · 7 Pending · 0 Fast.**

> 💡 **Zero "Fast" is correct.** No case closed in half its SLA or less. An empty category doesn't mean the formula is wrong, so always check against the data.

<details><summary>Reference formula</summary>

```excel
=IF(I3="","Pending",IF(I3<=J3*0.5,"Fast",IF(I3<=J3,"Within SLA",IF(I3<=J3*1.5,"Moderate Breach","Critical Breach"))))
```
</details>

---

# Exercise 5 — Ask Copilot to Explain a Formula
**Time:** ~3 minutes

This works exactly as it does in the Agent version. No meta prompt or attachment is needed.

Copy the formula from **Q3** and paste it into M365 Copilot chat:
```
Explain this Excel formula in simple terms for a branch operations user. What does each part
do, and in what order are the conditions checked?
[paste formula here]
```

**What to look for:**
- The explanation should state that the conditions are checked **in order**.
- Each `IF` only runs if the one before it was not true.

---

# Exercise 6 — Pivot Table: Cases by Service Type and Status
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the count of cases for each Service Type (rows) broken down by
Status (columns: Closed, Pending, Escalated). Give me the exact field placement and
click-by-click steps to build it in Excel, plus the expected result table so I can check my pivot.
```

### Steps 2–3
Run the Working Prompt with the file attached, as before.

### Step 4 — Build it in Excel
1. On **Branch Ops Data**, select **A2:Q27** exactly. Don't include the title in row 1 or the note rows below the data.
2. Go to **Insert → PivotTable → New Worksheet → OK**.
3. Place the fields:
   - **Service Type** → Rows
   - **Status** → Columns
   - **Case ID** → Values. It shows as *Count of Case ID*.

### Step 5 — Verify

| Service Type | Closed | Escalated | Pending | Total |
|---|---|---|---|---|
| Account Opening | 5 | | | 5 |
| Closure Request | 1 | 1 | 2 | 4 |
| FD Booking | 4 | | | 4 |
| KYC Update | 2 | | 3 | 5 |
| Loan Disbursal | 6 | 1 | | 7 |
| **Grand Total** | **18** | **2** | **5** | **25** |

*Excel sorts rows and columns alphabetically by default, so your order may differ from the list in the Agent guide.*

> **Discussion Point:** Closure Request has only 1 of 4 cases closed, and KYC Update has 3 cases still pending. Where is the backlog forming?

---

# Exercise 7 — Pivot Table: Average TAT by Case Owner
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the AVERAGE TAT (Days) for each Case Owner (rows) broken down by
Service Type (columns). Give me the field placement, click-by-click steps, how to switch the
value from Count to Average, and the expected row totals.
```

### Step 4 — Build it in Excel
1. Select **A2:Q27** → **Insert → PivotTable → New Worksheet**.
2. Place the fields:
   - **Case Owner** → Rows
   - **Service Type** → Columns
   - **TAT (Days)** → Values
3. Excel may default the value to **Count** because the column contains blanks. To change it:
   - Click the value field → **Value Field Settings → Average → OK**.
   - Blank rows (open cases) are ignored in the average.

### Step 5 — Verify (Grand Total column)

| Case Owner | Average TAT (days) | Closed cases |
|---|---|---|
| Sunita Rao | 12 | 1 |
| Priya Desai | 9.5 | 2 |
| Amit Kulkarni | 8 | 4 |
| Neha Joshi | 5.67 | 3 |
| Rahul Mehta | 5 | 4 |
| Ravi Patil | 5 | 4 |
| **Grand Total** | **6.67** | **18** |

> 💡 **Why your Grand Total may differ from the ready-made `Pivot - TAT by Owner` sheet:** a pivot's Grand Total averages **every closed case**. The "Overall Avg" column on that sheet averages each owner's **per-service averages** instead. The two only match when an owner has one case per service type. Ask Copilot: *"What is the difference between an average of all cases and an average of averages?"*

> **Discussion Point:** Priya Desai has the highest Loan Disbursal TAT (16 days, one Corporate case). Sunita Rao's 12-day average rests on a single case. How many cases does an average need before you act on it? And which service type breaches SLA consistently across owners?

> 💡 **No pivot tables allowed on your machine?** Ask Copilot for the same result as a `COUNTIFS` / `AVERAGEIFS` formula grid instead. For example, `=AVERAGEIFS(I3:I27,F3:F27,"Rahul Mehta")` returns **5**.

---

# Exercise 8 — Bonus: Ask Copilot for Insights
**Time:** ~5 minutes

This works directly in M365 Copilot chat with the file attached. No manual steps are needed.

```
Look at the Branch Ops Data sheet in the attached file. Which branches have the most SLA
breaches (TAT greater than SLA Limit)? If branches are tied, group them by city
(e.g. all "Pune …" branches together). Summarise the key risk areas for the Branch Ops team
in 3 bullet points, quoting Case IDs as evidence.
```

**Expected:**
- **At branch level, 10 branches are tied** with one breach each, so the branch-level question has no single answer.
- **By city:** **Mumbai 3** (Andheri, Dadar, Bandra), **Pune 3** (Wakad, Camp, Shivajinagar), **Nashik 2**, **Solapur 1**, **Nagpur 1**.
- **8 of the 10 breaches** are in the **West** zone, and **6** are Loan Disbursal.

> 💡 **Lesson:** if Copilot names one "top branch", check it against the data. A question that ends in a tie needs a better grouping, and here city works better than branch.

---

## Reference: What Your Results Should Show

| Check | Expected |
|---|---|
| Total cases | 25: 18 Closed · 5 Pending · 2 Escalated |
| Escalation Flag = Escalate | 6 |
| SLA Breach | 10 Breach (8 West, 2 Central) · 8 On Time · 7 Pending |
| Loan Disbursal | Highest volume (7), and 6 of the 10 breaches |
| FD Booking | 3 of 4 cases breached |
| TAT Category | 8 Within SLA · 5 Moderate · 5 Critical · 7 Pending · 0 Fast |
| Highest average TAT | Sunita Rao, 12 days (1 case); Priya Desai, 9.5 days (2 cases) |

---

## Agent vs M365 Copilot (Basic) — What Changes

| | Edit with Copilot (Agent) | M365 Copilot chat + Meta Prompt (this guide) |
|---|---|---|
| Licence | M365 Copilot (Premium) | M365 Copilot (Basic) |
| Writes formula into cells | ✅ Automatic | ✍️ You paste and fill down |
| Builds pivot table | ✅ Automatic | ✍️ You build it using Copilot's layout |
| Explains formulas, gives insights | ✅ | ✅ Same |
| Handles errors | Agent retries | You paste the error back and ask for a fix |
| What you learn | Prompting | Prompting **plus** checking the formula logic yourself |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Formula refers to row 2 or the wrong column | Remind Copilot: *"Headers are row 2, data starts row 3."* |
| `#VALUE!` in Pending Days | This is the text-date issue. See Exercise 3. |
| `#NAME?` after pasting | Curly quotes crept in. Retype the `"` characters in Excel. |
| Pivot shows *Count* instead of *Average* | Change it in **Value Field Settings → Average**. |
| Pivot includes the title or note text | Rebuild it from **A2:Q27** only. |
| Copilot reads a `Pivot - …` sheet instead of the data | Name the sheet: *"Use only the Branch Ops Data sheet."* |
| Copilot says it can't open the file | Re-attach it from OneDrive, or paste the relevant rows as text. |

---

## Further Reading

- [Microsoft Copilot overview: Basic vs Premium experiences](https://learn.microsoft.com/en-us/copilot/overview)
- [Microsoft 365 Copilot overview: in-app features for Basic](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-overview)
- [Microsoft 365 Copilot release notes: Edit with Copilot in Excel](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

*Bajaj Finance Limited | AI Academy — Branch Operations | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India***
