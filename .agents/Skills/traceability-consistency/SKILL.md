# Traceability and Consistency Skill

> **Skill Set Version:** 3.0 — Template-Driven  
> **Skill Type:** Cross-cutting lifecycle skill  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`

---

## 1. Purpose

Maintain **bidirectional traceability and consistency** across the complete software engineering lifecycle.

The primary traceability chain is:

Business Rule  
→ User Requirement  
→ Software Requirement (FR / NFR)  
→ Use Case  
→ Design Element  
→ Code Element  
→ Test

The Skill shall support both:

- **Forward Traceability:** Requirement → Design → Code → Test
- **Backward Traceability:** Test / Code / Design → Requirement

The Skill shall also support **change impact analysis** whenever an approved artifact changes.

---

## 2. Governing Sources

Before performing traceability or consistency checking, the Agent MUST read:

1. `/AGENTS.md`
2. Applicable files under `.agents/rules/`
3. Approved project baselines and artifacts
4. The approved Requirements Traceability Matrix template
5. Relevant artifact templates
6. Relevant review checklists

Project-approved artifacts and templates take precedence over assumptions or general AI knowledge.

---

# 3. Approved RTM Template

The approved Requirements Traceability Matrix is:

`/templates/Requirements_Traceability_Matrix_Simplified.xlsx`

Before updating the workbook, the Agent MUST inspect its actual structure.

The current workbook contains the following logical sheets:

- `RTM`
- `Requirements`
- `Design_Elements`
- `Coverage`
- `README`

The Agent MUST preserve the approved workbook structure.

The Agent MUST NOT:

- rename sheets;
- remove sheets;
- add new sheets;
- rename columns;
- remove columns;
- change formulas;
- modify validation rules;
- redesign the workbook;

unless explicitly authorized by the responsible project role.

Rows may be added as necessary.

---

# 4. Main Traceability Model

The main `RTM` sheet represents the lifecycle trace:

| Business Rule | User Requirement | Software Requirement (FR / NFR) | Use Case | Design Element | Code Element | Test |
|---|---|---|---|---|---|---|

Each row represents a meaningful traceability path between lifecycle artifacts.

Example:

BR-07  
→ UR-03  
→ FR-06  
→ UC-05  
→ CLS-BookService  
→ CheckAvailability()  
→ TC-05.01

Not every row is required to contain every artifact type.

If an artifact is not applicable to a particular trace path, the corresponding cell MAY remain empty.

The Agent MUST NOT invent an artificial relationship merely to fill every column.

---

# 5. Requirements Catalog

The `Requirements` sheet is the catalog of approved requirements used by the RTM.

It may contain:

- Business Rules (`BR-xx`)
- User Requirements (`UR-xx`)
- Functional Requirements (`FR-xx`)
- Non-Functional Requirements (`NFR-xx` or approved category-specific IDs)

Examples of NFR categories may include:

- Performance
- Security
- Usability
- Reliability
- Availability
- Maintainability

The actual ID convention defined by the project MUST be preserved.

Each requirement should have a stable identifier.

The Agent MUST NOT create a new requirement solely for traceability purposes.

If a required trace cannot be established because the source requirement does not exist, report the issue instead of inventing one.

---

# 6. Design Element Catalog

The `Design_Elements` sheet manages the hierarchy of design elements.

The design hierarchy may include:

Subsystem  
→ Component  
→ Package  
→ Class  
→ Method

Typical element types include:

- Subsystem
- Component
- Package
- Class
- Method

Each design element should have:

- stable ID where applicable;
- element type;
- name;
- parent element;
- responsibility/description;
- source artifact or diagram;
- status.

Example:

Subsystem:

`SS-01 – Borrowing Management`

Component:

`CMP-01 – Borrowing Service`

Package:

`PKG-01 – Services.Borrowing`

Class:

`CLS-01 – BorrowingService`

Method:

`MTH-01 – CheckEligibility()`

The hierarchy is maintained in `Design_Elements`.

The main `RTM` sheet therefore does NOT need separate columns for every level of the design hierarchy.

---

# 7. Traceability Levels

## 7.1 Business Rule Traceability

Verify:

Business Rule  
→ affected User Requirement / Software Requirement / Use Case  
→ affected Design / Code / Test

Business Rules may originate from:

- organizational policy;
- domain rules;
- contractual obligations;
- legal/regulatory requirements;
- approved business procedures.

The Agent MUST preserve the source/reference of Business Rules where available.

---

## 7.2 User Requirement Traceability

Verify:

User Requirement  
→ Software Requirement  
→ Use Case  
→ Design  
→ Code  
→ Test

Every approved User Requirement should be realized by one or more downstream artifacts unless explicitly documented otherwise.

---

## 7.3 Software Requirement Traceability

Verify both Functional and Non-Functional Requirements.

### Functional Requirements

Typical trace:

FR  
→ Use Case  
→ Design Element  
→ Code Element  
→ Functional/System Test

### Non-Functional Requirements

NFRs do not always map directly to one Use Case.

They may trace to:

NFR  
→ Architecture / Component / Class / Configuration  
→ Code / Infrastructure  
→ Quality Test

For example:

PER-01  
→ API Component  
→ Search Service  
→ performance implementation/configuration  
→ Performance Test

SEC-01  
→ Authentication Component  
→ Authorization Service  
→ authorization code  
→ Security Test

The Agent MUST NOT force every NFR to map to a Use Case if the relationship is not meaningful.

---

# 8. Use Case Traceability

Verify:

User Requirement / Functional Requirement  
→ Use Case  
→ Analysis  
→ Design  
→ Code  
→ Test

Use Cases MUST remain consistent with:

- Functional Requirements;
- Business Rules;
- Use Case descriptions;
- Activity Diagrams;
- prototypes where applicable.

A Use Case without an approved upstream requirement must be reported as a potential unsupported function.

---

# 9. Analysis Traceability

For each relevant Use Case, verify consistency across:

Use Case  
→ Activity Diagram  
→ BCE Classes  
→ VOPC  
→ Analysis Sequence Diagram  
→ State Machine Diagram, where applicable

The Agent MUST detect:

- missing BCE participants;
- VOPC classes not supported by the Use Case;
- sequence participants absent from BCE/VOPC;
- missing alternative/exception behavior;
- inconsistent entity states.

Analysis artifacts do not need to appear as separate columns in the main RTM unless the approved template is changed.

They remain part of lifecycle consistency checking.

---

# 10. Design Traceability

Verify:

Requirements / Use Case / Analysis  
→ Architecture  
→ Subsystem  
→ Component  
→ Package  
→ Class  
→ Method

The Agent MUST verify that significant design elements have an upstream justification.

Report design elements that cannot be traced to:

- an approved requirement;
- a Use Case;
- a Quality Attribute;
- a Constraint;
- an approved architecture decision;
- or another authorized technical requirement.

Do NOT automatically delete apparently unsupported design elements.

Report them for review.

---

# 11. Code Traceability

Verify:

Design Element  
→ Code Element

Typical mappings include:

Class Design  
→ Source Class

Operation / Method Design  
→ Implemented Method

Component  
→ Project / Module / Service

Package  
→ Namespace / Folder / Module

The Agent MUST detect significant code elements that:

- are not represented in approved design;
- implement functionality not supported by requirements;
- contradict the approved design.

If implementation requires a design change:

DO NOT silently update the design.

Trigger Change Impact Analysis.

---

# 12. Test Traceability

Verify:

Requirement / Business Rule / Use Case  
→ Test Condition  
→ Test Case  
→ Automated Test where applicable  
→ Test Result

Testing traceability must support determining:

1. Which tests verify a requirement?
2. Which requirement is verified by a test?
3. Which requirements have no tests?
4. Which tests have no valid test basis?

Use the approved testing templates under:

`/templates/Test Documents/`

The Agent MUST inspect the actual workbook structure before using test identifiers or report/result locations.

---

# 13. Forward Traceability Check

Perform forward traceability from approved requirements.

Check:

Business Rule  
→ User Requirement  
→ Software Requirement  
→ Use Case  
→ Design  
→ Code  
→ Test

Detect:

- requirement without realization;
- requirement without design;
- requirement without implementation;
- requirement without verification/test;
- broken intermediate trace.

Report missing links.

Do NOT invent links.

---

# 14. Backward Traceability Check

Perform backward traceability from downstream artifacts.

Check:

Test  
→ Code  
→ Design  
→ Use Case / Requirement  
→ Business Rule where applicable

Detect:

- test without test basis;
- code without approved design/requirement;
- design element without upstream justification;
- Use Case without supporting requirement;
- unnecessary or unauthorized functionality.

---

# 15. Coverage Analysis

Use the `Coverage` sheet in the approved RTM workbook.

Coverage checking should determine whether each approved:

- Business Rule;
- User Requirement;
- Functional Requirement;
- Non-Functional Requirement

has the expected downstream trace.

A zero or missing trace is a **review finding**, not automatically a defect.

The Agent must determine whether:

- the trace is genuinely missing;
- the artifact is not applicable;
- the requirement is intentionally deferred;
- or the RTM has not yet been updated.

---

# 16. Consistency Checking

Traceability alone is not sufficient.

The Agent MUST also check semantic consistency.

Examples:

### Business Requirement ↔ User Requirement

Verify that User Requirements support approved business objectives, processes and rules.

### User Requirement ↔ Software Requirement

Verify that Software Requirements correctly realize User Requirements.

### Software Requirement ↔ Use Case

Verify that Use Cases implement the expected system behavior.

### Use Case ↔ Analysis

Verify:

UC  
↔ Activity  
↔ BCE  
↔ VOPC  
↔ Analysis Sequence  
↔ State Machine

### Analysis ↔ Design

Verify that analysis responsibilities are correctly mapped to design elements.

### Design ↔ Code

Verify that implementation conforms to approved design.

### Requirements ↔ Database

Verify that database entities, attributes and constraints are justified by approved requirements/business rules.

### Requirements ↔ Tests

Verify that tests cover approved requirements and rules.

---

# 17. Change Impact Analysis

Whenever an approved artifact changes, perform impact analysis.

Use:

Changed Artifact / ID  
→ Upstream Dependencies  
→ Downstream Dependencies  
→ Impacted Artifacts  
→ Required Action

Examples:

FR change  
→ UC  
→ Activity  
→ BCE/VOPC  
→ Design Sequence  
→ Class  
→ Method  
→ Test Case

Business Rule change  
→ UR/FR  
→ UC  
→ Database Constraint  
→ Code  
→ Test

NFR change  
→ Architecture  
→ Component  
→ Configuration / Code  
→ Performance/Security/Quality Test

Class Design change  
→ Code  
→ Unit Test  
→ Integration Test

---

# 18. Impact Classification

For every impacted artifact classify the impact as:

### Must Change

The artifact is directly affected and must be updated.

### Review Required

The artifact may be affected and requires human/technical review.

### No Impact

No change is required.

A `No Impact` classification MUST include a rationale.

---

# 19. Orphan Detection

The Agent MUST detect and report:

### Orphan Requirement
Requirement with no downstream realization or verification.

### Orphan Design Element
Design element with no valid upstream justification.

### Orphan Code
Code implementing behavior not supported by approved requirements/design.

### Orphan Test
Test with no approved test basis.

### Broken Trace
A lifecycle chain where an expected intermediate link is missing.

---

# 20. Significant Inconsistency Rule

Significant inconsistencies MUST NOT be silently repaired.

When a significant inconsistency is found:

1. identify the affected IDs;
2. identify conflicting artifacts;
3. describe the inconsistency;
4. identify upstream/downstream impact;
5. identify the responsible project role;
6. propose possible resolution where appropriate;
7. request a decision;
8. STOP propagation if the inconsistency affects an approved baseline.

---

# 21. Updating the RTM

Update the RTM whenever an approved artifact is:

- created;
- approved;
- changed;
- replaced;
- deprecated;
- implemented;
- tested.

Relevant lifecycle Skills should trigger RTM updates after their artifacts change.

Examples:

`requirements-engineering`
→ update BR / UR / FR / NFR

`usecase-modeling`
→ update UC traces

`software-design`
→ update Design Element traces

`database-design`
→ verify requirement-to-data consistency

`implementation`
→ update Code Element traces

`software-testing`
→ update Test traces

`devops-release`
→ verify release content against traceable approved artifacts

---

# 22. Human Verification

AI-generated traceability links are **proposed links until verified** when project governance requires human review.

The responsible role should verify that the relationship is semantically valid.

The Agent MUST NOT assume that two artifacts are traceable merely because they contain similar names or keywords.

Traceability must be based on actual responsibility, behavior, constraint, implementation, or verification relationships.

---

# 23. Output

The primary output is the updated approved workbook:

`/templates/Requirements_Traceability_Matrix_Simplified.xlsx`

During an actual project, do not overwrite the pristine template if project governance requires templates to remain unchanged.

Create/use the project artifact instance according to the project's artifact storage convention.

Additional outputs may include:

- traceability findings;
- consistency findings;
- orphan report;
- impact-analysis report;
- unresolved issues;
- coverage status.

Do not create additional permanent formats when the approved project template already provides the required structure.

---

# 24. Completion Criteria

Traceability work is complete for the current baseline when:

- required BRs are traced;
- required URs are traced;
- FRs/NFRs have appropriate downstream realization;
- Use Cases have approved upstream justification;
- significant Design Elements have upstream justification;
- significant Code Elements conform to Design;
- required Tests have valid test bases;
- required requirements have verification coverage;
- identified inconsistencies are resolved or formally accepted;
- RTM reflects the current approved baseline.

---

# 25. Traceability Consistency Gate

If the Agent identifies a significant inconsistency affecting an approved or baselined artifact:

**Report → Impact Analysis → Responsible Role Review → Resolution → RTM Update → Recheck**

Until an authorized resolution is received:

**STOP propagation to affected downstream artifacts.**

This Skill is cross-cutting and normally does not create an independent lifecycle baseline. It protects consistency among the existing project baselines.