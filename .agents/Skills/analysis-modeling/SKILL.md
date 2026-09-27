> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Analysis Modeling Skill
## Entry
Approved Requirements Baseline or explicitly authorized iterative input.
## Workflow
1. Inspect Analysis sections of the approved master specification.
2. Read complete approved Use Case and related requirements/activity/prototype.
3. Identify BCE classes: Boundary, Control, Entity.
4. Populate BCE information only in the approved format.
5. Create VOPC (View of Participating Classes).
6. Create Analysis Sequence Diagram using BCE objects.
7. Model significant alternatives/exceptions where required.
8. Create State Machine Diagram where lifecycle/state-dependent behavior exists.
9. Verify `UC ↔ Activity ↔ BCE ↔ VOPC ↔ Analysis Sequence ↔ State Machine`.
10. Insert/reference outputs in the Analysis sections, update traceability and apply checklist.
## Constraint
Remain technology-independent; do not prematurely introduce final framework/database implementation details.
## Gate
Submit to System Analyst + Architect/Technical Lead + applicable reviewer; STOP until Analysis Baseline approval.
