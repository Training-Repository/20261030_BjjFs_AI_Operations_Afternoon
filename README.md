# M365 Copilot Training — Operations Team (Bajaj Finance Limited)

Training materials for a Microsoft 365 Copilot enablement session for the Bajaj Finance Limited (BFL) Operations team, delivered by Technizer India under the **GenAI for Enterprise Teams** program.

The session covers prompt engineering (meta-prompting, RTCFT framework), Excel formulas and pivot tables with Copilot, the end-to-end flow from a raw data file to a leadership-ready deck, using Copilot Notebooks to work across more files than the chat attachment limit, and turning a large document into a formatted PDF.

The session follows the Inspect → Plan → Execute workflow shown in [`Workflow.png`](Workflow.png).

## Which guide do I use?

| You have | Use |
|---|---|
| M365 Copilot (Basic), the default | `Excel_Chat_Guide.md` for the Excel exercises |
| M365 Copilot (Premium) licence | `Excel_Agent_Guide_Premium.md` for the same Excel exercises, done by Copilot inside Excel |

Every other guide works on both.

## Contents

| File | Description |
|---|---|
| [`MetaPrompting_Guide.md`](MetaPrompting_Guide.md) | Introduces meta-prompting: asking Copilot to write your prompt for you. Includes 5 ready-to-use meta-prompts for Ops use cases (SOP review, incident analysis, performance reporting, workflow optimization, stakeholder comms). |
| [`Participant_Guide.md`](Participant_Guide.md) | Participant guide built around the **RTCFT** (Role–Task–Context–Format–Tone) prompt framework, with step-by-step meta-prompt and working-prompt pairs for the same 5 use cases, plus an FAQ. |
| [`Excel_Chat_Guide.md`](Excel_Chat_Guide.md) | **Default Excel guide.** Formula and pivot exercises using an RTCFT meta-prompt in M365 Copilot, applied by hand, with expected results to check against. |
| [`Excel_Agent_Guide_Premium.md`](Excel_Agent_Guide_Premium.md) | **Premium only.** The same exercises, with Copilot writing the formulas and building the pivots inside Excel. |
| [`Excel_To_PowerPoint.md`](Excel_To_PowerPoint.md) | "AI at Work" workbook describing a 9-step Copilot flow, across three chats (Discovery, Execution, PowerPoint), for turning any file into an analysis, a Word document, and a leadership deck. |
| [`Copilot_Notebooks_Guide.md`](Copilot_Notebooks_Guide.md) | Using Copilot Notebooks as a persistent workspace: add all files once as references, set standing instructions, and query across more files than the 3-attachment chat limit. |
| [`PDF_Playbook.md`](PDF_Playbook.md) | Repeatable process for turning a large document into a formatted PDF using Copilot and Word, with a monthly Ops review pack as the example. |
| [`Ops_Copilot_Dataset.xlsx`](Ops_Copilot_Dataset.xlsx) | Practice dataset for the meta-prompting exercises. Sheets: SOP Register, Incident Log, Ops Performance Report, Workflow Analysis, Stakeholder Comms Log. |
| [`Ops_Copilot_Demo.xlsx`](Ops_Copilot_Demo.xlsx) | Practice dataset for the Excel exercises: 25 rows of branch operations cases, with columns left blank for you to fill using Copilot-generated formulas. |
| [`Workflow.png`](Workflow.png) | The Inspect → Plan → Execute workflow diagram. |
| [`Contact.md`](Contact.md) | Trainer contact details. |

## How to use this material

1. Start with `MetaPrompting_Guide.md` or `Participant_Guide.md` to learn the RTCFT framework and generate working prompts against `Ops_Copilot_Dataset.xlsx`.
2. Move to the Excel exercises on `Ops_Copilot_Demo.xlsx`: `Excel_Chat_Guide.md` by default, or `Excel_Agent_Guide_Premium.md` if you have a Premium licence.
3. Finish with `Excel_To_PowerPoint.md` to practise the full 9-step flow from raw file to analysis, document, and deck.
4. Use `Copilot_Notebooks_Guide.md` to move all of the above into a single Copilot Notebook, with no re-attaching and no 3-file limit.
5. Keep `PDF_Playbook.md` for when a review pack or SOP manual needs to go out as a PDF.

## Requirements

- M365 Copilot (Basic) is enough for everything except `Excel_Agent_Guide_Premium.md`
- Access to Copilot Notebooks in the M365 Copilot app (for `Copilot_Notebooks_Guide.md`)
- Excel files uploaded to OneDrive so they can be attached in M365 Copilot

---

*Delivered by Technizer India | GenAI for Enterprise Teams*
