> **Version:** 3.0 — Template-Driven  
> **Governance:** `/AGENTS.md` and applicable `.agents/rules/*.md`.  
> **Mandatory template rule:** Before creating/updating an artifact, inspect the actual approved template in `/templates` (sections, sheets, columns, fields, formulas, validation, naming, embedded result/report areas). Populate the existing structure. Do **not** add/delete/rename/reorder/redesign it without authorization. If an approved template already contains the required output/report, do not create a duplicate artifact. If a required template does not exist, report `TEMPLATE MISSING`, propose a format if useful, and STOP for approval before adopting it.  
> **Gate rule:** At required verification/baseline gates, submit to the authorized project role and STOP until approval/revision instructions.

# Software Design Skill
## A. High-Level Architecture
1. Inspect Design sections of the approved master specification.
2. Identify architecture drivers from FRs, Quality Attributes, Constraints, integrations, data, deployment and risks.
3. Evaluate/select justified styles/patterns such as Layered, MVC, MVVM, Component-Based, SOA, Modular Monolith, Microservices, Repository and DI.
4. Record rationale/trade-offs using the approved structure.
5. Define subsystems/components/services/interfaces/dependencies.
6. Create required Architecture/Component/Package diagrams.
7. Coordinate with `database-design`; verify quality-attribute support.
## B. Detailed Design
After architecture approval:
1. Map Analysis classes/responsibilities to Design classes/components/services.
2. Create Design Sequence Diagrams.
3. Create Detailed Design Class Diagrams.
4. Populate detailed class specifications using exact approved fields.
5. Verify architecture boundaries and `Requirements ↔ Analysis ↔ Architecture ↔ Detailed Design`.
6. Insert/reference outputs in designated sections, update RTM and apply Design Review Checklist.
## Gate
Submit to Architect/Technical Lead and authorized roles; STOP until Design Baseline approval.
