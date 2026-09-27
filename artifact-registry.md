# Artifact Registry

**Version:** 2.0  
**Status:** Project Governance Artifact  
**Purpose:** Define the authoritative mapping between lifecycle activities, Skills, approved Templates, Checklists, generated Artifacts, responsible Roles, and Human Verification/Baseline Gates.

---

# 1. Purpose

This registry tells an AI Agent and project team:

- which Skill governs an activity;
- which approved Template must be inspected and used;
- which Checklist must be applied;
- which Artifact is created or updated;
- where the artifact belongs in the lifecycle;
- who reviews/approves it;
- which Gate controls progression;
- how traceability is maintained.

This registry does NOT replace:

- `AGENTS.md`;
- project Rules;
- project Skills;
- approved Templates;
- approved Checklists;
- approved project baselines.

---

# 2. Governance and Priority

Use the following priority order:

1. `AGENTS.md`
2. Applicable Project Rules (`.agents/Rules/*.md`)
3. Approved project requirements and baselines
4. Stakeholder / authorized project decisions
5. This Artifact Registry (`artifact-registry.md`)
6. Applicable Project Lifecycle Skills (`.agents/Skills/<lifecycle-skill>/SKILL.md`)
7. Approved Templates (`/templates`)
8. Approved Checklists (`/checklists`)
9. Supporting External Skills (`.agents/Skills/external-skills/*/SKILL.md`) — applied ONLY when needed to assist specific execution sub-tasks
10. Approved Examples (`/examples`)
11. Reference books / standards (`/references`, `/standards`)
12. General AI knowledge

### Fundamental Precedence Invariant
The project's own Rules and Lifecycle Skills take absolute precedence over external skills. External skills in `.agents/Skills/external-skills/` are secondary, supporting accelerators. They must strictly operate under governing project skills, conform to approved project templates, and respect all verification gates.

If a conflict is detected between approved project artifacts, the Agent MUST report the inconsistency and follow the applicable governance/verification rule rather than silently selecting one.

---

# 3. Mandatory Template-Driven Rule

Before creating or updating an artifact, the Agent MUST:

1. identify the lifecycle activity;
2. identify the governing Skill;
3. consult this Registry;
4. locate the approved Template;
5. inspect the actual Template structure;
6. inspect the applicable Checklist;
7. read approved upstream artifacts;
8. create/update the artifact using the approved structure;
9. update traceability where applicable;
10. perform consistency checking;
11. submit to the applicable Human Verification/Baseline Gate.

The Agent MUST NOT infer an artifact structure solely from a filename.

---

# 4. Template Preservation Rule

For approved Templates, the Agent MUST preserve, as applicable:

- document sections;
- heading hierarchy;
- tables;
- workbook sheets;
- column names;
- fields;
- formulas;
- validation;
- naming conventions;
- embedded result/report areas.

The Agent MUST NOT add, delete, rename, reorder, or redesign approved structures unless explicitly authorized.

If a Template already contains a section/sheet for a required output, the Agent MUST populate that existing location instead of creating a duplicate artifact.

If a required Template truly does not exist:

`TEMPLATE MISSING – Project approval required.`

The Agent may propose a candidate format but MUST NOT treat it as an approved project Template until authorized.

---

# 5. Approved Template Inventory

## 5.1 Master Requirements–Analysis–Design Specification

Approved Template:

`/templates/Template_Requirements_Analysis_Design_Specification.docx`

This is the primary consolidated engineering specification for:

- Requirements;
- Analysis Models;
- High-Level Design;
- Detailed Design;
- Database Design;
- implementation-related specification sections where present.

The Agent MUST inspect the actual document before editing.

Requirements, Analysis, and Design Skills should populate their corresponding existing sections rather than creating parallel specification documents unless project governance explicitly requires separation.

---

## 5.2 Requirements Traceability Matrix

Approved Template:

`/templates/Requirements_Traceability_Matrix_Simplified.xlsx`

This workbook is the authoritative RTM Template.

Its logical sheets are:

- `RTM`
- `Requirements`
- `Design_Elements`
- `Coverage`
- `README`

The actual workbook structure MUST be inspected before use.

