# Platform Release Note & Migration Impact Agent 📦

An automated infrastructure governance agent that ingests vendor release notes, service pack documentation, and API deprecation notices, comparing them against an active landscape inventory to generate migration risk scores and readiness briefs.

---

## 🏗️ Agent Pipeline Architecture
[ Vendor Release Notes / API Changelog ]
│
▼
[ Ingress Entity Extractor: Features, Removals, Schema Changes ]
│
▼
[ Inventory Cross-Referencing Engine: Active Landscape Match ]
│
▼
[ Migration Impact & Risk Evaluation Brief (Markdown / JSON) ]


---

## 📐 Impact Classification Rubric

| Impact Category | Operational Trigger | Required Remediation Window |
| :--- | :--- | :--- |
| **Breaking / Deprecated** | Endpoint removed, TLS protocol sunset, schema incompatible | Pre-upgrade mandatory refactor |
| **Functional Alteration** | Default parameter shift, rate-limit adjustment | Regression test coverage required |
| **Non-Breaking Extension** | Additive endpoints, performance improvements | Standard release cadence |

---

## 📝 Deterministic Migration Impact Prompt Blueprint

```text
[SYSTEM CONTEXT]: You are an Enterprise Platform Migration Strategist. Analyze the provided vendor changelog against the active system inventory to generate a migration impact assessment.

[ACTIVE SYSTEM INVENTORY]:
"${ACTIVE_INVENTORY_METADATA}"

[RAW VENDOR CHANGELOG]:
"${RAW_RELEASE_NOTES}"

[STRICT REASONING PROTOCOL]:
1. Identify all breaking changes, sunsets, and mandatory upgrades.
2. Cross-reference identified changes against active interfaces in the landscape inventory.
3. Compute a composite risk score (0.0 to 1.0).
4. Output structured JSON with zero introductory remarks.

[OUTPUT SCHEMA]:
{
  "release_version": "String",
  "composite_risk_rating": "CRITICAL | MODERATE | LOW",
  "migration_score": 0.00,
  "impacted_active_systems": [
    {
      "component_name": "String",
      "nature_of_impact": "BREAKING | DEPRECATED | ENHANCEMENT",
      "required_engineering_action": "String"
    }
  ],
  "pre_upgrade_testing_focus": ["Array of specific testing paths"]
}
