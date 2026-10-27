# Meta-Prompting Guide — Operations Team
**Microsoft Copilot Training | Bajaj Finance Limited**

---

## What Is Meta-Prompting?

Instead of writing a prompt yourself, you ask Copilot to write the prompt for you — by telling it your role, your task, and what you need.

You are essentially saying:

> *"You are a prompt expert. You know how to talk to AI. Write me a prompt I can use for my actual operations work."*

The output becomes your **reference prompt** — something you refine and reuse across SOP reviews, incident reporting, performance analysis, workflow improvement, and stakeholder communication workflows.

---

## The Core Meta-Prompt Formula

```
Act as a Microsoft Copilot prompt expert.
I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].
Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

## Meta-Prompts for Operations Team — Bajaj Finance

Use these as your starting point. Copy, paste, and run in Copilot. Use the output as your working prompt for your exercises.

---

### 1. SOP Creation and Documentation

```
Act as a Microsoft Copilot prompt expert.
I am an Operations Manager at Bajaj Finance Limited. I am responsible for process
governance across multiple operational functions including Lending Ops, Collections,
Compliance Ops, Retail Ops, and Service Ops. I maintain a SOP Register in Excel with
fields including: SOP ID, Process Name, Department, Owner, Version, Last Reviewed,
Review Due, Status, and Compliance Risk.

I need to identify all SOPs that are Overdue or Under Review, flag any SOPs whose
review is due within the next 30 days, and produce a compliance risk-sorted action
summary for the Head of Compliance. I also need to generate a structured SOP template
for a new process that needs to be documented.

My audience is the Head of Compliance and the Ops Head who need a clear view of SOP
review gaps and a ready-to-use template for new documentation.

Write me a detailed, structured Copilot prompt I can use to produce these outputs from
my attached Excel register. The prompt should specify format (overdue SOP table sorted
by Compliance Risk — Critical first + review-due calendar by department + structured
SOP template with sections for Purpose, Scope, Roles, Process Steps, SLA, Escalation
Matrix, and Version Control), tone (formal and compliance-ready), and what to surface
(Status = Overdue or Under Review, Compliance Risk = Critical or High, SOPs with no
review scheduled in the next quarter).
```

---

### 2. Incident Analysis

```
Act as a Microsoft Copilot prompt expert.
I am an Operational Risk Analyst at Bajaj Finance Limited. I prepare quarterly incident
reviews for the COO and Risk Committee. I maintain an Incident Log in Excel with fields
including: Incident ID, Date, Process Affected, Severity, Root Cause Category,
Description, Downtime (hrs), Customers Impacted, Resolution Time (hrs), Status,
and Recurrence.

I need to analyse Q1 FY2026-27 incidents to produce an executive summary of incident
volume and severity, a root cause frequency analysis identifying systemic patterns,
and the top 3 corrective action recommendations with suggested process owners. I also
need to flag all open and escalated incidents requiring immediate attention.

My audience is the COO and the Risk Committee who need an analytical, data-led view
of operational incident health and the actions being taken to prevent recurrence.

Write me a structured Copilot prompt I can use to produce this Incident Analysis Report
from my attached Excel log. The prompt should specify format (executive summary 4–5
lines + root cause frequency table: Category | Count | Recurring | Avg Resolution Time
| Severity Range + corrective actions table with suggested owners + open/escalated
incidents flag), tone (analytical and concise — Risk Committee ready), and what to
surface (Recurrence = Yes items, P1 and P2 severity incidents, Status = Open or
Escalated).
```

---

### 3. Operational Reporting

```
Act as a Microsoft Copilot prompt expert.
I am the Head of Operations at Bajaj Finance Limited. I prepare monthly and quarterly
performance reports for the COO and Board. I maintain an Ops Performance Report in
Excel with fields including: Month, Transactions Processed, SLA Adherence %,
First-Time-Right %, Avg Processing Time (hrs), Error Rate %, Cost per Transaction (₹),
Customer Complaints, Escalations, and Incidents (P1+P2).

I need to analyse Q1 FY2026-27 data to identify performance highlights and areas of
concern, track month-on-month trends for key metrics, and produce a structured
executive commentary with management recommendations — ready to share with the COO
directly.

My audience is the COO and Senior Leadership who need a concise, data-led performance
narrative — not raw numbers.

