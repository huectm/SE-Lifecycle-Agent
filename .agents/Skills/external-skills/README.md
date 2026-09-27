# Supporting External Skills Directory (`.agents/Skills/external-skills`)

**Status:** Tier 2 Supporting Engineering Skills  
**Governance:** Governed by `AGENTS.md`, `.agents/Rules/*.md`, and `.agents/Skills/<lifecycle-skill>/SKILL.md`

---

## 1. Operating Principle: Project-First, External-Second

Skills in this directory are **tactical execution helpers** (imported from `mattpocock/skills`). They are NOT project lifecycle governors.

The Agent and project team MUST follow the strict execution precedence:
1. **Primary Authority:** Always apply the project's own Rules (`.agents/Rules/*.md`) and Tier 1 Project Lifecycle Skills (`.agents/Skills/<skill>/SKILL.md`) first.
2. **Conditional Invocation:** Apply skills in this directory **ONLY WHEN NEEDED** ("Sau đó nếu cần") to accelerate a specific sub-task (e.g., TDD cycle, deep interview, bug diagnosis, refactoring).
3. **Template Supremacy:** All outputs must be formatted and saved into the project-approved templates in `/templates/` (e.g., Master Specification `.docx`, RTM `.xlsx`, Defect Log `.xls`). Never replace project templates with external skill formats.
4. **Gate Supremacy:** External skills cannot bypass, weaken, or auto-complete any Human Verification Gate or remove the mandatory STOP condition.
5. **No Invented Requirements:** External skills cannot unilaterally alter scope, inject requirements, or modify baselined artifacts.

---

## 2. Mapping to Project Lifecycle Activities

| Lifecycle Phase / Governing Skill (Tier 1) | Supporting External Skills (Tier 2) | Typical Tactical Use Case |
|---|---|---|
| `requirements-engineering` | `research`, `grill-me`, `grill-with-docs`, `to-questionnaire`, `to-spec`, `writing-for-agents` | Elicitation interview, deep document extraction, questionnaire formatting, structured requirement drafting |
| `business-process-modeling` | `grilling`, `wayfinder` | Probing process edge-cases, discovering branching logic and swimlane boundaries |
| `usecase-modeling` | `prototype`, `to-spec` | UI mockup validation for complex flows, detailing actor interaction sequences |
| `analysis-modeling` | `domain-modeling` | Domain entity discovery, responsibility allocation, conceptual boundaries |
| `software-design` | `codebase-design`, `improve-codebase-architecture` | Component boundary analysis, architectural pattern trade-off assessment |
| `database-design` | `domain-modeling` | Data relationship modeling and normalization support |
| `implementation` | `implement`, `implement-spec`, `tdd`, `loop-me` | TDD red-green-refactor micro-cycles, modular implementation against spec |
| `static-code-analysis` | `code-review`, `setup-pre-commit` | Static heuristic review, pre-commit quality check, linter configuration |
| `software-testing` | `diagnosing-bugs`, `triage`, `wait-what` | Bug root-cause diagnosis, defect reproduction, test scenario triage |
| `traceability-consistency` | `to-tickets` | Decomposing verified requirements into traceable implementation units |
| `devops-release` | `pr`, `git-guardrails-claude-code`, `claude-handoff`, `handoff` | Pull request preparation, commit hygiene, session handoff documentation |

---

## 3. Skill Inventory & Provenance

All skills in this directory are tracked in `skills-lock.json`.
