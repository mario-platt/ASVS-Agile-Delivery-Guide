## ASVS Requirement: V14.4.1 HTTP Content type header specifies safe character set
## ASVS:14.4.1

## ASVS Requirement description
Verify that every HTTP response contains a content type header specifying a safe character set (e.g., UTF-8, ISO 8859-1).

## User Story
**Feature_Name**: HTTP response content type header specifies safe character set

**Story**:
As a Security Engineer\
I want to allow only safe character sets in HTTP responses
So that I can prevent unsafe character sets which could obfuscate malicious activity

## Scenario
**Scenario_name**: Specify allowed character sets

**Gherkin syntax**:
```gherkin
Given an HTTP response
And an HTTP Security header
When specifying allowable character sets
Then only UTF-8 OR ISO 8859-1 should be allowed
```

This would entail expecting the following in HTTP headers
`text/html; charset=utf-8`
`text/html; charset=iso-8859-1`

## Validations

**Chef Inspec**

```ruby
control 'HTTP Header - Content type' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Safe character set'             # A human-readable title
  desc 'HTTP response contains content type header with safe character set'
  tag 'ASVS-14.4.1'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('headers.Content-type') { should cmp 'text/html; charset=utf-8' }
  end
end

control 'HTTP Header - Content type' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Safe character set'             # A human-readable title
  desc 'HTTP response contains content type header with safe character set'
  tag 'ASVS-14.4.1'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('headers.Content-type') { should cmp 'text/html; iso-8859-1' }
  end
end
```

**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
https://cwe.mitre.org/data/definitions/173