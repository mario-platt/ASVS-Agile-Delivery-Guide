## ASVS Requirement: V14.5.1 Verify only accepted HTTP methods are used, including pre-flight OPTIONS
## ASVS:14.5.1

## ASVS Requirement description
Verify that the application server only accepts the HTTP methods in use by the application or API, including pre-flight OPTIONS.

## User Story
**Feature_Name**: HTTP method restriction

**Story**:
As a Security Engineer\
I want to restrict the HTTP methods available\
So that I can reduce the attack surface of my application

## Scenario
**Scenario_name**: Ensure X-Frame-Options header is enabled in all HTTP responses

**Gherkin syntax**:
```gherkin
	Given an HTTP request
	And an HTTP method being used
	When I receive an HTTP response
	Then the HTTP status code isn't 4XX or 5XX
```


## Validations

**Chef Inspec**
TBC

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cwe.mitre.org/data/definitions/749
https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods