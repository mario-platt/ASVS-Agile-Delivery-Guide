## ASVS Requirement: V2.1.3

## ASVS:14.2.3

## ASVS Requirement description

Verify that password truncation is not performed. However, consecutive multiple spaces may be replaced by a single space

## User Story

**Feature_Name**: Disallow password truncation

**Story**:
As a Security Engineer\
I want to disallow password truncation
And allow single space
And disalllow multiple spaces
So that we can increase password complexity by allowing single spaces

## Scenario

**Scenario_name**: Enforce minimum and maximum password length

**Gherkin syntax**:

```gherkin
Given the need to store user passwords
When I set criteria for the content of the password
Then I disallow password truncation
But I replace multiple spaces with a single space
```

**Gherkin syntax**:

```gherkin
Given the need to store user passwords
When I set criteria for the content of the password
Then I disallow password truncation
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