### Main RTM trace

The `RTM` sheet follows:

`Business Rule → User Requirement → Software Requirement (FR/NFR) → Use Case → Design Element → Code Element → Test`

The Agent MUST NOT invent relationships merely to fill every column.

### Requirements catalog

The `Requirements` sheet manages approved:

- Business Rules;
- User Requirements;
- Functional Requirements;
- Non-Functional Requirements.

### Design hierarchy

The `Design_Elements` sheet manages:

`Subsystem → Component → Package → Class → Method`

This hierarchy is maintained separately so the main RTM remains concise.

### Coverage

The `Coverage` sheet supports detection of:

- missing trace;
- orphan requirement;
- missing design realization;
- missing code realization;
- missing test coverage.

A missing/zero trace is a review finding and must be interpreted in context; it is not automatically a defect.

---

## 5.3 Test Document Templates

Current approved Test Documents include:

- `/templates/Test Documents/Log_Report Test.xlsx`
- `/templates/Test Documents/Sample_Test_Cases.xlsx`
- `/templates/Test Documents/Sample_Test_Design.xls`
- `/templates/Test Documents/Template_Defect_log.xls`
- `/templates/Test Documents/Template_Integration Test Case.xls`
- `/templates/Test Documents/Template_Unit Test Case.xls`

Before using any workbook, the Agent MUST inspect:

- sheet names;
- hidden/reference sheets where relevant;
- headers;
- merged cells;
- required fields;
- formulas;
- validation;
- sample rows;
- execution-result areas;
- report/summary sheets.

### Functional Testing Report Rule

If the approved Functional Testing workbook contains an embedded execution-result/report sheet, that sheet is the approved Functional Test result/report.

The Agent MUST NOT generate a separate Functional Test Report when the approved workbook already provides the report location.

---

# 6. Approved Checklist Inventory

Current known approved Checklists:

- `/checklists/d2_Checklist_SRS Review.xls`
- `/checklists/d1_Checklist_GUI Review.xls`
- `/checklists/d4_Checklist_Design Review.xls`
- `/checklists/Code Review CheckList_v1.0.xls`
- `/checklists/Checklist_Test Case Review.xls`
- `/checklists/Checklist_Quality Gate Review.xls`

The Agent MUST inspect the actual checklist before applying it.

The checklist's own items, status fields, scoring, and exit criteria take precedence over generic assumptions.

---

# 7. Lifecycle Artifact Registry

