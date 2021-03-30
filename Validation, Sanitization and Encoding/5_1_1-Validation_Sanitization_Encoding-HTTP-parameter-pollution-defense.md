## ASVS Requirement: V5.1.1 HTTP parameter pollution defense
## ASVS:5.1.1

## ASVS Requirement description
Verify that the application has defenses against HTTP parameter pollution attacks, particularly if the application framework makes no distinction about the source of request parameters (GET, POST, cookies, headers, or environment variables).

## User Story
**Feature_Name**: HTTP parameter validation against pollution attacks

**Story**:
As a Security Engineer\
I want to confirm app behaviour when multiple parameters exist with the same name
So that I detect and manage any behaviour that could lead to incorrect sanitisation of input

## Scenario
**Scenario_name**: HTTP parameter pollution defense

**Gherkin syntax**:
```gherkin
Given an HTTP request
And parameters being passed in URL
And multiple values for the same parameter are defined
When I validate app behaviour from the parameter duplication
Then I ensure that the app can handle this event without unintended side effects
```


## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html \
https://cwe.mitre.org/data/definitions/235 \
https://securityintelligence.com/posts/how-to-prevent-http-parameter-pollution/