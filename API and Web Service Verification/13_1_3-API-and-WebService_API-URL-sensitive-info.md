# ASVS Requirement: V13.1.3 API URLs don't expose sensitive info

## ASVS:13.1.3

## ASVS Requirement description

Verify API URLs do not expose sensitive information, such as the API key, session tokens etc.

## User Story

**Feature_Name**: Protection of sensitive information in API URLs

**Story**:\
As a Security Engineer\
I want to verify that sensitive information isn't exposed in API URLs\
So that I can protect this information from unauthorised disclosure

## Scenario

**Scenario_name**: Use POST method to transmit sensitive information

**Gherkin syntax**:

```gherkin
Given a need to process `sensitive information` which could expose access credentials
When I transmit this `sensitive information`
Then I use a POST method so this information isn't exposed in URLs
```

`sensitive information` can include API keys, Session Tokens, username and password pairs, etc

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet.html>
<https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html>
<https://cwe.mitre.org/data/definitions/598>
