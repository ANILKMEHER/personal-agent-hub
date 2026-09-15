# Personal Agent Hub 🕹️

A modular collection of autonomous, task-specific personal AI agents built on deterministic prompting, tool-use protocols, and structured memory layers.

---

## 🧭 Active Agent Modules

| Agent Module | Primary Capability | Architecture Pattern | Status |
| :--- | :--- | :--- | :--- |
| **[Career Intel & Sync Agent](./agents/career-intel-agent/)** | Parses raw operational notes & git diffs to generate executive achievement logs. | Map-Reduce Extraction + Structured Synthesis | Active |

---

## 🛠️ Architecture Principles
* **Local-First & Private:** Personal operational data remains local; external API calls transmit only minified, scrubbed context payloads.
* **Deterministic Outputs:** Output structures follow immutable schemas (JSON or strict Markdown tables) rather than open conversational text.
* **Human-in-the-Loop:** Agents prepare drafts, summaries, and action plans; humans authorize external commits and distributions.
