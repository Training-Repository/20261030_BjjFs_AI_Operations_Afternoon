# Copilot Notebooks — Participant Guide
### One workspace, all your files, no re-attaching
**Bajaj Finance Limited | M365 Copilot Training — Operations Team**
**Files used:** `Ops_Copilot_Dataset.xlsx`, `Ops_Copilot_Demo.xlsx`, and the guides in this repo

---

## Why Notebooks?

In a normal Copilot Chat, every new conversation starts from zero. You attach the file again, explain your role again and restate the format you want again. You are also limited to **3 attachments per prompt**.

A **Copilot Notebook** is a saved workspace for one piece of work. You add your files to it once, as **references**, and write your standing instructions once. After that, every chat you start inside the notebook is grounded on those references, and it stays that way across sessions and days.

| | Regular Copilot Chat | Copilot Notebook |
|---|---|---|
| Files | Attached per prompt (max **3** in BFL) | Added once as **references**, then available to every chat in the notebook |
| Context | Lost when you open a new chat | Kept in the notebook across chats and days |
| Instructions (role, tone, format) | Re-typed in every prompt (the RTCFT block) | Set once in the notebook's **Copilot instructions** |
| Grounding | Your prompt + attachments (+ wider M365 / web, depending on settings) | **Only** the references you added, so answers stay focused on your files |
| Outputs | Chat replies | Chat replies, saved pages, and (where enabled) Word / PowerPoint drafts, mind maps, study guides |

> 💡 **Rule of thumb:** use one notebook per piece of work, such as the Q1 Ops review, an SOP refresh cycle or a monthly Ops review pack. Don't create a new notebook for every question.

---

## ⭐ Going Beyond the 3-Attachment Limit

This is the most useful reason to use Notebooks at BFL.

- The 3-file limit applies to **attachments in a chat prompt**.
- Notebook **references** are added separately, through the notebook's *Add references* panel rather than the chat box. Copilot then grounds its answers on **all** of them together.
- According to Microsoft's documentation:
  - **Copilot Chat** users can add up to **50 references**, and all 50 are used for grounding.
  - **Microsoft 365 Copilot** (licensed) users can add more than 300 references. The first **300** are used for grounding.
- A **OneDrive or SharePoint folder** can be added as a single reference. Every file you put in that folder later is then available to the notebook without any extra steps.

**In practice:** you can ask one question that draws on SOPs, incident logs, performance reports and branch case data at once, without attaching anything to the prompt.

> ⚠️ **Check in your own tenant:** the 3-attachment cap is BFL's setting for chat. If references in your notebook also appear capped, report it to your trainer or IT, because the admin policy may be set differently. Exercise 2 below is a simple way to test this.

---

## Before You Begin

- [ ] You can sign in to the **M365 Copilot** app (desktop or web) with your BFL work account, and you see **Notebooks** in the left navigation.
- [ ] You have copied the files from this repo to your **OneDrive** (a folder such as `OneDrive › Copilot-Training-Ops`).
- [ ] You have made `.txt` copies of the three Markdown guides. Notebooks accept `.docx, .pptx, .xlsx, .pdf, .loop, .page, .txt, .rtf` and OneNote pages, but **not `.md`**. Download the guides, then rename them:

| Original in repo | Rename to |
|---|---|
| `MetaPrompting_Guide.md` | `MetaPrompting_Guide.txt` |
| `Participant_Guide.md` | `Participant_Guide.txt` |
| `Excel_To_PowerPoint.md` | `Excel_To_PowerPoint.txt` |

Your OneDrive folder should now contain **5 files**:

```
Copilot-Training-Ops/
├── Ops_Copilot_Dataset.xlsx   (SOP Register, Incident Log, Ops Performance Report,
│                                            Workflow Analysis, Stakeholder Comms Log)
├── Ops_Copilot_Demo.xlsx         (25 branch operations cases)
├── MetaPrompting_Guide.txt
├── Participant_Guide.txt
└── Excel_To_PowerPoint.txt
```

That is already **more than the 3-attachment limit**, which is intentional for these exercises.

---

# Exercise 1 — Create Your Notebook
**Time:** ~5 minutes

### Step 1 — Create it
1. In the M365 Copilot app, select **Notebooks** → **New notebook**.
2. Name it: `BFL Operations — Q1 FY26-27 Review`

### Step 2 — Add references
1. Select **Add references** (at the top of the content pane in the Copilot app, or the **+** next to *References* in OneNote).
2. Choose **one** of these methods:
   - **Option A: files.** Select all 5 files from your OneDrive folder, or use **Upload** to add them from your computer.
   - **Option B: folder (recommended).** Select the `Copilot-Training-Ops` **folder** as a single reference.
