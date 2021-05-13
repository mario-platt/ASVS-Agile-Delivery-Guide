# ASVS Requirement: V5.1.4 Verify that structured data is strongly typed and validated against defined schema

## ASVS:5.1.3

## ASVS Requirement description

Verify that structured data is strongly typed and validated against a defined schema including allowed characters, length and pattern (e.g. credit card numbers or telephone, or validating that two related fields are reasonable, such as checking that suburb and zip/postcode match).

## User Story

**Feature_Name**: Proper Input Validation

**Story**:\
As a Security Engineer\
I want all of the structured data to be strongly typed and validated against a defined schema\
So that I can reduce the attack surface of my application

## Scenario

**Scenario_name**: Validation of schema

**Gherkin syntax**:

```gherkin
Given the processing of structured data
When I parse or encode this data
Then I validate that only allowed characters, length and pattern are being used
And I reject the processing for non-compliance
```

**Scenario_name**: Use of input validation framework

**Gherkin syntax**:

```gherkin
Given functions processing externally provided inputs
When I parse or encode such inputs
Then I use an `input validation framework` to reduce exposure to parsing-related threats
```

Relevant `input validation frameworks` could be Struts or OWASP ESAPI Validation API

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

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html> \
<https://cwe.mitre.org/data/definitions/20>
