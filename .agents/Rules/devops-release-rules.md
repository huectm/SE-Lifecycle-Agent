# DevOps, CI/CD and Release Rules

## 1. Purpose
These rules govern build, CI/CD, packaging, deployment, configuration, and release.

## 2. Source Control
Project source and configuration SHOULD be version controlled. Generated secrets, build outputs, local IDE files, and sensitive configuration MUST be excluded as appropriate.

## 3. Branching and Change Control
Use the project-approved branching and pull/merge request strategy. Do not invent mandatory branch policies when none are defined.

## 4. CI Pipeline
CI SHOULD automate applicable activities such as:
- dependency restore;
- build/compile;
- static analysis;
- unit tests;
- integration tests where feasible;
- test/coverage reporting;
- artifact packaging.

Pipeline failures MUST NOT be silently ignored.

## 5. CD Pipeline
Deployment automation SHOULD use environment-specific configuration and approved release gates.

Do not embed environment secrets in pipeline files.

## 6. Environments
Distinguish environments such as Development, Test, Staging, and Production where applicable.

Configuration differences MUST be explicit and controlled.

## 7. Build Artifacts
Release artifacts MUST be reproducible and versioned where practical.

Record source revision/commit, build version, and relevant dependency/configuration metadata.

## 8. Database Migration
Database changes MUST use controlled migration procedures with compatibility, backup/rollback, and data-impact considerations.

## 9. Release Readiness
Before release verify, where applicable:
- approved requirements/design baseline;
- required tests passed;
- static-analysis findings reviewed;
- critical defects resolved/accepted;
- security checks completed;
- deployment configuration verified;
- database migration reviewed;
- release notes prepared;
- rollback/recovery approach defined.

## 10. Release Notes
Release notes SHOULD identify:
- version;
- included features/fixes;
- known issues;
- migration/configuration notes;
- deployment considerations.

## 11. Rollback
Production deployment SHOULD have an approved rollback or recovery strategy appropriate to project risk.

## 12. Observability
Where required, deployment SHOULD include appropriate logging, monitoring, health checks, and alerting.

## 13. Credentials
Use environment/CI secret stores or approved secret-management systems. Never commit credentials.

## 14. Approval Gate
Production release MUST follow project governance and authorized release approval.