| Lifecycle Activity | Governing Skill (Tier 1) | Supporting External Skill(s) (`.agents/Skills/external-skills`) (Tier 2 - If Needed) | Main Inputs | Approved Template / Artifact Location | Checklist | Main Output | Reviewer / Approver | Gate |
|---|---|---|---|---|---|---|---|---|
| Business Context & Business Requirements | `requirements-engineering` | `research`, `grill-me`, `grill-with-docs`, `to-questionnaire`, `to-spec` | Stakeholder/business sources | Master R-A-D Specification | SRS Review as applicable | Background, problem/opportunity, objectives, scope, risks, BRs | Business Stakeholder, PO, BA | Requirements Gate |
| Business Process Discovery | `business-process-modeling` | `grilling`, `wayfinder` | Business Requirements, BRs, process evidence | Master specification + editable BPMN `.drawio` | No dedicated BPMN checklist currently registered | AS-IS, problems/opportunities, TO-BE, BPMN | BA, Process Owner, PO | Process Verification Gate |
| User Classes | `requirements-engineering` | `grill-me`, `to-spec` | Processes, stakeholders | Master specification | SRS Review | User Class specification | BA, PO | Requirements Gate |
| User Requirements | `requirements-engineering` | `to-spec`, `writing-for-agents` | Business/process/user evidence | Master specification + RTM | `d2_Checklist_SRS Review.xls` | `UR-xx` | BA, PO | Requirements Gate |
| Functional Requirements | `requirements-engineering` | `to-spec`, `writing-for-agents` | URs, processes, BRs | Master specification + RTM | `d2_Checklist_SRS Review.xls` | `FR-xx` | BA/System Analyst, QA | Requirements Gate |
| Non-Functional Requirements | `requirements-engineering` | `research`, `to-spec` | Business goals, quality needs, constraints | Master specification + RTM | `d2_Checklist_SRS Review.xls` | Quality Attribute requirements | BA/System Analyst, Architect, QA | Requirements Gate |
| Constraints | `requirements-engineering` | `to-spec` | Business/technical/regulatory sources | Master specification | SRS Review | Constraints | BA/System Analyst, Architect | Requirements Gate |
| External Interfaces | `requirements-engineering` | `to-spec` | Integration/UI/device/communication needs | Master specification | SRS Review | Interface requirements | System Analyst, Architect | Requirements Gate |
| Data Requirements | `requirements-engineering` | `domain-modeling`, `to-spec` | Business/process requirements | Master specification | SRS Review | Data requirements | System Analyst, DB/Architect | Requirements Gate |
| Prototype | `requirements-engineering` / `usecase-modeling` | `prototype` | Complex/unclear requirements | Approved prototype tool + reference in master specification | `d1_Checklist_GUI Review.xls` | Prototype | Stakeholder/PO, BA/UX | Requirements Gate |
| Use Case Model | `usecase-modeling` | `to-spec` | URs, FRs, TO-BE | Master specification + `.drawio` + RTM | SRS Review as applicable | Actor/Use Case model | System Analyst, PO, QA | Requirements Gate |
| Use Case Description | `usecase-modeling` | `to-spec` | UC, FR, BR | Exact approved section/template | SRS Review | Structured Use Case specification | System Analyst, PO, QA | Requirements Gate |
| Activity Diagram | `usecase-modeling` | `wayfinder` | Complex Use Case | Master specification + `.drawio` | SRS/Design Review as applicable | Actor/System swimlane Activity Diagram | System Analyst, QA | Requirements Gate |
| Requirements Traceability | `traceability-consistency` | `to-tickets` | BR, UR, FR/NFR, UC and downstream artifacts | `Requirements_Traceability_Matrix_Simplified.xlsx` | Traceability/consistency rules | Updated RTM + coverage findings | BA/System Analyst, QA and relevant downstream roles | Cross-cutting Consistency Gate |
| BCE Analysis | `analysis-modeling` | `domain-modeling` | Approved Requirements/UC | Analysis section of master specification | `d4_Checklist_Design Review.xls` as applicable | Boundary/Control/Entity analysis | System Analyst, Architect | Analysis Gate |
| VOPC | `analysis-modeling` | `domain-modeling` | BCE + UC | Master specification + `.drawio` | Design Review | VOPC | System Analyst, Architect | Analysis Gate |
| Analysis Sequence Diagram | `analysis-modeling` | `domain-modeling` | UC, BCE, VOPC | Master specification + `.drawio` | Design Review | Analysis Sequence | System Analyst, Architect | Analysis Gate |
| State Machine Diagram | `analysis-modeling` | `domain-modeling` | State-dependent requirement/entity | Master specification + `.drawio` | Design Review | State Machine | System Analyst, Architect | Analysis Gate |
| High-Level Architecture | `software-design` | `codebase-design`, `improve-codebase-architecture` | Requirements, Analysis, Quality Attributes | Design section + `.drawio` + RTM | `d4_Checklist_Design Review.xls` | Architecture | Architect/Technical Lead | Architecture/Design Gate |
| Subsystem Design | `software-design` | `codebase-design` | Architecture drivers | Master specification + Design_Elements sheet + `.drawio` | Design Review | Subsystems | Architect/Technical Lead | Design Gate |
| Component Design | `software-design` | `codebase-design` | Architecture/subsystems | Master specification + Design_Elements sheet + `.drawio` | Design Review | Components | Architect/Technical Lead | Design Gate |
| Package Design | `software-design` | `codebase-design` | Components/design organization | Master specification + Design_Elements sheet + `.drawio` | Design Review | Packages | Architect/System Designer | Design Gate |
| Analysis-to-Design Mapping | `software-design` | `codebase-design` | BCE/VOPC/analysis sequence + architecture | Master specification + RTM/Design_Elements | Design Review | Mapping specification | Architect/System Designer | Design Gate |
| Design Sequence Diagram | `software-design` | `codebase-design`, `domain-modeling` | UC realization + architecture | Master specification + `.drawio` | Design Review | Design Sequence | Architect/System Designer | Design Gate |
| Detailed Class Design | `software-design` | `codebase-design` | Detailed realization | Master specification + `.drawio` + Design_Elements | Design Review | Classes, operations/methods, class specification | Architect/Technical Lead | Design Gate |
| Database Design | `database-design` | `domain-modeling` | Data Requirements, BRs, entities, architecture | Database section + `.drawio` | Design Review as applicable | Conceptual/logical/physical DB design | DB Designer, Architect | Database/Design Gate |
| Implementation | `implementation` | `implement`, `implement-spec`, `tdd`, `loop-me` | Approved Design Baseline | `/src` / approved repository structure + RTM | `Code Review CheckList_v1.0.xls` | Source code, methods, unit tests | Peer Developer, Technical Lead | Code Review Gate |
| Static Code Analysis | `static-code-analysis` | `code-review`, `setup-pre-commit` | Reviewable code/build | Approved analyzer output + defect/report structures | Code Review as applicable | Findings, fixes, re-scan, Quality Gate evidence | Developer, QA, Security/Lead | Static Analysis Gate |
| Unit Testing | `software-testing` | `tdd`, `diagnosing-bugs` | Unit/code/design basis | `Template_Unit Test Case.xls` | `Checklist_Test Case Review.xls` | Unit Test artifacts/results as template supports | Developer/QA | Test Gate |
| Integration Testing | `software-testing` | `diagnosing-bugs`, `wait-what` | Interface/integration basis | `Template_Integration Test Case.xls` | `Checklist_Test Case Review.xls` | Integration Test artifacts/results | QA/Developer | Test Gate |
| Functional/System Test Design | `software-testing` | `triage` | Requirements, BRs, UCs, states | `Sample_Test_Design.xls` and inspected approved workbook | `Checklist_Test Case Review.xls` | Test Conditions/Design | QA | Test Gate |
| Functional/System Test Cases | `software-testing` | `triage` | Approved Test Design | `Sample_Test_Cases.xlsx` / actual approved Functional workbook | `Checklist_Test Case Review.xls` | Test Cases + execution evidence | QA | Test Gate |
| Functional Test Result/Report | `software-testing` | `wait-what` | Functional execution | Existing embedded result/report sheet in approved Functional workbook | According to workbook/checklist | Functional Test result/report | QA/Test Lead | Test Completion Gate |
| Defect Management | `software-testing` | `diagnosing-bugs`, `triage`, `wait-what` | Review/test failures | `Template_Defect_log.xls` | — | Defect Log | QA + responsible developer | Review/Test Gate |
| Test Log / Report | `software-testing` | `wait-what` | Test execution | `Log_Report Test.xlsx` only according to inspected approved purpose | — | Test log/report | QA/Test Lead | Test Completion Gate |
| Test Data | `software-testing` | — | Test cases | CSV when project convention requires | — | Test data | QA | Test Gate |
| Performance Testing | `software-testing` | `wait-what` | Performance requirements | Existing testing workbook if supported; otherwise `TEMPLATE MISSING` | No dedicated checklist currently registered | Performance design/results | QA/Performance role | Test Completion Gate |
| CI/CD | `devops-release` | `setup-pre-commit`, `pr` | Approved code/test/static evidence | Repository pipeline configuration | — | CI/CD pipeline | DevOps/Technical Lead | Pipeline Gate |
| Release Readiness | `devops-release` | `claude-handoff`, `handoff` | Release candidate + evidence | Existing approved release artifact if identified; otherwise `TEMPLATE MISSING` | `Checklist_Quality Gate Review.xls` as applicable | Release readiness evidence | DevOps, QA, PO/Approver | Release Gate |
| Release Notes | `devops-release` | `writing-beats`, `writing-fragments` | Approved release content | Existing project standard if identified; otherwise `TEMPLATE MISSING` | — | Release Notes | DevOps/PO | Release Gate |
| Release Baseline | `devops-release` | `pr`, `git-guardrails-claude-code` | Approved successful release | Project versioning/release convention + RTM | — | Versioned Release Baseline | Authorized Approver | Release Complete |