Write me a structured Copilot prompt I can use to produce this Ops Performance Report
from my attached Excel tracker. The prompt should specify format (Q1 highlights —
3 positive metrics + areas of concern — 3 declining metrics with Apr | May | Jun trend
table + management recommendations — 3 actionable bullet points), tone (executive-level,
data-led, concise — 400 words maximum), and what to surface (metrics worsening
month-on-month, SLA adherence below 94%, error rate above 1.5%, complaint and
escalation spikes).
```

---

### 4. Workflow Optimization

```
Act as a Microsoft Copilot prompt expert.
I am a Business Process Improvement Manager at Bajaj Finance Limited. I lead
operational transformation initiatives across the Ops function. I maintain a Workflow
Analysis tracker in Excel with fields including: Process Name, Steps Count, Manual
Steps, Automated Steps, Avg Cycle Time (hrs), Benchmark Time (hrs), Rework Rate %,
Bottleneck Step, Automation Potential, and Efficiency Score.

I need to identify the top 3 processes with the highest inefficiency by analysing cycle
time gaps against benchmark, rework rates, and manual step ratios. I also need to
produce a 30-day quick-win action plan and an automation roadmap identifying which
High-potential processes should be prioritised for RPA or AI tooling in Q2.

My audience is the VP Operations and the Ops Transformation team who need a
prioritised, actionable improvement plan — not just a list of problems.

Write me a structured Copilot prompt I can use to produce this Workflow Optimization
Report from my attached Excel tracker. The prompt should specify format (inefficiency
priority matrix: Rank | Process | Efficiency Score | Cycle Time Gap | Rework Rate |
Bottleneck | Automation Potential | Recommended Action + 30-day quick-win plan with
expected impact + automation roadmap for Q2), tone (practical and solution-focused —
for a transformation workshop), and what to surface (Efficiency Score below 50,
Avg Cycle Time more than 2x Benchmark, Rework Rate above 15%, Automation Potential
= High).
```

---

### 5. Operational Communication

```
Act as a Microsoft Copilot prompt expert.
I am an Operations Lead at Bajaj Finance Limited. I manage all stakeholder
communications across the Ops function including incident alerts, escalation notices,
monthly reports, compliance updates, and process advisories. I maintain a Stakeholder
Comms Log in Excel with fields including: Comm ID, Date, Type, Subject, Audience,
Sent By, Key Message, Action Required, Deadline, and Status.

I need to identify all communications with Status = Pending, In Progress, Escalated,
or Critical, flag any items past their deadline, and produce a structured COO Weekly
Comms Briefing covering active items requiring senior decisions and a prioritised
action dashboard sorted by deadline.

My audience is the COO and Senior Leadership who need a concise, action-oriented
view of open communications — readable in under 2 minutes.

Write me a structured Copilot prompt I can use to produce this Comms Briefing from
my attached Excel log. The prompt should specify format (action-required dashboard:
Comm ID | Subject | Audience | Action Required | Deadline | Status | Priority sorted
by deadline + draft COO briefing email under 200 words with subject line), tone
(concise and action-oriented — senior leader ready), and what to surface (Status =
Pending, In Progress, Escalated, or Critical; items past deadline; communications
requiring CEO or COO decision).
```

---

## Still Confused? Run This.

If the prompt Copilot wrote doesn't feel right — too generic, wrong format, wrong tone — don't rewrite it yourself. Use this follow-up prompt instead:

```
The prompt you wrote is a good start, but I need you to adjust it.
Here is what I want to change:

- [Describe what felt off — e.g., "the format doesn't match what our COO
  expects in a monthly operations report"]
- [Describe what's missing — e.g., "it doesn't tell Copilot to flag incidents
  where the root cause is recurring and no corrective action is assigned"]
- [Describe the tone issue — e.g., "it sounds too casual for a Risk Committee
  presentation"]

Please rewrite the prompt with these corrections.
Keep the same structure (Role / Task / Context / Format / Tone) but fix the parts
I've described.
```

---

## What to Do With the Output

Once Copilot gives you a well-structured prompt:

1. **Read it** — does it reflect your actual Ops role and the kind of work you manage at BFL?
2. **Replace the placeholders** — swap generic text with your real reporting period, department name, process category, or metric threshold.
3. **Run it** — use it on the exercise dataset (`Ops_Copilot_Dataset.xlsx`) provided during training.
4. **Save it** — this is your reusable reference prompt for that operations task type.

---

## 📋 Operations Team Quick Reference

| Use Case | Sheet in Dataset | Key Fields Copilot Will Use |
|---|---|---|
| SOP Creation & Documentation | SOP Register | Status, Review Due, Compliance Risk, Owner |
| Incident Analysis | Incident Log | Severity, Root Cause Category, Recurrence, Status |
| Operational Reporting | Ops Performance Report | SLA Adherence %, Error Rate %, Complaints, Trends |
| Workflow Optimization | Workflow Analysis | Efficiency Score, Cycle Time Gap, Rework Rate %, Automation Potential |
| Operational Communication | Stakeholder Comms Log | Status, Deadline, Action Required, Audience |

---

*Bajaj Finance Limited | AI Academy — Operations Team | Microsoft Copilot Training Programme*
