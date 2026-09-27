# Software Design Rules

## 1. Purpose
These rules govern high-level and detailed software design.

## 2. Entry Criteria
Design uses approved requirements and analysis artifacts as inputs. Significant unresolved requirement/analysis defects MUST be addressed or explicitly accepted before design is baselined.

## 3. Architecture Drivers
Architecture decisions MUST be justified by:
- Functional Requirements
- Quality Attributes
- Constraints
- Integration needs
- Data requirements
- Deployment needs
- Risks

Do not select architecture styles or patterns only because they are popular.

## 4. Architecture Selection
Possible approaches include, when justified:
- Layered Architecture
- MVC
- MVVM
- Component-Based Architecture
- Service-Oriented Architecture
- Microservices
- Modular Monolith
- Repository Pattern
- Dependency Injection

The selected approach MUST include rationale and trade-offs.

## 5. High-Level Design
High-level design SHOULD define:
- system/subsystem boundaries;
- major components/services;
- responsibilities;
- dependencies;
- external integrations;
- deployment-relevant boundaries where applicable.

## 6. Component and Package Design
Components/packages MUST have cohesive responsibilities and controlled dependencies.

Avoid cyclic dependencies unless explicitly justified.

## 7. Analysis-to-Design Mapping
Every significant analysis class/responsibility MUST be mapped to one or more design elements or explicitly marked as transformed/merged/removed with rationale.

Maintain a mapping table when appropriate:
| Analysis Element | Design Element | Mapping / Rationale |

## 8. Detailed Use Case Realization
After architecture is approved, realize Use Cases at design level.

Design Sequence Diagrams MUST:
- reflect approved Use Case behavior;
- use actual design classes/components;
- respect architecture boundaries;
- show important calls/messages;
- remain consistent with class responsibilities.

## 9. Detailed Class Design
Detailed class specifications SHOULD include, where relevant:
- responsibility;
- attributes;
- operations;
- visibility;
- parameter/return types;
- relationships;
- interfaces;
- constraints.

Do not add methods/fields without responsibility or requirement/design rationale.

## 10. Design Patterns
Patterns such as Repository and Dependency Injection MUST be applied because they solve identified design problems, not as mandatory decoration.

## 11. Quality Attributes
Design MUST explicitly address applicable quality attributes such as performance, security, reliability, availability, maintainability, scalability, and testability.

## 12. Diagram Format
Architecture and UML design diagrams SHOULD be delivered as editable `.drawio` files unless another format is approved.

## 13. Design Review
Apply the project Design Review Checklist before baselining. Record findings, fixes, and unresolved issues.

## 14. Verification Gate
Verify:
Requirements ↔ Analysis ↔ Architecture ↔ Detailed Design.

Design MUST be approved before implementation proceeds beyond explicitly authorized prototypes/spikes.
