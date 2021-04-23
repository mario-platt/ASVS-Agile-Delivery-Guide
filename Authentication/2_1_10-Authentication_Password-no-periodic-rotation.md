## ASVS Requirement: V2.1.10
## ASVS:.2.1.10

## ASVS Requirement description
Verify that there are no periodic credential rotation or password history requirements.

## User Story
**Feature_Name**: No periodic rotation of passwords

**Story**:
As a Security Engineer\
I want to be sure not to enforce periodic rotation of passwords for users or password history enforcement
So that they can set strong and memorable patterns and avoid predictable incremental patterns

## Scenario
**Scenario_name**: no periodic rotation of passwords

**Gherkin syntax**:
```gherkin
Given the setting and resetting of passwords
When I accept a password to be set
Then I don't enforce a periodic rotation of the password
And I don't verify password history
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\
https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html

https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html

https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html

https://cwe.mitre.org/data/definitions/263