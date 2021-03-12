## ASVS Requirement: V13.1.1 Use same encoders and parsers
## ASVS:13.1.1

## ASVS Requirement description
Verify that all application components use the same encodings and parsers to avoid parsing attacks that exploit different URI or file parsing behavior that could be used in SSRF and RFI attacks.

## User Story
**Feature_Name**: Standardised encodings and parsers

**Story**:\
As a Security Engineer\
I want to use consistent encodings and parsers\
So that I can avoid parsing attacks that exploit different behaviour that could be used in RFI and SSRF attacks\

## Scenario
**Scenario_name**: Standardised encodings

**Gherkin syntax**:\
Given a need to encode or escape content
And send it to different services
When I choose a library or framework
Then I vet the library or framework exposure to this weakness

**Scenario_name**: Parameterization of queries

**Gherkin syntax**:\
Given a need to encode or escape content
And send it to different services
When I need to perform queries
Then I use stored procedures or similar to reduce reliance on manual validations


## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet.html
https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html
https://cwe.mitre.org/data/definitions/116
