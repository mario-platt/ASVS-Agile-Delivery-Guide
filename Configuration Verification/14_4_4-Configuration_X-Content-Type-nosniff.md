## ASVS Requirement: V14.4.4 Verify X-Content-Type-Options as no-sniff
## ASVS:14.4.4

## ASVS Requirement description
Verify that all responses contain X-Content-Type-Options: nosniff.

## User Story
**Feature_Name**: HTTP response prevents browsers from overriding response content type

**Story**:
As a Security Engineer\
I want to ensure only the server-provided Content type is allowed
So that I can prevent MIME-based attacks or MIME sniffing

## Scenario
**Scenario_name**: Secure Content type responses from being modified by server

**Gherkin syntax**:
```gherkin
	Given an HTTP response
	And an HTTP Security header
	When determining Content type options
	Then nosniff is enforced
```

## Validations

**Chef Inspec**

```ruby
control 'HTTP Header - Content Type Options' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Content type Options = no sniff'
  desc 'All responses should contain X-Content-Type-Options=nosniff'
  tag 'ASVS-14.4.4'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('headers.x-content-type-options') { should cmp 'nosniff' } 
  end
end
```

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
https://cwe.mitre.org/data/definitions/116
https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition
