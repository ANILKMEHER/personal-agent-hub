# Enterprise Incident Triage & RCA Drafter Agent 🚨

An automated operations agent that ingests raw production system dumps, database timeout traces, and system error codes to deterministically classify severity, isolate root causes, and draft enterprise-standard Root Cause Analysis (RCA) briefs.

---

## 🏗️ Agent Pipeline Architecture

[ Raw System Dump / Trace Ingress ]
│
▼
[ Ingress Sanitizer: PII / Secret Masking ]
│
▼
[ Diagnostics Classifier: Signature & Error Matching ]
│
▼
[ RCA Synthesis Engine: Remediation & Timeline Mapping ]
│
▼
[ Validated Enterprise RCA Brief (Markdown / JSON) ]


---

## 📐 Triaging Taxonomy

| Incident Vector | Primary Detection Signature | Default Severity | Target Resolution Path |
| :--- | :--- | :--- | :--- |
| **Memory / Dump Exhaustion** | Out-of-memory dumps, allocation limits breached | P1 - High | Memory parameter tuning, heap inspection |
| **Thread & Lock Contention** | Connection timeouts, thread-pool exhaustion | P2 - Medium | Lock analysis, thread-pool resizing |
| **Gateway / Ingress Drops** | Network socket drops, reverse proxy timeouts | P2 - Medium | Routing table verification, keep-alive adjustment |

---

## 📝 Deterministic RCA Prompt Blueprint

```text
[SYSTEM CONTEXT]: You are an Enterprise Reliability Architect. Parse raw diagnostic traces and produce a deterministic, objective Root Cause Analysis (RCA) conforming strictly to the output schema.

[INCIDENT LOG TRACE]:
"${INGESTED_DIAGNOSTIC_TRACE}"

[STRICT REASONING INSTRUCTIONS]:
1. Identify the primary failure mechanism from the trace signatures.
2. Establish the operational timeline: Initial failure point, cascading impact, and current system state.
3. Formulate immediate containment actions and long-term preventative architectural guardrails.
4. Output strict JSON with zero introductory remarks.

[OUTPUT SCHEMA]:
{
  "incident_classification": {
    "severity": "P1 | P2 | P3",
    "primary_subsystem": "Database | Application Core | Integration Layer",
    "signature_detected": "String"
  },
  "root_cause_summary": "1-2 sentence deterministic explanation",
  "containment_steps": ["Array of immediate technical actions"],
  "preventative_measures": ["Array of architectural remediations"]
}
