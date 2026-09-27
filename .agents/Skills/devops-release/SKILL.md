> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# DevOps and Release Skill
## Template Handling
Inspect approved CI/CD, release-readiness, deployment and release-note templates. Avoid parallel release documents. If a required template is absent, report `TEMPLATE MISSING` before adopting a new format.
## CI
1. Inspect repository/build conventions.
2. Restore/install → Build → Static Analysis → Unit Tests → configured Integration/Automation → Reports → versioned Package.
3. Record source revision and build identity.
## CD/Release
1. Select approved release candidate.
2. Apply secure environment configuration.
3. Review DB migrations.
4. Deploy to authorized environment.
5. Run smoke/verification tests.
6. Evaluate release criteria and obtain production approval.
7. Release, monitor and rollback/recover when required.
## Release Traceability
Populate approved release artifact with applicable requirement/change IDs, defect/fix IDs, commit/tag, build/package ID, migration version, test evidence, static-analysis/security evidence, known issues and approval.
## Gate
After successful authorized release, establish/update Release Baseline. STOP if criteria are unmet unless an authorized exception exists.
