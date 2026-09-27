> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Static Code Analysis Skill
## Template Handling
Inspect approved static-analysis/report and defect templates. If a report area already exists in another approved artifact, populate it; do not create a duplicate.
## Workflow
1. Identify repository, branch/commit/build.
2. Build/compile as required.
3. Run approved analyzer (e.g. SonarQube).
4. Collect supported findings such as Bugs, Vulnerabilities, Security Hotspots and Code Smells.
5. Review/triage findings; tool findings are not automatically confirmed defects.
6. Record confirmed issues using the approved defect/report structure.
7. Developer confirms/fixes accepted defects.
8. Rebuild and re-scan; compare results.
9. Evaluate project-approved Quality Gate; record unresolved findings/accepted risks.
## Security Hotspots
Require human security review; a hotspot is not automatically a vulnerability.
## Gate
If required Quality Gate criteria are not met, STOP progression unless an authorized exception/risk acceptance exists.
