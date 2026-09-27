> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Business Process Modeling Skill
## Workflow
1. Inspect approved BPMN/process template or master-document section.
2. Define process scope, trigger, outcome, participants, Process Owner and evidence.
3. Discover AS-IS activities, decisions, handoffs, data, systems, exceptions and rules.
4. Model AS-IS using BPMN.
5. Identify evidence-supported pain points/opportunities.
6. Derive/propose TO-BE from approved objectives, scope, Business Rules and decisions.
7. Model TO-BE using BPMN.
8. Verify `Objectives ↔ Rules ↔ AS-IS ↔ TO-BE`.
9. Identify process-derived user needs/candidate system responsibilities without silently approving FRs.
10. Insert/reference diagrams in the approved specification and update traceability.
11. Apply applicable checklist.
## Output
Editable `.drawio` unless project policy specifies otherwise. Do not substitute UML Activity notation for BPMN.
## Gate
Submit to BA + Domain Expert/Process Owner + Product Owner/authorized stakeholder; STOP when approval is required.
