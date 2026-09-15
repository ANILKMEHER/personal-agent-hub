# Personal Agent Hub 🕹️

A modular collection of autonomous, task-specific personal AI agents built on deterministic prompting, tool-use protocols, and structured memory layers.

---

## 🧭 Active Agent Modules

| Agent Module | Primary Capability | Architecture Pattern | Status |
| :--- | :--- | :--- | :--- |
| **[Career Intel & Sync Agent](./agents/career-intel-agent/)** | Parses raw operational notes & git diffs to generate executive achievement logs. | Map-Reduce Extraction + Structured Synthesis | Active |
| **[Enterprise Incident & RCA Agent](./agents/enterprise-incident-rca-agent/)** | Ingests production crash traces, classifies root causes, and drafts deterministic RCA briefs. | Trace Sanitisation + Pattern Classification | Active |
| **[Release & Migration Impact Agent](./agents/release-migration-impact-agent/)** | Parses vendor release notes against landscape inventories to identify breaking architectural changes. | Dependency Matching + Risk Scoring | Active |
---

## 🛠️ Architecture Principles
* **Local-First & Private:** Personal operational data remains local; external API calls transmit only minified, scrubbed context payloads.
* **Deterministic Outputs:** Output structures follow immutable schemas (JSON or strict Markdown tables) rather than open conversational text.
* **Human-in-the-Loop:** Agents prepare drafts, summaries, and action plans; humans authorize external commits and distributions.

---

## 🧠 PM & TPM Skill Library (Claude / Gemini Ready)

Downloadable, deterministic skill definitions to paste directly into **Claude Projects** or **Gemini Gems**:

* **[`prd-spec-generator.md`](./skills/prd-spec-generator.md)**: Structured Technical PRD drafting with SLAs and non-functional requirements.
* **[`user-story-acceptance-spec.md`](./skills/user-story-acceptance-spec.md)**: INVEST-compliant user stories with Gherkin scenarios.
* **[`rice-prioritisation-engine.md`](./skills/rice-prioritisation-engine.md)**: Mathematical RICE scoring and roadmapping.
* **[`root-cause-discovery-5whys.md`](./skills/root-cause-discovery-5whys.md)**: 5-Whys discovery framing and problem canvases.
