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

### 💻 Step 3: Create `agents/career-intel-agent/run_digest.py`

Create the file: `agents/career-intel-agent/run_digest.py`

```python
#!/usr/bin/env python3
"""
Career Intel Agent - Local Synthesis Pipeline
Author: Anil K. Meher
Description: Parses unstructured operational logs and formats them into structured achievement nodes.
"""

import json
import re
from typing import List, Dict, Any

# Simulated daily raw logs
RAW_WORK_LOGS = """
- Spent 4 hours fixing HANA connection timeouts on subaccount 904. Replaced connection pool settings.
- Wrote the initial draft of the prompt token compression utility. Reduced prompt size by ~52%.
- Aligned deliverables with the platform infrastructure lead for the upcoming cloud migration milestone.
- Ran team sync on sprint velocity. Two tickets blocked by firewall credentials.
"""

def extract_meaningful_signals(raw_text: str) -> List[str]:
    """Filters routine admin noise and extracts core engineering achievements."""
    lines = [line.strip("- ").strip() for line in raw_text.strip().split("\n") if line.strip()]
    signals = []
    
    # Filter routine syncs; retain optimization, architecture, and resolution tasks
    for line in lines:
        if any(keyword in line.lower() for keyword in ["fixed", "wrote", "reduced", "migrat", "architect"]):
            signals.append(line)
            
    return signals

def synthesize_career_digest(signals: List[str]) -> Dict[str, Any]:
    """Transforms filtered signals into executive achievement entries."""
    records = []
    
    for signal in signals:
        if "reduced prompt size" in signal.lower():
            records.append({
                "initiative": "LLM Ingress Optimization",
                "category": "FinOps / AI Architecture",
                "accomplishment": "Engineered automated prompt minification script, slashing payload token footprint by 52% to lower runtime API consumption.",
                "verified_metric": "52% token footprint reduction"
            })
        elif "hana connection" in signal.lower():
            records.append({
                "initiative": "Database Tier Resilience",
                "category": "Enterprise Architecture",
                "accomplishment": "Remediated connection exhaustion on production HANA instances by reconfiguring connection pool parameters and timeout thresholds.",
                "verified_metric": "Resolved timeout failures"
            })
            
    return {
        "agent_status": "COMPLETED",
        "processed_signals_count": len(signals),
        "executive_achievements": records
    }

if __name__ == "__main__":
    print("🚀 Running Career Intel Digest Agent...")
    extracted = extract_meaningful_signals(RAW_WORK_LOGS)
    print(f"Extracted {len(extracted)} high-impact signals from raw log.")
    
    digest = synthesize_career_digest(extracted)
    print("\n" + json.dumps(digest, indent=2))
