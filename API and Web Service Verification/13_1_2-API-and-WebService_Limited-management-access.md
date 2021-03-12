## ASVS Requirement: V13.1.2 Limit access to administration and management functions to authorized administrators
## ASVS:13.1.2

## ASVS Requirement description
Verify that access to administration and management functions is limited to authorized administrators.

## User Story
**Feature_Name**: Limited access to admin / management functions

**Story**:\
As a Security Engineer\
I want to ensure that administrative or management functionality is restricted access\
So that I can protect my system against unauthorised access attempts

## Scenario
**Scenario_name**: Unexposed admin functionality on UI

**Gherkin syntax**:
```gherkin
Given a business need to expose an administrative endpoint\
When I wish to perform administrative functions\
Then I provide a separate endpoint which has further access restrictions to protect this functionality from being maliciously accessed
```
**Scenario_name**: Protection of administrative interface

**Gherkin syntax**:
```gherkin
Given a business need to expose an administrative endpoint\
When I wish to perform administrative functions\
Then I use `strong mechanisms` for authentication and authorisation
```
`strong mechanisms` can entail Multi-factor authentication, or mechanisms akin to 'sudo' to provide individual authorisation for critical tasks

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\
https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet.html
https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html
https://cwe.mitre.org/data/definitions/419