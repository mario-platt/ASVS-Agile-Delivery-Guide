# ASVS Requirement: V14.2.1 Updated components

## ASVS:14.2.1

## ASVS Requirement description

Verify that all components are up to date, preferably using a dependency checker during build or compile time.

## User Story

**Feature_Name**: Identification of known vulnerable dependencies at build or compile time

**Story**:
As a Security Engineer\
I want to ensure known vulnerabilities are identified when I build/compile my application\
So that I can identify and remediate vulnerable dependencies

## Scenario

**Scenario_name**: Integrated vulnerability checker software into the build/compile process

**Gherkin syntax**:

```gherkin
Given a build and deployment process
When I deploy my application in UAT or Production environment
Then I ensure I’m identifying any potentially vulnerable dependencies
And raising JIRA tickets with identified high or critical vulnerabilities if this is the case
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet.html> \
<https://cwe.mitre.org/data/definitions/1104>
