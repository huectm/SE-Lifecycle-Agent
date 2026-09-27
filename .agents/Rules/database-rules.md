# Database Design Rules

## 1. Purpose
These rules govern conceptual, logical, and physical database design.

## 2. Sources
Database design MUST derive from:
- Data Requirements
- Business Rules
- Functional Requirements
- Use Cases
- Analysis entities
- Reporting/audit needs
- Integration requirements
- Legal/privacy/retention obligations

## 3. No Unsupported Data
Do not introduce business entities, attributes, or relationships without an approved source or documented technical rationale.

## 4. Conceptual and Logical Design
Identify:
- entities;
- attributes;
- identifiers;
- relationships;
- cardinalities;
- optionality;
- business integrity constraints.

## 5. Physical Design
Physical schema decisions MAY introduce technical fields such as surrogate keys, timestamps, concurrency fields, indexes, and audit metadata when justified.

Technical fields MUST be distinguishable from business data.

## 6. Normalization and Denormalization
Normalize data appropriately to reduce anomalies. Denormalization MUST have a documented reason such as performance/reporting needs and MUST preserve correctness.

## 7. Referential Integrity
Foreign keys and relationship constraints SHOULD enforce approved domain relationships unless a justified architecture constraint requires another approach.

## 8. Business Rules
Database constraints MAY enforce Business Rules when appropriate, but enforcement location MUST be consistent with architecture and application rules.

## 9. Security and Privacy
Apply least privilege, sensitive-data protection, retention, audit, and privacy requirements where applicable.

Never place credentials/secrets in schema scripts or repository files.

## 10. Traceability
Maintain traceability:
Requirement / Business Rule → Data Entity/Attribute/Constraint → Database Element.

## 11. Review Gate
Before database baseline:
- check consistency with requirements and analysis/design;
- review integrity and deletion/update behavior;
- review security/privacy;
- review migration implications;
- obtain approval from responsible design/database roles.
