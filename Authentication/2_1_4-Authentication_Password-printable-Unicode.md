## ASVS Requirement: V2.1.4
## ASVS:14.2.4

## ASVS Requirement description
Verify that any printable Unicode character, including language neutral characters such as spaces and Emojis are permitted in passwords.

## User Story
**Feature_Name**: Disallow password truncation

**Story**:
As a Security Engineer\
I want to allow any printable Unicode character to be used in passwords
So that we can support large universe of characters to be used in passwords

## Scenario
**Scenario_name**: Allow printable Unicode characters in passwords

**Gherkin syntax**:
```gherkin
Given the need to store user passwords
When I set criteria for the content of the password
Then I allow printable Unicode characters
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

https://cwe.mitre.org/data/definitions/521