# Traceability and Consistency Rules

## 1. Purpose
These rules govern bidirectional traceability and consistency across the complete software lifecycle.

## 2. Mandatory Traceability Chain
Maintain traceability, where applicable, across:

Business Objective / Business Rule / Business Process
→ User Requirement
→ Software Requirement
→ Use Case
→ Analysis Model
→ Architecture / Detailed Design
→ Database Design
→ Source Code
→ Test Case
→ Release Artifact

Not every relationship is one-to-one. All missing or unjustified links MUST be reported.

## 3. Traceability Identifiers
Approved identifiers MUST remain stable. Never silently renumber baselined items.

Typical IDs:
- BO-xx: Business Objective
- BR-xx: Business Rule
- UR-xx: User Requirement
- FR-xx: Functional Requirement
- UC-xx: Use Case
- AC-xx: Analysis Class
- DC-xx: Design Class
- DB-xx: Database element or design item when project convention requires it
- TC-xx: Test Case
- DEF-xx: Defect

## 4. Traceability Matrix
The project SHOULD maintain a Requirements Traceability Matrix (RTM).

Minimum useful columns:
| Upstream Source | UR | SR/FR/NFR | UC | Analysis | Design | DB | Code | Test | Status |

The Agent MUST update the RTM whenever an approved artifact changes.

## 5. Forward Traceability
For each approved upstream requirement, verify that necessary downstream realization exists.

Examples:
- BR → relevant UR/FR
- FR → UC
- UC → analysis realization
- Analysis class → design class/component
- Design → code
- Requirement → test coverage

## 6. Backward Traceability
For each downstream artifact, verify that it has a valid upstream reason.

Examples:
- A design class must map to analysis/design responsibility or approved technical rationale.
- A database table/field must support approved data/functional requirements or technical needs.
- A code feature must trace to approved design/requirement.
- A test case must trace to a requirement, use case, business rule, risk, code structure, or approved quality objective.

Unsupported downstream artifacts MUST be flagged as possible scope creep or over-design.

## 7. Consistency Checks
Check at minimum:
- Business Requirements ↔ Business Processes
- Business Rules ↔ Business Processes
- Business Processes ↔ User Requirements
- User Requirements ↔ Software Requirements
- Software Requirements ↔ Use Cases
- Use Case Description ↔ Activity Diagram
- Use Case ↔ BCE/VOPC
- VOPC ↔ Analysis Sequence Diagram
- State-dependent requirements ↔ State Machine
- Analysis Model ↔ Architecture/Design
- Software Requirements ↔ Database
- Design ↔ Code
- Requirements/Design/Code ↔ Tests

## 8. Change Impact Analysis
When a baselined artifact changes:
1. Identify changed IDs.
2. Traverse upstream and downstream links.
3. List impacted artifacts.
4. Classify impact: must change / review required / no impact with rationale.
5. Obtain required approval.
6. Update artifacts.
7. Re-run consistency checks.
8. Update RTM and baseline status.

## 9. Orphan Detection
Report:
- Requirements with no source.
- Requirements with no realization.
- Use Cases with no related requirement.
- Analysis/design elements with no justification.
- Code with no approved source.
- Requirements with no tests.
- Tests with no traceable test basis.

## 10. Human Verification Gate
Traceability findings MUST be presented to the responsible project role before affected baselines are approved or changed. Significant gaps MUST NOT be silently repaired.
