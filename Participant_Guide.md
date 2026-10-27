# M365 Copilot Prompt Guide
## Operations Team — 5 Workplace Use Cases
**Program: GenAI for Enterprise Teams | Technizer India**
**Tool: M365 Copilot Chat (microsoft365.com/chat)**

---

## How to Use This Guide

This guide gives you ready-to-use prompts for five real operations tasks. Each use case follows a simple two-step approach:

**Step 1 — Generate your prompt** using the Meta Prompt Framework
**Step 2 — Apply it live** by attaching your Excel file and running the generated prompt

You don't need to write prompts from scratch. The Meta Prompt does that for you.

---

## The RTCFT Prompt Framework

Use this template whenever you want Copilot to write a high-quality prompt for any task:

```
Act as a Microsoft Copilot prompt expert.

Role:    I am a [YOUR JOB TITLE] in [YOUR TEAM/DEPARTMENT].
Task:    I need to [WHAT YOU WANT TO DO].
Context: My data is in [FILENAME]. The relevant sheet is [SHEET NAME].
Format:  The output should be [table / bullet points / email / report].
Tone:    The tone should be [formal / concise / executive-level / action-oriented].

Write me a detailed, ready-to-use Copilot prompt I can apply directly.
```

> **Remember:** After Copilot generates your working prompt, attach your Excel file using `/` in Copilot Chat — then paste and run the generated prompt.

---

## Dataset: What's in Your Excel File

| Sheet | What It Contains |
|---|---|
| **SOP Register** | 12 SOPs with owner, version, review dates, and compliance risk |
| **Incident Log** | 12 operational incidents with severity, root cause, and resolution details |
| **Ops Performance Report** | Monthly KPIs: SLA, first-time-right %, error rate, complaints |
| **Workflow Analysis** | 12 processes with cycle times, manual steps, bottlenecks, automation potential |
| **Stakeholder Comms Log** | 10 internal communications with audience, action required, and status |

**File name:** `Ops_Copilot_Dataset.xlsx`

---

## Use Case 1 — SOP Creation and Documentation

**Scenario:** Your team manages SOPs across multiple functions. Some are overdue for review. Use Copilot to identify gaps and prioritise action.

---

### Step 1 — Paste this Meta Prompt into Copilot Chat

```
Act as a Microsoft Copilot prompt expert.

Role:    I am an Operations Manager responsible for process governance.
Task:    I need to analyse our SOP Register, identify which SOPs are overdue for review,
         and generate a summary table with recommended actions.
Context: My data is in Ops_Copilot_Dataset.xlsx, sheet: SOP Register.
         Columns: SOP ID, Process Name, Department, Owner, Version,
         Last Reviewed, Review Due, Status, Compliance Risk.
Format:  A structured table showing overdue SOPs sorted by Compliance Risk (Critical first),
         followed by 3 bullet-point action recommendations.
Tone:    Formal and action-oriented — suitable for sharing with the Head of Compliance.

Write me a detailed, ready-to-use Copilot prompt I can apply directly to this file.
```

---

### Step 2 — Attach the Excel file using `/`, then paste this Working Prompt

```
I am an Operations Manager reviewing our SOP compliance status.

Analyse the SOP Register sheet in the attached file. Identify all SOPs where:
- Status is "Overdue" or "Under Review"
- Review Due date has passed or is within 30 days

Present findings in a table with columns:
SOP ID | Process Name | Owner | Compliance Risk | Status | Days Overdue | Recommended Action

Sort by Compliance Risk (Critical → High → Medium → Low).
After the table, provide 3 concise action recommendations for the Ops Head.
Use formal, compliance-ready language.
```

---

### Try It Yourself

Adapt this for your own SOPs by changing the role, the sheet name, and the compliance risk threshold. Try asking Copilot to also draft a reminder email to overdue SOP owners.

---

## Use Case 2 — Incident Analysis

**Scenario:** Your team logged 12 incidents in Q1. Leadership wants a root cause summary and corrective action recommendations before the Risk Committee meeting.

---

### Step 1 — Paste this Meta Prompt into Copilot Chat

```
Act as a Microsoft Copilot prompt expert.

Role:    I am an Operational Risk Analyst preparing a quarterly incident review.
Task:    I need to analyse Q1 FY2026-27 operational incidents, identify recurring root
         cause categories, and highlight the top 3 systemic issues needing process fixes.
Context: My data is in Ops_Copilot_Dataset.xlsx, sheet: Incident Log.
         Columns: Incident ID, Date, Process Affected, Severity, Root Cause Category,
         Description, Downtime (hrs), Customers Impacted, Resolution Time (hrs),
         Status, Recurrence.
Format:  Executive summary (4–5 lines), a root cause frequency table,
         then 3 corrective action recommendations with suggested process owners.
Tone:    Analytical and concise — suitable for the COO and Risk Committee.

Write me a detailed, ready-to-use Copilot prompt I can apply directly.
```

