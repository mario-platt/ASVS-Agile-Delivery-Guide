# ASVS Requirement: V5.2.8 Verify that the application sanitizes, disables, or sandboxes user-supplied scriptable or expression template language content

## ASVS Requirement description

Verify that the application sanitizes, disables, or sandboxes user-supplied scriptable or expression template language content, such as Markdown, CSS or XSL stylesheets, BBCode, or similar.

## User Story

**Feature_Name**: Sanitization of user-supplied content

**Story**:\
As a Security Engineer\
I want to sanitize, disable or sandbox user-supplied scriptable or expression template language content
So that I can reduce the likelihood of malicious input resulting in security breaches

## Scenario

**Scenario_name**: Sanitization and sandboxing

**Gherkin syntax**:

```gherkin
Given the processing of `user-supplied scriptable or expression template language content`
When I validate input into my application
Then I ensure strict input validation is performed
And I run the code in a sandbox with limited resource and OS access in order to limite potential scope of security breach
```

**Scenario_name**: Diverse input testing eg fuzzing

**Gherkin syntax**:

```gherkin
Given the processing of `user-supplied scriptable or expression template language content`
When I test and validate input into my application
Then I ensure fuzz testing and fault injection is performed
And I confirm no security vulnerabilities exist and no unnaceptable performance or availability impact is experienced
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html> \
<https://cwe.mitre.org/data/definitions/94>
