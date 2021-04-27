# ASVS Requirement: V14.5.2 Origin header not used for auth or access control

## ASVS:14.5.2

## ASVS Requirement description

Verify that the supplied Origin header is not used for authentication or access control decisions, as the Origin header can easily be changed by an attacker.

## User Story

**Feature_Name**: Origin header not used for auth/access control

**Story**:
As a Security Engineer\
I want to verify that Origin header isn't used for authentication or access control purposes
So that an attacker can't easily use this route to gain unauthorised access to my application

## Scenario

**Scenario_name**: No auth/access control decisions made using Origin headers

**Gherkin syntax**:

```gherkin
 Given an HTTP request
 And an Origin header being present
 When I receive the Origin header
 Then I don't use it for authentication or access control purposes
```

## Validations

**Chef Inspec**
TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cwe.mitre.org/data/definitions/346>
<https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin>
