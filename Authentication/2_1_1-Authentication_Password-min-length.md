## ASVS Requirement: V2.1.1
## ASVS:2.1.1

## ASVS Requirement description
Verify that user set passwords are at least 8 characters in length (after multiple spaces are combined)

## User Story
**Feature_Name**: Password length requirement

**Story**:
As a Security Engineer\
I want to ensure that a password of at least 8 characters is set
So that I reduce exposure of my system against brute force attacks

## Scenario
**Scenario_name**: Enforce minimum password length

**Gherkin syntax**:
```gherkin
Given the need to store user passwords
When I set criteria for password length
Then I enforce a minimum length of 8 characters for the password
```
## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\