3. Select **Add**.

> 💡 **Option B scales better.** When you drop next month's incident log into the folder, the notebook can use it without any extra step.

### Step 3 — Set the Copilot instructions (your RTCFT Role, Format and Tone, written once)
Open the notebook's **Copilot instructions** and paste:

```
I work in the Operations team at Bajaj Finance Limited (an NBFC).
The period is Q1 FY2026-27 (April–June 2026). TAT and SLA are in days unless a column says hours.
Currency is ₹.

When you answer:
- Use only the references in this notebook. Name the file and sheet for every number you quote.
- If a number is not in the references, say "not in the data" — do not estimate.
- Lead with a 3-line summary, then a table, then recommendations with a suggested owner.
- Tone: formal, concise and action-oriented — suitable for the COO or Head of Operations.
- Use Green / Amber / Red status where an SLA, benchmark or target exists.
```

### ✅ Check
Your notebook shows **5 references**, or 1 folder, and the instructions are saved.

---

# Exercise 2 — Validate the Notebook Can See Everything
**Time:** ~5 minutes

Before you rely on any analysis, confirm that Copilot has read every reference. This is the same idea as Step 1 of the 9-Step Flow.

Start a chat **inside the notebook** and type:

```
List every reference in this notebook. For each one, give:
- the file name
- what it contains (sheets / sections, row counts, periods covered)
- one fact from it that proves you have read it
Then tell me if any file looks incomplete or could not be read.
```

### ✅ Check
- [ ] All **5 files** are listed. This is more than you could attach to one chat prompt.
- [ ] For `Ops_Copilot_Dataset.xlsx`, it names the five data sheets (SOP Register, Incident Log, Ops Performance Report, Workflow Analysis, Stakeholder Comms Log) plus a README sheet.
- [ ] For `Ops_Copilot_Demo.xlsx`, it mentions 25 cases (BOP-001 to BOP-025).

> If a file is missing, open **References**, confirm it is listed, and check that you have access to it in OneDrive.

---

# Exercise 3 — Ask Across Files (the payoff)
**Time:** ~10 minutes

Neither of these questions could be answered in one regular chat prompt without going past the 3-attachment limit. In the notebook, you don't attach anything.

### 3a — One process, every source

```
Loan disbursement appears in several places:
- Branch Ops Data (Ops_Copilot_Demo.xlsx) — Service Type "Loan Disbursal"
- Workflow Analysis, Incident Log and SOP Register (Ops_Copilot_Dataset.xlsx)

Build a one-page view of loan disbursement:
1. Branch SLA performance: cases, breaches, average TAT vs SLA
2. Workflow: cycle time vs benchmark, bottleneck step, automation potential
3. Incidents: which incidents hit loan disbursement, severity, recurrence
4. SOP: owner, version, review due, status
Then tell me: is there a single root cause that links these? Recommend 3 actions.
```

**What a good answer contains:**
- **Branch SLA:** 6 of the 10 branch SLA breaches are Loan Disbursal.
- **Workflow:** cycle time is 6.8 hrs against a 4 hr benchmark, and the bottleneck is the Credit Bureau Check.
- **Incidents:** INC-2026-010 was a recurring CIBIL API timeout.
- **SOP:** SOP-OPS-002 is owned by Rahul Mehta.
- **The link:** the Credit Bureau Check and CIBIL issue appears in three different sources.

### 3b — Data + method in one question

```
Using the RTCFT framework in Participant_Guide and the data in the
Workflow Analysis sheet, write me a Working Prompt for a 30-day quick-win plan for the
Ops transformation workshop. Then run that Working Prompt yourself on the Workflow Analysis
data and show the output.
```

### ✅ Check
- [ ] The answer quotes figures with **file and sheet names**, as your instructions asked.
- [ ] 3a draws on **both** workbooks and at least three sheets.
- [ ] You did **not** attach a single file.

> 💡 **Tip:** names differ between sources ("Loan Disbursal" vs "Loan Disbursement"). Check that Copilot matched the right rows. Treat its matches as a starting point for you to confirm, not a final answer.

---

# Exercise 4 — Re-run the Five Ops Use Cases Without Re-attaching
**Time:** ~10 minutes

In `Participant_Guide.md`, every use case says *"Attach the Excel file using `/`, then paste the Working Prompt."* In the notebook, you skip the attach step.

Pick any two use cases and use the short versions below. The notebook instructions already supply the role, tone and format.