---

### Step 2 — Attach the Excel file using `/`, then paste this Working Prompt

```
I am an Operational Risk Analyst reviewing Q1 FY2026-27 incidents.

Analyse the Incident Log sheet in the attached file and provide:

1. Executive Summary (4–5 lines): Total incidents, severity breakdown (P1/P2/P3),
   total customers impacted, total downtime hours, and open/escalated items.

2. Root Cause Analysis Table: Group incidents by Root Cause Category.
   Show: Category | Count | Recurring (Y/N count) | Avg Resolution Time (hrs) | Severity Range.

3. Top 3 Systemic Issues: Based on recurrence and severity, identify the 3 most
   critical process gaps and recommend corrective actions with suggested owners.

Use analytical language appropriate for a Risk Committee presentation.
```

---

### Try It Yourself

Ask Copilot to compare P1 vs P2 incidents separately, or to identify which process areas have the highest customer impact. Try requesting a draft RCA report for the most severe incident.

---

## Use Case 3 — Operational Reporting

**Scenario:** You need to prepare the Q1 performance commentary for the COO. The data is ready in your Excel file. Copilot drafts the narrative for you.

---

### Step 1 — Paste this Meta Prompt into Copilot Chat

```
Act as a Microsoft Copilot prompt expert.

Role:    I am the Head of Operations preparing a monthly performance report for the COO.
Task:    I need to analyse Q1 FY2026-27 operations data, identify performance trends,
         flag metrics that are declining, and generate an executive commentary.
Context: My data is in Ops_Copilot_Dataset.xlsx, sheet: Ops Performance Report.
         Columns: Month, Transactions Processed, SLA Adherence %, First-Time-Right %,
         Avg Processing Time (hrs), Error Rate %, Cost per Transaction (₹),
         Customer Complaints, Escalations, Incidents (P1+P2).
Format:  Structured report with: (a) Q1 highlights — 3 positive metrics,
         (b) Q1 concerns — 3 declining metrics with month-on-month trend,
         (c) Recommended management actions — 3 bullet points.
Tone:    Executive-level, data-led, concise — 400 words maximum.

Write me a detailed, ready-to-use Copilot prompt I can apply directly.
```

---

### Step 2 — Attach the Excel file using `/`, then paste this Working Prompt

```
I am the Head of Operations preparing a Q1 FY2026-27 performance report for the COO.

Analyse the Ops Performance Report sheet in the attached file (April–June 2026 data) and produce:

A. Q1 Performance Highlights (3 positives): Metrics where the team performed well
   or showed improvement across the quarter.

B. Areas of Concern (3 declining metrics): Identify metrics trending negatively
   month-on-month. For each, show: Metric | Apr | May | Jun | Trend | Risk Level.

C. Management Recommendations (3 actions): Specific, actionable recommendations
   tied directly to the data — not generic advice.

Keep the entire report under 400 words. Use executive-level, data-led language
suitable for sharing with the COO directly.
```

---

### Try It Yourself

Ask Copilot to convert the report into a 5-bullet executive briefing for a town hall, or to generate a subject line and intro paragraph for an email to the leadership team.

---

## Use Case 4 — Workflow Optimization

**Scenario:** Your team runs 12 core processes. You need to identify which ones are most inefficient and build a quick-win improvement plan for the next 30 days.

---

### Step 1 — Paste this Meta Prompt into Copilot Chat

```
Act as a Microsoft Copilot prompt expert.

Role:    I am a Business Process Improvement Manager conducting a workflow efficiency review.
Task:    I need to analyse 12 operational processes, identify the top 3 with the highest
         inefficiency, and recommend specific improvement actions including automation opportunities.
Context: My data is in Ops_Copilot_Dataset.xlsx, sheet: Workflow Analysis.
         Columns: Process Name, Steps Count, Manual Steps, Automated Steps,
         Avg Cycle Time (hrs), Benchmark Time (hrs), Rework Rate %, Bottleneck Step,
         Automation Potential, Efficiency Score.
Format:  A ranked priority matrix (top 3 processes) with: Process | Gap vs Benchmark |
         Rework Rate | Bottleneck | Automation Potential | Recommended Intervention.
         Followed by a 30-day quick-win action plan with 3 specific actions.
Tone:    Practical and solution-focused — for an Ops transformation workshop.

Write me a detailed, ready-to-use Copilot prompt I can apply directly.
```

---

### Step 2 — Attach the Excel file using `/`, then paste this Working Prompt

```
I am a Business Process Improvement Manager reviewing operational workflows
for a transformation initiative.

Analyse the Workflow Analysis sheet in the attached file and provide:

1. Inefficiency Priority Matrix — Top 3 processes needing urgent improvement:
   Rank by combining (Cycle Time Gap vs Benchmark) + (Rework Rate %) + (Manual Step ratio).
   Table: Rank | Process | Efficiency Score | Cycle Time Gap | Rework Rate |
          Bottleneck | Automation Potential | Recommended Action.

2. Quick-Win Action Plan (30 days): For the top 3 processes, one specific,
   implementable action each — with expected impact (time saved / error reduction).

3. Automation Roadmap: Which 2 "High" automation potential processes should be
   prioritised for RPA/AI tooling in Q2?

Use practical, workshop-ready language.
```

