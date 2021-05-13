# ASVS Requirement: V14.2.2 Unneeded assets removed

## ASVS:14.2.2

## ASVS Requirement description

Verify that all unneeded features, documentation, samples, configurations are removed, such as sample applications, platform documentation, and default or example users.

## User Story

**Feature_Name**: Ensure only required artefacts in the production environment are deployed

**Story**:
As a Security Engineer\
I want to ensure that I identity and remove any *artefacts* that aren’t required to run my application in production\
So that I can reduce the attack surface of my application

## Scenario

**Scenario_name**: Ensure there are no unnecessary *artefacts* in my production environment

**Gherkin syntax**:

```gherkin
Given a build and deployment process
When I deploy my application in UAT or Production environment
Then I I define the `artefacts` which aren’t deployed into production
```

`artefacts` in this context, refers to `features`, `documentation`, `samples`, `configuration`, `software and test dependencies`, `standalone users` etc

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
<https://cwe.mitre.org/data/definitions/531>
