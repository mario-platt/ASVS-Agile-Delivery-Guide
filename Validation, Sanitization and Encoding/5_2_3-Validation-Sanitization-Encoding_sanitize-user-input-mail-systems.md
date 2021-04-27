# ASVS Requirement: V5.2.3 Verify that application sanitizes user input before passing to mail systems (SMTP/IMAP injection)

## ASVS:5.2.3

## ASVS Requirement description

Verify that the application sanitizes user input before passing to mail systems to protect against SMTP or IMAP injection.

For example, a `.` in SMTP signifies the end of mail message data, whereas a `null character` can be used for the end of a string.

## User Story

**Feature_Name**: Sanitization of user input towards mail systems

**Story**:\
As a Security Engineer\
I want to neutralize special elements that could be interpreted as controls elements or syntactic markers when passing information to mail systems
So that I can protect my application from abuse and exploitation

## Scenario

**Scenario_name**: Anticipation of input vectors through whitelisting

**Gherkin syntax**:

```gherkin
Given a need process external requests
When I validate input into my application
Then I anticipate the `special elements` that could be injected
And create a whitelist using regular expressions
And only allow requests which meet the regular expression
```

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
<https://cwe.mitre.org/data/definitions/147>
