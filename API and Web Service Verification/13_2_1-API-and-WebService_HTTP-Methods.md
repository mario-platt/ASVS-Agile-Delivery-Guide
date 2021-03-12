## ASVS Requirement: V13.2.1 Verify RESTful HTTP methods
## ASVS:13.2.1

## ASVS Requirement description
Verify that enabled RESTful HTTP methods are a valid choice for the user or action, such as preventing normal users using DELETE or PUT on protected API or resources.

## User Story
**Feature_Name**: Trusted HTTP Permission methods on Server Side

**Story**:\
As a Security Engineer\
I want ensure I only allow the appropriate HTTP methods to the associated operation\
So that I can ensure access to resources is controlled and protected

## Scenario
**Scenario_name**: Ensure GET method isn't used to modify state of application

**Gherkin syntax**:\
```gherkin
Given the use of an HTTP method\
And as HTTP GET is used\
When I determine the related operation being performed\
Then it is not performing any changes in application state
```
**Scenario_name**: Validate all used HTTP methods are restricted to the scope of the function

**Gherkin syntax**:\
Given the creation of a new function\
When I use HTTP methods\
Then I restrict restrict it to only the required methods for the operation being handled


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
https://cwe.mitre.org/data/definitions/650
