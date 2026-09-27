# Requirements Engineering Rules

## 1. Purpose
These rules govern requirements engineering activities from business context through requirements baseline.

## 2. Source-of-Truth Priority in Requirements
1. Approved business requirements, charter, and baselined artifacts.
2. Authorized stakeholder decisions.
3. Project-approved templates and checklists.
4. Business Rules and validated domain knowledge.
5. General reference books (e.g., Karl Wiegers & Joy Beatty, Software Requirements 3rd Edition).
6. Generic AI knowledge.

A lower-priority source MUST NOT override an approved business source or requirement baseline.

## 3. Separation of Requirement Types
Maintain strict conceptual and structural separation:
- **Business Requirements (Why):** Background, business problems/opportunities, business objectives, success metrics, vision, scope, and business risks.
- **Business Rules (Organizational Policies):** Policies, computations, constraints, and business logic that exist independently of software automation.
- **User Requirements (What users need):** User classes, user tasks, user goals, and user stories.
- **Software Requirements (What the system shall provide):**
  - **Functional Requirements (FR):** Verifiable statements of what the software must execute or support.
  - **Quality Attributes / Non-Functional Requirements (NFR):** Measurable quality characteristics (Performance, Security, Usability, Reliability, Maintainability, Availability).
  - **Constraints:** Technical, organizational, regulatory, or business limits placed on the solution.
  - **External Interfaces:** UI, Hardware, Software, Communication, and API interfaces.
  - **Data Requirements:** Logical data structures, data dictionary, retention, volume, and integrity rules.

## 4. Process-Driven Requirements Discovery
When the software automates or supports organizational workflows:
1. Explore and model the **AS-IS** business process first.
2. Identify pain points, bottlenecks, compliance issues, and opportunities.
3. Design and model the **TO-BE** business process using standard BPMN notation (`.drawio`).
4. Derive User Requirements and Functional Requirements directly from TO-BE process steps and actor responsibilities.

## 5. Do Not Invent Requirements
The Agent MUST NOT introduce requirements, business rules, or data attributes without a traceable basis:
- **Source-confirmed:** Clearly grounded in stakeholder input or project documentation.
- **Logically derived:** Directly and logically inferred from confirmed business processes or rules.
- **Proposed:** Tagged explicitly as `Proposed – Project approval required.`
- **Missing / Unknown:** Tagged explicitly as `TBD – Stakeholder confirmation required.`

A proposal MUST NOT silently become an approved requirement.

## 6. Identifier Stability and Conventions
Requirements MUST have unique, persistent, and traceable identifiers:
- `BO-xx`: Business Objective
- `BR-xx`: Business Rule
- `UC-xx`: Use Case
- `UR-xx`: User Requirement
- `FR-xx`: Functional Requirement
- `NFR-xx`: Non-Functional Requirement (or `QA-xx`)
- `CON-xx`: Constraint
- `EI-xx`: External Interface
- `DR-xx`: Data Requirement

Never renumber baselined requirements. If a requirement is deprecated, mark it `Deprecated / Withdrawn` with approved rationale.

## 7. Prototyping Rules
- Prototypes (UI wireframes, mockups, screen flows) SHOULD be used to clarify ambiguous, risky, or complex user interactions.
- A prototype is a visual clarification mechanism, NOT a license to invent new unapproved requirements.
- Any new requirement discovered through a prototype must be explicitly specified in the Requirements specification, verified against checklists, and approved before baseline.

## 8. Template and Presentation Rules
- Requirements MUST be documented within the project-approved master specification template: `/templates/Template_Requirements_Analysis_Design_Specification.docx`.
- Preserve existing sections, headings, tables, and conventions. Do not create parallel, unapproved SRS documents.
- RTM sheet in `/templates/Requirements_Traceability_Matrix_Simplified.xlsx` must be updated with all approved requirement IDs.

## 9. Verification Checklist
Every requirements increment MUST be statically verified against:
- `/checklists/d2_Checklist_SRS Review.xls`
- `/checklists/d1_Checklist_GUI Review.xls` (for prototypes and UI requirements)
- Traceability checks against business objectives and rules.

Report all defects, ambiguities, conflicting requirements, and TBD items.

## 10. Human Verification Gate & Baseline
- Requirements MUST NOT proceed to Analysis or Detailed Design without explicit approval from the Business Analyst, Product Owner, and authorized approvers.
- Once approved, the document forms the **Requirements Baseline**.
- Any downstream change to requirements must trigger Change Impact Analysis and formal re-baselining.
