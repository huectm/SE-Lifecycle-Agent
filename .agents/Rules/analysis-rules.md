# Software Analysis Rules

## 1. Purpose
These rules govern analysis activities after the Requirements Baseline is approved.

## 2. Entry Criteria
Analysis MUST NOT begin until applicable requirements are approved/baselined or explicitly authorized for iterative analysis.

Required inputs may include:
- Software Requirements
- Use Case Model and Use Case Descriptions
- Activity Diagrams
- Business Rules
- Data Requirements
- Prototypes
- Traceability information

## 3. BCE Analysis
For each significant Use Case, identify participating analysis classes using BCE:
- Boundary: interaction between actors/external systems and the system.
- Control: coordinates use-case behavior/business flow.
- Entity: represents persistent or domain information.

Do NOT force a fixed number of BCE classes. Classes must be justified by responsibilities.

## 4. Boundary Rules
Boundary classes SHOULD correspond to meaningful interaction points such as UI screens/forms, APIs, external-system adapters, or interfaces.

Do not model every UI widget as a separate Boundary class unless justified.

## 5. Control Rules
Control classes coordinate use-case flow. Avoid placing persistent domain state or low-level infrastructure responsibilities in Control classes.

A complex Use Case MAY require more than one Control class when responsibilities justify it.

## 6. Entity Rules
Entity classes MUST derive from domain/data concepts supported by approved requirements. Do not invent entities without an approved source or documented design rationale.

## 7. VOPC
Create a View of Participating Classes (VOPC) for relevant Use Cases before detailed interaction modeling.

A VOPC SHOULD show:
- participating Boundary, Control, Entity classes;
- relevant actors where the project notation requires them;
- meaningful relationships needed to understand participation.

The VOPC is an analysis view, not a final design class diagram.

## 8. Analysis Sequence Diagrams
Analysis Sequence Diagrams MUST realize approved Use Case flows using participating analysis objects.

Check:
- actor/system interactions match the Use Case Description;
- alternative/exception behavior is represented when significant;
- messages correspond to analysis responsibilities;
- no premature framework/database implementation detail is introduced.

## 9. State Machine Diagrams
Create State Machine Diagrams for entities or systems whose behavior depends materially on lifecycle state.

States and transitions MUST derive from requirements, Business Rules, Use Cases, or approved domain behavior.

Each transition SHOULD have a meaningful trigger and, where applicable, guard/action.

## 10. Analysis Class Responsibilities
Each analysis class MUST have a clear responsibility. Avoid:
- duplicate responsibilities;
- god classes;
- infrastructure-specific details;
- design patterns introduced without need.

## 11. Consistency
Verify:
Use Case ↔ Activity Diagram ↔ BCE ↔ VOPC ↔ Analysis Sequence ↔ State Machine.

Any discrepancy MUST be reported.

## 12. Output Format
UML diagrams SHOULD be editable `.drawio` files unless project standards require another format.

## 13. Review Gate
Before Design:
1. Self-review analysis artifacts.
2. Apply applicable design/analysis checklist.
3. Run traceability/consistency checks.
4. Record defects/issues.
5. Correct and re-review.
6. Obtain approval from the responsible System Analyst / Architect / project approver.
