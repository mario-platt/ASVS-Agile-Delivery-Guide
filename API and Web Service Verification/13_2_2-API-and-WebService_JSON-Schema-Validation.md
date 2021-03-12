## ASVS Requirement: V13.2.2 JSON Schema Validation
## ASVS:13.2.2

## ASVS Requirement description
Verify that JSON schema validation is in place and verified before accepting input.

## User Story
**Feature_Name**: Proper Input Validation

**Story**:\
As a Security Engineer\
I want all of the input which can affect control or data flow to be validated\
So that I can protect my application from malicious manipulation which could lead to unauthorised disclosure or loss of integrity

## Scenario
**Scenario_name**: Use of input validation framework

**Gherkin syntax**:
```gherkin
Given functions processing externally provided inputs
When I parse or encode such inputs
Then I use an `input validation framework` to reduce exposure to parsing-related threats
```
**Scenario_name**: Input conformance to specifications

**Gherkin syntax**:
```gherkin
Given functions processing externally provided input
When I parse or encode such inputs
Then I validate that inputs are conforming to specification
```
**Scenario_name**: Input transformation to specifications

**Gherkin syntax**:
```gherkin
Given functions processing externally provided input
When I parse or encode such inputs
Then I transform it to meet expected specification
```

**Scenario_name**: Conversion of input type to expected data type

**Gherkin syntax**:
```gherkin
Given functions processing externally provided input
When I parse or encode such inputs
Then I convert input into the expected data type
And that input value is within an expected range of allowable values
```

**Scenario_name**: Conversion of input type to expected data type

**Gherkin syntax**:
```gherkin
Given functions processing externally provided input
When I parse or encode such inputs
And exchange data between components
Then I confirm both components are using the same character encoding
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\
https://cheatsheetseries.owasp.org/cheatsheets/REST_Assessment_Cheat_Sheet.html\
https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html\
https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html\
https://cwe.mitre.org/data/definitions/20
