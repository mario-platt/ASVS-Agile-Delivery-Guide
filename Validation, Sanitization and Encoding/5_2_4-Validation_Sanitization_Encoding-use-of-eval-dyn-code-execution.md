## ASVS Requirement: V5.2.4 Verify that application avoids using eval or other dynamic code execution features

## ASVS Requirement description
Verify that the application avoids the use of eval() or other dynamic code execution features. Where there is no alternative, any user input being included must be sanitized or sandboxed before being executed, which can lead to execution of arbitrary code.

## User Story
**Feature_Name**: Sanitization of user input towards mail systems

**Story**:\
As a Security Engineer\
I want to avoid using eval() or other dynamic code execution features
So that I can reduce opportunities for malicious code execution by attackers

## Scenario

**Scenario_name**: Refactoring use of eval()

**Gherkin syntax**:
```gherkin
Given current use of eval() and other dynamic code execution features
When I confirm the use case for needing it
Then refactor the code to use functions with expected returns
```

**Scenario_name**: Sanitization and sandboxing

**Gherkin syntax**:
```gherkin
Given a current use of eval() and other dynamic code execution features
When I validate input into my application
Then I ensure strict input validation is performed
And I run the code in a sandbox in order to limite potential scope of security breach
```


## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html \
https://cwe.mitre.org/data/definitions/95