# ASVS Requirement: V5.1.5 Verify that URL redirects and forwards only allow whitelisted destinations

## ASVS:5.1.5

## ASVS Requirement description

Verify that URL redirects and forwards only allow whitelisted destinations, or show a warning when redirecting to potentially untrusted content.

## User Story

**Feature_Name**: Safe URL redirects and forwards

**Story**:\
As a Security Engineer\
I want all URL redirects and forwards to only allow whilisted destinations
So that I strictly control where users are redirected when using my application

## Scenario

**Scenario_name**: Enforcement by conversion

**Gherkin syntax**:

```gherkin
Given the need to redirect or forward users to an external URL
When I define the required objects in code
Then I create a mapping between fixed input values to the actual filenames or URLs
And I reject all other inputs
```

"When the set of acceptable objects, such as filenames or URLs, is limited or known, create a mapping from a set of fixed input values (such as numeric IDs) to the actual filenames or URLs, and reject all other inputs. For example, ID 1 could map to /login.asp and ID 2 could map to <http://www.example.com/>. Features such as the ESAPI AccessReferenceMap [REF45] provide this capability." from `SKF`

**Scenario_name**: Notify user of external redirect

**Gherkin syntax**:

```gherkin
Given the need to redirect or forward users to an external URL
When I am about to redirect the users to this external file or URL
Then I provide a warning to the user that they are leaving the current site
And I implement a long timeout before the redirect happens or force the user to click the link
```

**Scenario_name**: Nonce generation for redirect requests

**Gherkin syntax**:

```gherkin
Given the need to redirect or forward users to an external URL
When I am about to redirect the users to this external file or URL
Then my application generates a unique nonce associated with the request
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
<https://cwe.mitre.org/data/definitions/601>
