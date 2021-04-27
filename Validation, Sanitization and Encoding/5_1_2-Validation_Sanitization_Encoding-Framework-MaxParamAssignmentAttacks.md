# ASVS Requirement: V5.2 Framework protection against mass or unsafe parameter assignment attacks

## ASVS:5.1.2

## ASVS Requirement description

Verify that frameworks protect against mass parameter assignment attacks, or that the application has countermeasures to protect against unsafe parameter assignment, such as marking fields private or similar.

## User Story

**Feature_Name**: Protection against mass parameter assignment attacks

**Story**:
As a Security Engineer\
I want to use frameworks that protect against mass parameter assignment attacks
So that I can protect those elements and ensure expected application behavior

## Scenario

**Scenario_name**: Specify what's allowed to be modified

**Gherkin syntax**:

```gherkin
Given an HTTP request
And attributes, properties or fields are initialised or updated
When I process or parse those attributes, properties or fields
Then I specify which are allowed to be modified through an allow-list or deny-list
```

Examples could be in Ruby, using `attr_accessible (whitelist)` macro in each class that could be used in assignment, or in Javascript through using input validation libraries such as `express-validator` for Express code, for instance.

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
<https://cwe.mitre.org/data/definitions/915> \
<https://www.acunetix.com/blog/web-security-zone/deserialization-vulnerabilities-attacking-deserialization-in-js/>
