## ASVS Requirement: V2.1.2
## ASVS:14.2.2

## ASVS Requirement description
Verify that passwords of at least 64 characters are permitted, and that passwords of more than 128 characters are denied

## User Story
**Feature_Name**: Password length requirement

**Story**:
As a Security Engineer\
I want to ensure that a password of at least 64 characters is permitted
And and that more than 128 characters are denied
So that I don't constrain the use of secure password managers

## Scenario
**Scenario_name**: Enforce minimum and maximum password length

**Gherkin syntax**:
```gherkin
Given the need to store user passwords
When I set criteria for password length
Then I permit up to 64 character passwords
And no more than 128 character passwords
```
## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\