# Pipeline Intelligence Engine Skill

A Claude Skill that turns your raw CRM pipeline data into three forecast-ready deliverables — a pipeline health spreadsheet, an interactive dashboard, and a coaching priorities document — in a single prompt. Saves 6–8 hours per week of manual forecast prep.

Built by [Stage 2 Capital](https://stage2.capital) for RevOps teams, sales leaders, and CROs who want to walk into the forecast meeting knowing where the risk is — not finding out in the room.

---

## What It Does

Drop a Salesforce, HubSpot, or any CRM export into Claude with this skill installed, and you get three files generated in parallel:

- **Pipeline Health Spreadsheet (`.xlsx`)** — Stage conversion rates, velocity metrics, deals at risk, week-over-week movement, and per-rep breakdown, all with auditable formulas
- **Interactive Dashboard (`.html`)** — Funnel visualization, pipeline by rep vs. quota, coverage ratio gauge, and a sortable deals-at-risk table. Renders in any modern browser.
- **Coaching Priorities Document (`.md` / `.docx`)** — The 5 deals most likely to slip, rep performance highlights, and specific talk tracks for 1:1s — based on your actual data, not templates

This isn't AI summarizing a CSV. It's AI doing the analytical work a senior RevOps lead would do — calculating velocity, flagging stalled deals, identifying coaching patterns by rep — so your team can spend their time on the conversations that actually move pipeline.

---

## Who It's For

- **Sales leaders & CROs** prepping for weekly forecast calls
- **RevOps teams** producing recurring pipeline analytics
- **Sales managers** running 1:1s and looking for specific coaching talk tracks
- **Founders & GTM leaders** at early-stage B2B companies building their first forecast cadence
- **New RevOps hires** who need to produce senior-team-level reporting on day one

---

## Prerequisites

Before running the skill, confirm you have:

- **CRM data access** — A CSV or spreadsheet export from Salesforce, HubSpot, or any CRM. Alternatively, connect via CRM connector or MCP integration.
- **Pipeline export fields** — Active opportunities with: deal name, stage, amount, close date, owner, created date, last activity date. The more fields, the richer the output.
- **Quota context** — Current quarter's quota target and rep roster. Optional but strongly recommended — the skill gets significantly smarter with this context.

> **Watch out:** If your pipeline export is missing close dates or rep assignments, the skill will flag the gaps and work with what's available — but stage velocity and rep analysis will be limited. Clean data in, better coaching insights out.

---

## Installation

1. Download the `pipeline-intelligence-engine` skill folder from this repo
2. Open Claude and go to **Settings > Capabilities > Add Skill**
3. Upload the skill folder
4. Confirm it appears in your active skills list

**Optional — Connect Your CRM:** If you prefer live data pulls over manual exports, connect Salesforce or HubSpot via the built-in connector or MCP integration in Claude settings. Once connected, the skill can pull pipeline data directly — no export required.

---

## How to Use

### Step 1: Point Claude at your folder

Create a project folder containing your pipeline export, quota sheet, and rep roster. Select that folder in Claude.

### Step 2: Trigger the skill

Use any of these prompts:

```
Run the Pipeline Intelligence Engine on my pipeline data
```

```
Analyze my pipeline
```
