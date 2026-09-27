# Software Testing Rules

## 1. Purpose
These rules govern static and dynamic testing following a V-Model-oriented lifecycle.

## 2. Testing Principle
Testing begins with work-product review, not only with executable code.

For each development artifact:
Create → Review → Record Defects → Confirm → Fix → Re-review → Exit Criteria → Baseline/Next Activity.

## 3. Static Testing
Apply review/checklist-based static testing to applicable artifacts:
- Business/Software Requirements
- Use Cases
- UI/GUI specifications/prototypes
- Analysis/Design
- Source Code
- Test Cases

Use project checklists from `/checklists` where applicable.

## 4. Defect Management
Each detected issue SHOULD record:
- Defect ID
- Artifact/version
- Description
- Severity/Priority if project process requires
- Source/checklist item
- Owner
- Status
- Resolution
- Re-test/re-review result

Do not silently fix review defects without recording them when the project requires defect logging.

## 5. Test Levels
Dynamic testing MAY include:
- Unit Testing
- Integration Testing
- System Testing
- Acceptance Testing when in scope

Each level MUST have a defined test basis and scope.

## 6. Test Design Techniques
Use appropriate techniques including:
- Equivalence Partitioning
- Boundary Value Analysis
- Use Case Testing
- State Transition Testing
- Decision Table Testing when applicable
- Experience-Based Testing
- Exploratory Testing

Select techniques based on the test basis; do not mechanically apply every technique.

## 7. Structural Coverage
Where appropriate, design/measure structural coverage such as:
- Statement coverage
- Branch coverage
- Condition coverage
- Basic path / basis-path coverage

Coverage targets MUST come from approved project criteria; do not invent thresholds.

## 8. Requirements Coverage
Test design MUST cover approved requirements and relevant Business Rules.

Maintain traceability:
Requirement / Use Case / Rule → Test Condition → Test Case → Test Result → Defect.

## 9. Test Case Template
Use project-approved templates from `/templates/Test Documents` or the applicable project template.

Do not replace them with a generic AI format.

## 10. Test Data
Where required, test data SHOULD be maintained separately, including CSV for data-driven automation when the project specifies it.

Test data MUST NOT expose real credentials or sensitive production data.

## 11. Unit Testing
Unit tests SHOULD verify individual units/classes/components according to design and code contracts.

Unit-test projects MUST follow the technology stack and project structure.

## 12. Integration Testing
Integration tests MUST target interfaces/interactions between integrated units, components, services, databases, or external systems.

## 13. System Functional Testing
System functional testing MUST validate end-to-end behavior against approved Software Requirements and Use Cases.

## 14. Non-functional System Testing
When in scope, include:
- Performance Testing
- Load/Stress Testing
- Security Testing
- Usability/Reliability/Compatibility testing as required

Non-functional test objectives MUST trace to quality requirements or approved risks.

## 15. Test Automation
Automation MAY include:
- Unit test automation
- Data-driven functional automation
- Keyword-driven functional automation
- API automation
- Performance automation

Automation architecture MUST be maintainable and traceable to test cases.

## 16. Static Code Analysis
Run approved static-analysis tools such as SonarQube when configured by the project.

Findings SHOULD be classified and reviewed; tool output is evidence, not automatically a confirmed defect.

Security findings require appropriate verification.

## 17. Entry and Exit Criteria
Each test level/activity SHOULD define entry and exit criteria.

The Agent MUST NOT invent pass/fail thresholds. Missing criteria are `TBD – Project confirmation required`.

## 18. Review Gate
Before closing a testing phase:
- required tests executed;
- results recorded;
- defects triaged;
- coverage evaluated;
- exit criteria checked;
- unresolved risks documented;
- responsible QA/Test Lead or authorized approver confirms completion.
