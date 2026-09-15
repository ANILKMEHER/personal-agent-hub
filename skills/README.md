# Product Management System Skills for LLMs 🧠

A modular library of deterministic Product Management (TPM/PM) skills formatted for direct ingestion into **Claude Projects**, **Gemini Gems**, or **Custom System Prompts**.

---

## 🧭 Available Skills

| Skill File | Core Competency | Target Deliverable |
| :--- | :--- | :--- |
| **[`prd-spec-generator.md`](./prd-spec-generator.md)** | Technical PRD Drafting | Complete Product Requirements Document with non-functional constraints |
| **[`user-story-acceptance-spec.md`](./user-story-acceptance-spec.md)** | Backlog Structuring | INVEST-compliant user stories with Gherkin (Given-When-Then) criteria |
| **[`rice-prioritisation-engine.md`](./rice-prioritisation-engine.md)** | Quantitative Roadmapping | RICE scoring matrix with sensitivity analysis |
| **[`root-cause-discovery-5whys.md`](./root-cause-discovery-5whys.md)** | Discovery & Discovery Framing | Problem-statement canvas isolating symptoms from core user friction |

---

## 🚀 How to Load into Claude or Gemini

### For Claude (Projects / Artifacts)
1. Navigate to **Claude.ai** ➔ **Projects**.
2. Open or create your project (e.g., *Product Management Copilot*).
3. Under **Project Knowledge**, upload or paste the contents of any `.md` file in this folder.
4. Set the project instructions to: *"Refer to the loaded PM skill files to structure your responses deterministically."*

### For Gemini (Custom Gems)
1. Open **Gemini** ➔ Click **Gem Manager** ➔ **New Gem**.
2. Name the Gem according to the skill (e.g., *TPM Spec Writer*).
3. Copy the full markdown text from the desired skill file into the **Instructions** box.
4. Save and launch.