| Use Case | Prompt inside the notebook |
|---|---|
| 1 — SOP Documentation | `From the SOP Register: list SOPs that are Overdue or Under Review, or due within 30 days, sorted by Compliance Risk (Critical first). Add 3 actions for the Head of Compliance.` |
| 2 — Incident Analysis | `From the Incident Log: executive summary (count by P1/P2/P3, customers impacted, downtime), a root cause frequency table with recurrence, and the top 3 systemic issues with suggested owners.` |
| 3 — Operational Reporting | `From the Ops Performance Report (Apr–Jun 2026): 3 highlights, 3 declining metrics with the month-on-month trend, and 3 management actions — under 400 words for the COO.` |
| 4 — Workflow Optimization | `From Workflow Analysis: rank the top 3 inefficient processes by cycle-time gap, rework rate and manual-step ratio. Give a 30-day quick-win plan and the 2 "High" automation candidates for Q2.` |
| 5 — Operational Communication | `From the Stakeholder Comms Log: table of Pending / In Progress / Escalated / Critical items sorted by deadline, flag overdue items, then draft a COO weekly briefing email under 200 words.` |

### ✅ Check
Compare the output with the one you got in the regular chat earlier. The format and tone should be consistent **without** you retyping the RTCFT Role, Format and Tone, because the notebook instructions supply them.

---

# Exercise 5 — The 9-Step Flow, Inside One Notebook
**Time:** ~10 minutes

`Excel_To_PowerPoint.md` uses three separate chats (A: Discovery, B: Execution, C: PowerPoint) and asks you to **attach the file again** in Chat B. In a notebook:

1. Start **Chat A** in the notebook and run Steps 1–4 on a sheet of your choice, such as the Incident Log. Copy the Working Prompt from Step 4.
2. Start a **new chat** in the **same notebook** (Chat B) and paste the Working Prompt. The file is already there, so there is no re-attaching.
3. Save the useful output as a **page** in the notebook, so it doesn't sit only in a chat.
4. If your notebook shows **create options** (Word document / PowerPoint deck), generate the Step-6 document or the Step-9 deck from the notebook. Otherwise, continue with the PowerPoint agent as in the workbook.

> 💡 **Why this helps:** the chats stay separate, which keeps the output clean, while the files and instructions are shared. You get the benefit of the 3-chat method without the re-attaching.

---

## Optional Extras (if visible in your tenant)

Microsoft is rolling out Notebook features in stages, so some of these may not appear for you yet.

| Feature | Try this |
|---|---|
| **Mind map** | Create a mind map of the notebook to see how SOPs, incidents, workflows and branch SLAs connect. |
| **Study guide** | Generate a quiz or flashcards from `MetaPrompting_Guide` to test yourself on RTCFT. |
| **Word / PowerPoint from notebook** | Turn your Exercise 3a output into a Word brief or a 5-slide Ops review deck. |
| **Share the notebook** | Share with a colleague so they work from the same references and instructions. |

---

## Efficiency Rules — Quick Reference

| Do | Avoid |
|---|---|
| One notebook per piece of work (e.g. "Q1 Ops Review", "SOP Refresh FY27") | One giant notebook for everything, because the grounding gets noisy |
| Put role, period, units, tone and format in **Copilot instructions** | Re-typing the RTCFT block in every prompt |
| Add a **folder** reference when logs and reports keep arriving | Re-uploading each new version by hand |
| Remove outdated references (old SOP versions, superseded logs) | Keeping v1, v2 and v3 of the same file, because Copilot may quote the wrong one |
| Ask Copilot to **name file + sheet** for every number | Accepting figures you can't trace |
| Save good outputs as **pages** | Leaving key results only in chat history |
| Start a **new chat in the same notebook** for each new task | One endless chat, where earlier answers leak into later ones |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| `.md` file can't be added | Rename to `.txt`, or copy the content into a notebook page. |
| Copilot says it can't find a number | Check that the file is in **References** and that you can open it. Ask: *"Which sheet contains X?"* |
| Copilot quotes the `Pivot - …` sheets instead of the raw data | Name the sheet: *"Use only the Branch Ops Data sheet."* |
| Answer uses the wrong file version | Remove old versions from References. |
| Notebooks not in the left navigation | Your licence or tenant setting may not include Notebooks yet. Tell your trainer. |
| Folder reference returns partial results | Very large folders are ranked for relevance, so name the specific file in your prompt. |

---

## Further Reading

- [How Microsoft Copilot Notebooks works](https://support.microsoft.com/en-us/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works)
- [Add references to your Copilot Notebook](https://support.microsoft.com/en-us/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook)
- [Microsoft 365 Copilot release notes](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

## 📝 Notes

**What I would put in a notebook at work:**

&nbsp;

**My standing Copilot instructions:**

&nbsp;

---

*Bajaj Finance Limited | M365 Copilot Training — Operations Team*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*
