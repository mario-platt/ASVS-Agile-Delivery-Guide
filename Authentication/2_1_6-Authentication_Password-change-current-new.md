## ASVS Requirement: V2.1.6
## ASVS:.2.6

## ASVS Requirement description
Verify that password change functionality requires the user's current and new password.

## User Story
**Feature_Name**: User password change

**Story**:
As a Security Engineer\
I want to allow users to change their passwords
So that they can manage the lifecycle of their passwords

## Scenario
**Scenario_name**: Password change process requiring current and new password

**Gherkin syntax**:
```gherkin
Given the need to manage user passwords
When I provide a mechanism to change passwords
Then I require current user password
And the new password
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\