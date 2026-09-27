> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Implementation Skill
## Template/Scaffold Handling
Inspect and reuse approved repository/project scaffolds, coding conventions and file templates where present.
## Workflow
1. Confirm implementation scope and requirement/design IDs.
2. Inspect repository and approved scaffolds.
3. Implement according to approved architecture/detailed design and technology choices.
4. Apply specified validation, authorization, error handling and logging; never embed secrets.
5. Create/update unit tests.
6. Build frequently and run relevant tests.
7. Invoke `static-code-analysis` for reviewable increments.
8. Verify `Requirements ↔ Design ↔ Code`.
9. If design must change, trigger change/impact analysis rather than silently diverging.
10. Update traceability and submit code for review.
## Gate
Code increment is complete only after required build/test/static-analysis/code-review criteria are met; STOP when approval is required.
