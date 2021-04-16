## ASVS Requirement: V5.2.1 Verify that untrusted HTML input from WYSIWYG editors is properly sanitized with HTML sanitizer library or framework
## ASVS:5.2.1

## ASVS Requirement description
Verify that all untrusted HTML input from WYSIWYG editors or similar is properly sanitized with an HTML sanitizer library or framework feature.

## User Story
**Feature_Name**: HTML input sanitization

**Story**:\
As a Security Engineer\
I want all HTML input to be properly sanitized with an HTML sanitizer library or framework
So that I strictly control the effects of inputs into my application

## Scenario

**Scenario_name**: Specification of encodings required

**Gherkin syntax**:
```gherkin
Given a need to encode or escape content
And send it to different services
When I validate supported encodings
Then I clearly define which encodings I support
And I ensure all others aren't accepted
And I provide a notification informative of this rejection
```

**Scenario_name**: Parameterization of queries

**Gherkin syntax**:
```gherkin
Given a need to encode or escape content
And send it to different services
When I need to perform queries
Then I use stored procedures or similar to reduce reliance on manual validations
```

**Scenario_name**: Enforcement through libraries or frameworks

**Gherkin syntax**:
```gherkin
Given a need to encode or escape content
And send it to different services
Then I use a vetted library or framework that does not allow weak
And I reject all other inputs
```
"Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid. For example, consider using the ESAPI Encoding control [REF45] or a similar tool, library, or framework. These will help the programmer encode outputs in a manner less prone to error. Alternately, use builtin functions, but consider using wrappers in case those functions are discovered to have a vulnerability." from `SKF`

**Scenario_name**: Standardised encodings

**Gherkin syntax**:
```gherkin
Given a need to encode or escape content
And send it to different services
When I choose a library or framework for encoding or parsing
Then I ensure consistent use configuration, libraries or frameworks
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
https://cwe.mitre.org/data/definitions/116