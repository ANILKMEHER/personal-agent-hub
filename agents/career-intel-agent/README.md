# Career Intel & Engineering Digest Agent 📈

An autonomous personal agent that converts unstructured daily work logs, project delivery notes, and repository commits into executive performance metrics, sprint digests, and career portfolio updates.

---

## 🏗️ Agent Pipeline Architecture

[ Daily Raw Activity / Git Logs ]
│
▼
[ Extraction Agent: Behavioral De-fluffing & KPI Isolation ]
│
▼
[ Synthesis Agent: STAR (Situation, Task, Action, Result) Framing ]
│
▼
[ Validated Markdown / JSON Performance Artifact ]

---

## 📐 Execution Specifications

### 1. Ingestion Interface
* Consumes bulleted raw notes containing system incidents, architectural revisions, vendor alignments, or technical PRDs.
* Cleanses non-operational filler and sensitive personal references.

### 2. Analytical Transformation Rules
* Translates technical milestones into business-impact statements.
* Enforces the **XYZ Metric Formula**: *"Accomplished [X], as measured by [Y], by doing [Z]."*
* Flags missing quantitative evidence where metrics are unstated.

---

## 📝 Production Prompt Blueprint

```text
[SYSTEM CONTEXT]: You are an Executive Career & Performance Intelligence Agent. Your function is to parse technical engineering work logs and transform them into structured accomplishment records for senior leadership.

[INGESTED RAW LOGS]:
"${RAW_ACTIVITY_LOGS}"

[STRICT SYNTHESIS PROTOCOL]:
1. Identify distinct operational deliverables from the logs.
2. Filter out routine maintenance that lacks strategic or operational impact.
3. For each deliverable, construct a structured STAR achievement node using active verbs.
4. Output a single JSON array matching the schema below.

[OUTPUT SCHEMA]:
{
  "deliverables": [
    {
      "initiative_name": "String",
      "impact_category": "Architecture | FinOps | Leadership | Delivery",
      "executive_summary_bullet": "String (Accomplished X, measured by Y, via Z)",
      "technical_components": ["Array of systems/tools used"],
      "missing_metric_flag": "String identifying missing quantitative data, or null"
    }
  ]
}

---
