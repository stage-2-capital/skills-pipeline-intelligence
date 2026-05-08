---
name: "pipeline-intelligence-engine"
description: "Generate weekly pipeline health reports, interactive dashboards, and coaching priorities from CRM data — all in one prompt. Use this skill whenever a RevOps leader, revenue leader, or sales ops professional mentions pipeline analysis, forecast reporting, pipeline health, deal velocity, stage conversion, weekly pipeline review, or forecast accuracy. Also trigger when someone asks for a pipeline dashboard, rep performance analysis, or coaching priorities based on pipeline data."
---

# Pipeline Intelligence Engine

## Overview

Transform raw CRM pipeline data into three parallel deliverables: a pipeline health spreadsheet, an interactive HTML dashboard, and a coaching priorities document. This replaces the 6-8 hours RevOps teams typically spend each Monday building the same reports manually.

## How to Use This Skill

1. **Install**: Upload this skill folder to Claude Cowork via Settings > Capabilities > Add Skill
2. **Select your folder**: Point Cowork to a folder containing your pipeline data (CSV or spreadsheet export from your CRM)
3. **Trigger it**: Say "Run the Pipeline Intelligence Engine on my pipeline data" or simply "Analyze my pipeline"
4. **Answer the setup questions**: The skill will ask about your CRM, quota targets, and analysis preferences
5. **Get your deliverables**: Three files appear in your folder — spreadsheet, dashboard, coaching doc
6. **Make it recurring**: Say "Save this as a weekly workflow" to run it every Monday

**Pro tip**: Add your quota targets and rep roster to the folder as a reference file. The skill gets smarter with more context.

## Example Use Cases

**RevOps Weekly Pipeline Review**
Export your Salesforce pipeline every Monday morning, drop it in the folder, and trigger the skill. In 5 minutes you have your pipeline health spreadsheet for the forecast call, an interactive dashboard for the CRO, and coaching talking points for every manager's 1:1.

**Sales Leader Forecast Prep**
Before your Wednesday forecast meeting, run this on the latest pipeline pull. The coaching priorities doc tells you exactly which deals to probe and what questions to ask each rep. No more guessing which deals are real.

**Board-Ready Pipeline Metrics**
When the board wants pipeline health data, run the skill and hand them the dashboard. It visualizes funnel conversion, coverage ratios, and velocity — all from your actual data, not a static slide from last month.

**New RevOps Hire Onboarding**
Share this skill with a new RevOps team member. They can generate the same reports the senior team produces on day one — no training required on which spreadsheets to pull or how to calculate pipeline velocity.

**Multi-Segment Analysis**
Run it on enterprise pipeline one day, mid-market the next. Compare the dashboards side by side to see where conversion rates differ and which segment needs different coaching.

## Prerequisites

Before running, confirm the user has:
- CRM data access (Salesforce, HubSpot export, or CSV pipeline dump)
- If using a connector: ensure the CRM connector is enabled
- If using files: the user should have a pipeline data export in the working folder

Ask: "Do you have your pipeline data as a CSV/spreadsheet export, or should I pull it from a connected CRM?"

## Workflow

### Step 1: Gather Context

Ask the user these questions (skip any they've already answered):
1. What CRM or data source are you using? (Salesforce, HubSpot, CSV export)
2. What's your current fiscal quarter and quota target?
3. Do you want analysis by rep, by team, or both?
4. What's your average sales cycle length?
5. Any specific deals or segments you want highlighted?

### Step 2: Ingest and Analyze Data

Read the pipeline data from the working folder or pull via CRM connector. Identify:
- All active opportunities with: stage, amount, close date, owner, created date, last activity date
- Calculate: stage conversion rates, average days in stage, pipeline velocity, weighted pipeline value
- Flag: deals with no activity in 14+ days, deals past close date, deals that moved backward in stage

### Step 3: Execute Three Parallel Tasks

Spin up 3 parallel sub-agents:

**Task 1 — Pipeline Health Spreadsheet (xlsx)**
Create a spreadsheet with these tabs:
- **Summary**: Total pipeline, weighted value, coverage ratio, quarter-over-quarter comparison
- **By Stage**: Deal count, total value, avg days in stage, conversion rate per stage
- **By Rep**: Pipeline value, weighted value, number of deals, avg deal size, velocity
- **Deals at Risk**: Stale deals (14+ days no activity), past-due close dates, backstage moves
- **Week-over-Week**: Pipeline movement — new deals added, deals advanced, deals lost, deals won

**Task 2 — Interactive Dashboard (HTML)**
Build a single-file HTML dashboard with:
- Pipeline funnel visualization (stage by stage, with conversion percentages)
- Pipeline by rep (bar chart with quota overlay)
- Forecast vs. actual trend line (if historical data available)
- Deals at risk table (sortable, with days-since-activity)
- Pipeline coverage ratio gauge (target: 3x)
Use Chart.js or D3 for visualizations. Make it clean, professional, dark-mode optional.

**Task 3 — Coaching Priorities Document (docx or md)**
Generate a document with:
- **Top 5 Deals Most Likely to Slip**: For each — deal name, current stage, risk factors, recommended action, suggested talk track for the 1:1
- **Rep Performance Highlights**: Which reps are ahead/behind, where their pipelines are thin
- **This Week's Focus Areas**: 3-5 specific actions the sales leader should take based on the data
- **Forecast Risk Assessment**: Likelihood of hitting quota based on current pipeline and historical conversion rates

### Step 4: Save and Present

Save all three deliverables to the working folder:
- `pipeline-health-[date].xlsx`
- `pipeline-dashboard-[date].html`
- `coaching-priorities-[date].md` (or .docx)

Present a summary to the user:
- Key pipeline metrics (total, weighted, coverage)
- Top 3 risks identified
- Recommended immediate actions

### Step 5: Offer to Save as Recurring Workflow

Ask: "Want me to save this as a weekly workflow you can trigger every Monday? I can also package it as a plugin your whole RevOps team can use."

## Output Quality Standards

- All calculations must be verifiable — include formulas in the spreadsheet
- The dashboard must render correctly in any modern browser
- Coaching priorities must include specific deal names and actionable recommendations, not generic advice
- Use the user's actual data — never generate placeholder or dummy data

## Common Edge Cases

- **Missing fields**: If data is incomplete (no close dates, no rep assignments), flag it and work with what's available
- **Small datasets**: If fewer than 20 deals, skip statistical analysis and focus on deal-by-deal review
- **Multiple pipelines**: Ask if they want combined or separate analysis
