> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Use Case Modeling Skill
## Workflow
1. Inspect approved Use Case sections/templates.
2. Read approved UR, FR, BR, TO-BE process and prototypes.
3. Identify Actors and actor goals; classify Primary/Secondary where appropriate.
4. Derive Use Cases and stable IDs according to project convention.
5. Verify `UR/FR ↔ UC` coverage.
6. Use UML Association, `<<include>>`, `<<extend>>`, Generalization correctly.
7. Create General and, where needed, decomposed Use Case diagrams.
8. Populate Use Case descriptions using the exact approved fields/order.
9. For complex UCs create UML Activity Diagrams with swimlanes, normally Actor and System.
10. Reference prototypes where needed.
11. Verify `Diagram ↔ Description ↔ Activity ↔ Prototype ↔ Requirements`.
12. Insert/reference outputs in the approved master specification, update RTM and apply checklist.
## Gate
Submit to appropriate Business/System Analyst, Product Owner and QA/Test roles; STOP until required approval.
