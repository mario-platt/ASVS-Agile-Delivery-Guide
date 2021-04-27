# ASVS Requirement: V14.3.3 HTTP headers or any part of HTTP response don't expose detailed version info of components

## ASVS:14.3.3

## ASVS Requirement description

Verify that the HTTP headers or any part of the HTTP response do not expose detailed version information of system components.

## User Story

**Feature_Name**: HTTP header and response component version removal

**Story**:
As a Security Engineer\
I want to ensure HTTP headers and responses don't expose detailed version information of components
So that I can reduce attackers ability to identify vulnerable components in my application

## Scenarios

**Scenario_name**: HTTP header component version removal

**Gherkin syntax**:

```gherkin
Given the transmission of an HTTP header
When I analyse verify the information in the header
Then I ensure versions of components used aren't included
```

**Scenario_name**: HTTP response component version removal

**Gherkin syntax**:

```gherkin
Given and HTTP response
When I analyse verify the information in the header
Then I ensure versions of components used aren't included in the response
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
<https://cwe.mitre.org/data/definitions/200>
