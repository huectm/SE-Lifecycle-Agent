> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Database Design Skill
## Workflow
1. Inspect approved database-design section/template.
2. Read Data Requirements, BRs, FRs, UCs, analysis Entities and architecture.
3. Identify conceptual entities/relationships; define identifiers, attributes, cardinalities, optionality and integrity rules.
4. Create logical model; normalize appropriately and document justified denormalization.
5. Create physical schema for approved DB technology.
6. Add only justified technical fields/indexes/audit metadata.
7. Address referential integrity, privacy, security, retention, audit and migration implications.
8. Verify `Requirements ↔ Analysis Entities ↔ Design ↔ Database`.
9. Populate/reference outputs in the approved template; update RTM and apply checklist.
## Gate
Submit to Database Designer + Architect/Technical Lead + Security/Compliance where applicable; STOP until approval.
