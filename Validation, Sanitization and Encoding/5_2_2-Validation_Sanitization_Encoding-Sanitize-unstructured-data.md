## ASVS Requirement: V5.2.2 Verify that unstructured data is sanitized to enforce safety measures
## ASVS:5.2.2

## ASVS Requirement description
Verify that unstructured data is sanitized to enforce safety measures such as allowed characters and length.

## User Story
**Feature_Name**: Sanitization of unstructured data

**Story**:\
As a Security Engineer\
I want to neutralize special elements that could be interpreted as controls elements or syntactic markers
So that I can protect my application from abuse and exploitation

## Scenario

**Scenario_name**: Anticipation of input vectors through whitelisting

**Gherkin syntax**:
```gherkin
Given a need process external requests
When I validate input into my application
Then I anticipate the `special elements` that could be injected
And create a whitelist using regular expressions
And only allow requests which meet the regular expression
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
https://cwe.mitre.org/data/definitions/138