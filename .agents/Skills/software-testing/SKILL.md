> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Software Testing Skill
## Critical Workbook Rule
Before test design/reporting, inspect every applicable file under `/templates/Test Documents`: sheet names, columns/fields, formulas/validation, and embedded result/report sheets. Preserve structure.

**If the Functional Testing workbook already contains execution-result/report sheet(s), populate those sheets. Do NOT create a separate Functional Test Report/Test Completion document unless the approved template explicitly requires one.**

## A. Static Testing
Use applicable Checklists: `Artifact → Review → Finding/Defect → Confirm → Fix → Re-review → Exit Criteria`.
## B. Test Analysis
Identify Test Basis (requirements, BRs, UCs, states, design, code, risks) and Test Conditions; trace basis → condition.
## C. Test Design
Use applicable Equivalence Partitioning, Boundary Value Analysis, Use Case Testing, State Transition Testing, Decision Table Testing, Experience-Based/Exploratory Testing. Structural coverage may include Statement, Branch, Condition and Basis Path. Never invent thresholds.
## D. Approved Test Workbooks
Inspect and use actual structures of applicable existing templates, including:
- `Sample_Test_Design.xls`
- `Sample_Test_Cases.xlsx`
- `Template_Unit Test Case.xls`
- `Template_Integration Test Case.xls`
- `Template_Defect_log.xls`
- `Log_Report Test.xlsx`

Do not infer exact purpose solely from filename; inspect workbook/sheets first.
## E. Test Data
Use CSV when required by the approved data-driven testing convention. Never expose production secrets/sensitive data.
## F. Automation
Create applicable Unit, Data-Driven, Keyword-Driven, UI/API and Performance automation; trace automation to approved test basis/cases.
## G. Execution
Execute applicable Unit, Integration, System and Acceptance tests. System testing may include Functional, Performance, Load/Stress, Security and other approved quality tests. Write actual results/status into the exact approved workbook sheet/fields.
## H. Defects
Use approved Defect Log. Link failed test → defect → test basis; confirm → fix → retest → regression as needed.
## I. Reporting
Use report/result sheets already embedded in approved testing workbooks when present. Use `Log_Report Test.xlsx` only according to its inspected approved purpose. Do not create duplicate standalone reports.
## Gate
Submit completed template-based test artifacts to QA/Test Lead/authorized roles; STOP until exit criteria and approval are satisfied.