---

### Try It Yourself

Ask Copilot to calculate potential hours saved per month if cycle times hit benchmark across the top 3 processes. Or ask it to suggest which bottleneck steps could be handled by a Copilot agent.

---

## Use Case 5 — Operational Communication

**Scenario:** Multiple stakeholder communications are pending action. You need to quickly identify critical items and draft the COO's weekly briefing email.

---

### Step 1 — Paste this Meta Prompt into Copilot Chat

```
Act as a Microsoft Copilot prompt expert.

Role:    I am an Operations Lead preparing an end-of-week internal communications summary.
Task:    I need to review pending and critical communications, identify items requiring
         immediate action, and draft a structured update for the COO's weekly briefing.
Context: My data is in Ops_Copilot_Dataset.xlsx, sheet: Stakeholder Comms Log.
         Columns: Comm ID, Date, Type, Subject, Audience, Sent By, Key Message,
         Action Required, Deadline, Status.
Format:  (a) A table of open/escalated/pending items sorted by deadline,
         (b) A draft email to the COO summarising critical items and required decisions.
Tone:    Concise and action-oriented — for a senior leader who reads in 2 minutes.

Write me a detailed, ready-to-use Copilot prompt I can apply directly.
```

---

### Step 2 — Attach the Excel file using `/`, then paste this Working Prompt

```
I am the Operations Lead preparing the weekly comms briefing for the COO.

Analyse the Stakeholder Comms Log sheet in the attached file and provide:

1. Action-Required Dashboard: Filter all entries where Status is "Pending",
   "In Progress", "Escalated", or "Critical".
   Table: Comm ID | Subject | Audience | Action Required | Deadline | Status | Priority.
   Sort by deadline (earliest first). Flag any items past their deadline.

2. Draft COO Weekly Briefing Email:
   Subject: Ops Weekly Comms Status — June 6, 2026
   Include: Number of active communications, critical items needing CEO/COO decision,
   overdue actions, and decisions required this week.
   Keep under 200 words. Use formal, executive-ready language.
```

---

### Try It Yourself

Ask Copilot to draft individual follow-up emails for each overdue action item, personalised to the relevant audience. Or ask it to generate a comms tracker summary for a Monday morning standup.

---

## Bonus — Generate a New SOP from Scratch

You don't need existing data to get value from Copilot. Try this prompt directly in Copilot Chat or Word Copilot to generate a complete SOP template:

```
I am an Operations Manager at a financial services NBFC.

Draft a Standard Operating Procedure (SOP) for:
"Customer Grievance Redressal — Digital Channels"

Structure:
1. Purpose & Scope
2. Definitions
3. Roles and Responsibilities (table: Role | Responsibility | Escalation Authority)
4. Process Steps (numbered, with decision points noted)
5. TAT / SLA Requirements (table)
6. Escalation Matrix (3 levels)
7. Compliance & Regulatory Requirements (RBI reference placeholders)
8. Version Control Log

Use formal, RBI-compliant language. Keep each section concise but complete.
```

Adapt the process name to any SOP your team needs — onboarding, cash management, vendor approval, and so on.

---

## RTCFT at a Glance

| Letter | Stands For | What to Write |
|---|---|---|
| **R** | Role | Your job title — "I am an Ops Manager / Risk Analyst / Ops Lead…" |
| **T** | Task | What you need — "Analyse… / Draft… / Identify… / Summarise…" |
| **C** | Context | File name, sheet name, and key column names |
| **F** | Format | Table / bullet list / email / report / executive summary |
| **T** | Tone | Formal / concise / executive-level / action-oriented |

**Tip:** Always give Copilot the column names from your sheet. The more context you provide, the more precise and usable the output.

---

## Quick Answers

**Does Copilot read all sheets in the file?**
Yes — when you attach the file via `/`, Copilot can access all sheets. Always name the specific sheet in your prompt for accurate results.

**Can Copilot write back to my Excel file?**
Copilot Chat produces text output. Copy the table or text into your Excel file. In-app Excel Copilot can insert columns and formulas directly.

**Is my data secure?**
M365 Copilot operates within your organisation's Microsoft 365 tenant. Your data does not leave your environment.

**Can I use these prompts for my own data?**
Yes — replace the file name, sheet name, and column names with your actual data. The RTCFT framework works for any dataset or document.

**What if the output isn't quite right?**
Follow up with a refinement prompt: *"Make it shorter / more formal / add a column for priority / present as an email instead."* Copilot remembers the context of the conversation.

---

*Technizer India | GenAI for Enterprise Teams*
*M365 Copilot — Operations Team Session*