---

# 7.1 Two-Tier Skill Execution Model & External Skills Usage Rules

To ensure strict engineering governance and avoid uncontrolled divergence:

### Rule 1: Project Lifecycle Skills (Tier 1) Always Govern
Every lifecycle activity is initiated, orchestrated, and closed by its designated **Governing Skill** (`.agents/Skills/<lifecycle-skill>/SKILL.md`). The governing skill is the sole authority responsible for:
- verifying entry criteria;
- enforcing applicable project Rules in `.agents/Rules/`;
- enforcing approved project Templates in `/templates/`;
- enforcing project Checklists in `/checklists/`;
- maintaining RTM traceability;
- enforcing Human Verification Gates (STOP condition).

### Rule 2: External Skills (Tier 2) Are Applied Only When Needed
External skills in `.agents/Skills/external-skills/` are **tactical execution helpers**. They are invoked **ONLY IF NEEDED** ("Sau đó nếu cần") to perform a focused technical task (e.g., executing a TDD loop, diagnosing an elusive bug, conducting an interactive interview via `grill-me`).

### Rule 3: Output Consolidation into Approved Templates
External skills frequently have their own internal conventions or output suggestions. The Agent MUST NOT use external skill output formats to replace or bypass project-approved templates. All intermediate or raw results generated with external skill assistance MUST be formatted and consolidated directly into the designated project template (e.g. Master Specification `.docx`, RTM `.xlsx`, or Test Document `.xls`).

### Rule 4: Verification Gates Cannot Be Skipped
An external skill MUST NOT conclude an activity on its own. After external execution completes, control returns to the Tier 1 Governing Skill to perform template validation, run checklists, update the RTM, and STOP at the designated Human Verification Gate for authorized sign-off.

---

# 8. RTM Update Responsibilities

The RTM is cross-cutting and must evolve with the project.

## Requirements Engineering

Update:

- Business Rules;
- User Requirements;
- Functional Requirements;
- Non-Functional Requirements;
- Use Case references when available.

## Analysis Modeling

Check consistency between:

`Use Case ↔ Activity ↔ BCE ↔ VOPC ↔ Analysis Sequence ↔ State Machine`

Analysis artifacts normally remain consistency links rather than separate main RTM columns unless the approved Template changes.

## Software Design

Update the `Design_Elements` catalog and RTM with relevant:

- Subsystems;
- Components;
- Packages;
- Classes;
- Methods.

## Database Design

Verify:

`Requirements / BRs ↔ Data Requirements ↔ Entities / DB constraints`

Database consistency may be reported even when database elements are not represented as separate main RTM columns.

## Implementation

Update Code Element trace from approved Design Elements to implemented classes/methods/modules.

## Software Testing

Update Test trace from requirements/UCs/design/code to:

- Test Conditions;
- Test Cases;
- automated tests where applicable;
- execution evidence.

## DevOps & Release

Verify that released content is traceable to approved requirements, design/code revisions, fixes, and test/static-analysis evidence.

---

# 9. Traceability Rules

The authoritative primary lifecycle trace is:

`Business Rule → User Requirement → Software Requirement (FR/NFR) → Use Case → Design Element → Code Element → Test`

Not every row must contain every element.

The Agent MUST NOT create artificial links simply to make a row complete.

Multiple rows may be used when:

- one requirement maps to several Use Cases;
- one requirement maps to several Design Elements;
- one Design Element maps to several Code Elements;
- one requirement is verified by several Tests.

---

# 10. Forward and Backward Traceability

## Forward

Check:

`Requirement → Use Case → Design → Code → Test`

Detect:

- requirement without realization;
- requirement without implementation;
- requirement without verification;
- broken lifecycle links.

## Backward

Check:

`Test → Code → Design → Requirement / Business Rule`

Detect:

- test without test basis;
- code without approved design/requirement;
- design without upstream justification;
- Use Case without approved requirement.

---

# 11. Consistency Checking

Traceability must include semantic consistency checks.

Required checks include:

- Business Requirement / Business Rule ↔ User Requirement
- User Requirement ↔ Software Requirement
- Software Requirement ↔ Use Case
- Use Case ↔ Activity
- Use Case ↔ BCE/VOPC
- BCE/VOPC ↔ Analysis Sequence
- State-dependent requirements ↔ State Machine
- Analysis ↔ Design
- Requirements ↔ Architecture
- Design ↔ Database where applicable
- Design ↔ Code
- Requirements ↔ Tests
- Code changes ↔ impacted tests
- Release content ↔ approved/tested artifacts

A similar name is not sufficient evidence of a valid trace.

---

# 12. Change Impact Analysis

When an approved artifact changes:

1. identify the changed ID;
2. locate its RTM links;
3. identify upstream dependencies;
4. identify downstream dependencies;
5. identify affected artifacts;
6. classify impact;
7. assign responsible role;
8. update affected artifacts only after required authorization;
9. update RTM;
10. re-run affected reviews/checklists/tests.

Impact classification:

- `Must Change`
- `Review Required`
- `No Impact`

`No Impact` requires rationale.

---

# 13. Orphan and Broken-Trace Detection

Report:

## Orphan Requirement

Approved requirement with no expected downstream realization or verification.

## Orphan Design Element

Design element with no valid upstream justification.

## Orphan Code

Code behavior with no approved requirement/design justification.

## Orphan Test

Test with no valid test basis.

## Broken Trace

Expected lifecycle relationship is missing between otherwise related artifacts.

Do not silently delete or repair these artifacts.

---

# 14. Human Verification and Baseline Gates

AI-generated or AI-inferred trace links are subject to Human Verification when project governance requires it.

At each lifecycle gate:

1. update affected trace links;
2. run coverage/orphan checks;
3. run semantic consistency checks;
4. report unresolved findings;
5. obtain authorized review/approval;
6. proceed only when gate conditions are satisfied.

If a significant inconsistency affects a baseline:

`Report → Impact Analysis → Responsible Role Review → Resolution → RTM Update → Recheck`

**STOP propagation to affected downstream work until authorized resolution.**

---

# 15. Current Template Gaps to Verify

The following are not automatically assumed to be missing. The Agent must first inspect existing Templates/workbooks.

Potential gaps currently include:

1. dedicated BPMN/process checklist/template, if required beyond the master document;
2. dedicated Static Code Analysis summary/report, if existing defect/report structures are insufficient;
3. Performance Test template, if not already included in an approved testing workbook;
4. Release Readiness template/checklist;
5. Release Notes format;
6. deployment/rollback record if project governance requires it.

The RTM is **NOT missing**. Its approved Template is:

`/templates/Requirements_Traceability_Matrix_Simplified.xlsx`

---

# 16. Recommended Artifact Storage

```text
/artifacts/
├── requirements/
│   ├── business-processes/
│   ├── prototypes/
│   ├── use-cases/
│   └── traceability/
├── analysis/
├── design/
├── database/
├── implementation/
├── testing/
│   ├── test-design/
│   ├── test-cases/
│   ├── test-data/
│   ├── defects/
│   ├── automation/
│   └── results/
└── release/
```

The master specification may remain the consolidated lifecycle document while editable diagrams, source files, workbooks, automation projects, and supporting evidence are stored in their corresponding artifact folders.

---

# 17. Registry Maintenance

This Registry must be updated when:

- an approved Template is added/replaced;
- a Template changes sheet/section structure;
- a Checklist is added/replaced;
- an Artifact type is added;
- a Skill responsibility changes;
- a Gate changes;
- project governance changes.

A Template change does not automatically require rewriting all Skills.

The Agent should first determine whether the change can be handled by:

1. updating this Registry;
2. updating the affected Template mapping;
3. updating only the directly affected Skill.

---

# 18. Current Governance Architecture

The project governance architecture is:

`AGENTS.md`

→ `Rules`

→ `Skills`

→ `Artifact Registry`

→ `Templates / Checklists`

→ `Project Artifacts`

→ `Traceability & Consistency`

→ `Human Verification / Baseline Gates`

The Artifact Registry therefore acts as the operational bridge between project workflow definitions and the actual files used to produce software engineering artifacts.
