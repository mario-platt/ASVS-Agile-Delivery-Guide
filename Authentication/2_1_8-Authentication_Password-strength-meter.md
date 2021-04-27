# ASVS Requirement: V2.1.8

## ASVS:.2.1.8

## ASVS Requirement description

Verify that a password strength meter is provided to help users set a stronger password.

## User Story

**Feature_Name**: Password strength meter

**Story**:
As a Security Engineer\
I want to provide feedback to a users password strength when they are setting it
So that they can set strong passwords and protect access to their information

## Scenario

**Scenario_name**: Strength meter is present

**Gherkin syntax**:

```gherkin
Given the setting of a user password
When validate password strength against my password policy
Then I provide a strength meter visualisation to the user of their password strength
And ensure it updates dynamically as the user introduces password characters
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html> \
<https://cwe.mitre.org/data/definitions/521>
