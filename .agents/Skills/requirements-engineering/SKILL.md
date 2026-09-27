> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Requirements Engineering Skill
## Role
Orchestrator for Requirements Engineering; delegate BPMN and Use Case details to their specialized Skills.
## Workflow
1. Read AGENTS.md and Requirements/Traceability/Testing/Security Rules.
2. Inspect the approved Requirements–Analysis–Design master template and determine its Requirements sections.
3. Inspect applicable Checklists and authoritative sources.
4. Populate, only in the approved structure: Background; Problem/Opportunity; Business Objectives; Success Measures where approved; Vision; Scope/Exclusions/Major Features; Risks; Assumptions/Dependencies; Business Rules and references.
5. Invoke `business-process-modeling` for AS-IS → problems/opportunities → TO-BE → BPMN.
6. Identify User Classes.
7. Derive User Requirements.
8. Specify Functional Requirements, Quality Attributes, Constraints, External Interfaces and Data Requirements.
9. Invoke `usecase-modeling`.
10. Use prototypes for unclear/complex requirements; prototypes must not silently create requirements.
11. Invoke `traceability-consistency`.
12. Apply approved SRS/requirements checklist; record → confirm → fix → re-review.
13. Update the same approved master document; do not create parallel Requirements documents unless explicitly required.
## Gate
Prepare the template-based Requirements Baseline package and STOP before Analysis until approved (unless authorized iterative overlap).
