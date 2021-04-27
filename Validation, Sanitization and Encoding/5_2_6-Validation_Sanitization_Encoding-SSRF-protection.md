# ASVS Requirement: V5.2.6 Verify that application protects against SSRF attack, by validating and sanitising untrusted data

## ASVS Requirement description

Verify that the application protects against SSRF attacks, by validating or sanitizing untrusted data or HTTP file metadata, such as filenames and URL input fields, use whitelisting of protocols, domains, paths and ports.

## User Story

**Feature_Name**: Sanitization of user input

**Story**:\
As a Security Engineer\
I want to validate or sanitize untrusted data or HTTP file metadata
So that I can reduce exposure to Server Side Request Forgery attacks

## Scenario

**Scenario_name**: Validation of untrusted data or HTTP file metadata

**Gherkin syntax**:

```gherkin
Given the processing of HTTP requests
And parameters being passed relating to the retrieval of externally hosted content
When I sanitise or validate the request
Then I ensure it is being sent to the expected destination
```

"By providing URLs to unexpected hosts or ports, attackers can make it appear that the server is sending the request, possibly bypassing access controls such as firewalls that prevent the attackers from accessing the URLs directly. The server can be used as a proxy to conduct port scanning of hosts in internal networks, use other URLs such as that can access documents on the system (using file://), or use other protocols such as gopher:// or tftp://, which may provide greater control over the contents of requests." from `SKF`

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html> \
<https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html> \
<https://cwe.mitre.org/data/definitions/918>
