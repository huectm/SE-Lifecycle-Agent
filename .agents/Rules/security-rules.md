# Security Engineering Rules

## 1. Purpose
These rules govern security-related requirements, design, implementation, testing, and operational handling.

## 2. Security by Lifecycle
Security MUST be considered across Requirements → Design → Implementation → Testing → Deployment/Operation.

## 3. Security Requirements
Security requirements MUST have approved sources such as:
- business risk;
- quality requirements;
- legal/compliance obligations;
- organizational security policy;
- threat/risk analysis.

Do not invent compliance obligations.

## 4. Authentication and Authorization
Apply authentication and authorization according to approved requirements. Authorization SHOULD follow least privilege and role/permission design.

## 5. Secrets
NEVER store passwords, API keys, access tokens, private keys, connection secrets, or personal credentials in:
- Rules
- Skills
- AGENTS.md
- source code
- templates
- example files
- committed configuration files

Use approved secret managers, environment variables, CI/CD secret stores, or secure credential mechanisms.

## 6. Sensitive Data
Identify sensitive/personal data and apply applicable privacy, access, retention, logging, and protection requirements.

## 7. Input and Output Security
Validate untrusted input and use appropriate output encoding/escaping according to context.

## 8. Data Protection
Use approved encryption/protection mechanisms for data in transit and at rest when required.

## 9. Logging
Security-relevant logging SHOULD support audit and incident investigation without logging secrets or unnecessary sensitive data.

## 10. Dependency Security
Track third-party dependencies and address known vulnerabilities according to project policy.

## 11. Static Analysis
Use approved SAST/static-analysis tools. Findings MUST be reviewed before being treated as confirmed defects.

## 12. Security Testing
Security testing MUST trace to security requirements, threat/risk findings, or approved test objectives.

## 13. External Tools and Accounts
The Agent MUST NOT request account passwords or long-lived secrets for inclusion in project files.

When a tool requires authentication, document:
- tool/service name;
- required permission/scope;
- approved authentication mechanism;
- where the user/project administrator configures credentials.

Do NOT document secret values.

## 14. Security Review Gate
Critical/high-risk unresolved security issues MUST be explicitly accepted by authorized project roles before release.
