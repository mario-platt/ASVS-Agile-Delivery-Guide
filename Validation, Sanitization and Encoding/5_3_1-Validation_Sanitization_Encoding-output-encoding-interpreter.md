## ASVS Requirement: V5.3.1 Verify that output encoding is relevant for the interpreter and context required

## ASVS Requirement description
Verify that output encoding is relevant for the interpreter and context required. For example, use encoders specifically for HTML values, HTML attributes, JavaScript, URL Parameters, HTTP headers, SMTP, and others as the context requires, especially from untrusted inputs (e.g. names with Unicode or apostrophes, such as bla or OHara).

## User Story
**Feature_Name**: Sanitization of user-supplied content

**Story**:\
As a Security Engineer\
I want to validate output encoding relevance to the interpreter and context
So that I restrict and validate the required data encodings to what's required by different components

## Scenario

**Scenario_name**: Use of Encoding libraries and frameworks

**Gherkin syntax**:
```gherkin
Given functions processing externally provided inputs
When I parse or encode such inputs in order to send to another component
Then I use an `input validation framework or library` to normalise output encoding
```
Relevant `input validation frameworks` could be  ESAPI Encoding control [REF45]

**Scenario_name**: Detailed specification of encodings required

**Gherkin syntax**:
```gherkin
Given functions processing externally provided inputs
When I parse or encode such inputs in order to send to another component
Then I determine and programatically enforce the required encodings for each component
```

**Scenario_name**: Standardisation of encoding usage between components

**Gherkin syntax**:
```gherkin
Given functions processing externally provided inputs
When I parse or encode such inputs in order to send to another component
Then I ensure that all components are using the same character encoding
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_in_Java_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/Bean_Validation_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html \
https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet.html \
https://cwe.mitre.org/data/definitions/116