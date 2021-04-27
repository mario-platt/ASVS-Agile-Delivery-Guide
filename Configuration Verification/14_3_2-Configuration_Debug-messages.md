# ASVS Requirement: V14.3.3 Disabled debug modes

## ASVS:14.3.2

## ASVS Requirement description

Verify that web or application server and application framework debug modes are disabled in production to eliminate debug features, developer consoles, and unintended security disclosures.

## User Story

**Feature_Name**: Disabling debug modes

**Story**:
As a Security Engineer\
I want to ensure that debug modes on web or application servers and frameworks are disabled
So that I can eliminate from production debug features, developer consoles, and security disclosures

## Scenario

**Scenario_name**: Validate debug modes are disabled

**Gherkin syntax**:

```gherkin
Given a web or application server or an application framework
When I deploy it on my production environment
Then I ensure that debug modes are disabled
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet.html>
<https://cwe.mitre.org/data/definitions/497>
