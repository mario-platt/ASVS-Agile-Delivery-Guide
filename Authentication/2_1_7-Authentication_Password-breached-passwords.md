## ASVS Requirement: V2.1.7
## ASVS:.2.7

## ASVS Requirement description
Verify that passwords submitted during account registration and password change are checked against a set of breached passwords either locally (such as the top 50,000 to 100,000 most common passwords which match the system's password policy) or using an external API. If using an API a zero knowledge proof or other mechanism should be used to ensure that the plain text password is not sent or used in verifying the breach status of the password. Whenever there is a major third party breach of passwords, lock affected users and force a password change for the user to set a new non-breached password.

## User Story
**Feature_Name**: Breached password validation

**Story**:
As a Security Engineer\
I want to verify passwords set by users against known insecure passwords
So that they can choose passwords which aren't easily guessed

## Scenario
**Scenario_name**: Verify password selections against set of breached passwords locally for initial passwords

**Gherkin syntax**:
```gherkin
Given the need to set user passwords at registration
When I set criteria for the content of the password
Then I verify against known breached passwords locally
And I don't find a match
```

**Scenario_name**: Verify password selections against set of breached passwords locally for changing passwords

**Gherkin syntax**:
```gherkin
Given the need to set user passwords at registration
When I set criteria for the content of the password
Then I verify against known breached passwords locally
And I don't find a match
```

**Scenario_name**: Verify password selections against set of breached passwords through an API

**Gherkin syntax**:
```gherkin
Given the need to set user passwords at registration
When I set criteria for the content of the password
Then I verify against known breached passwords through an API
And I don't find a match
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