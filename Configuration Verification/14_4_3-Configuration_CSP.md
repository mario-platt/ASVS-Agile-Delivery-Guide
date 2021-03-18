## ASVS Requirement: V14.4.3 Verify Content Security Policy is in place
## ASVS:14.4.3

## ASVS Requirement description
Verify that a content security policy (CSPv2) is in place that helps mitigate impact for XSS attacks like HTML, DOM, JSON, and JavaScript injection vulnerabilities.

## User Story
**Feature_Name**: Implemented Content Security Policy

**Story**:
As a Security Engineer\
I want to define a Content Security Policy in my web application
So that I constrain my exposure to attacks such as XSS or Injection vulnerabilities

## Scenario
**Scenario_name**: Define Content Security Policy as HTTP header

**Gherkin syntax**:
```gherkin
Given an HTTP response
And an HTTP Security header
When identifying the use case for the content of the document
Then I add a Content-Disposition header
And constrain it to the `use case` if refers to
```

The typical `use case`s are `inline` for when content is expected to be presented inline on a webpage or `attachment` or `attachment; filename="name.jpg"` for when the content relates to an attachment

Notes: Chrome, and Firefox 82 and later, prioritize the HTML <a> element's download attribute over the Content-Disposition inline parameter (for same-origin URLs). Earlier Firefox versions prioritize the header and will display the content inline

## Validations

**Chef Inspec**

```ruby
control 'HTTP Header - Content Security Policy' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Content Security Policy'             # A human-readable title
  desc 'HTTP response contains Content Security Policy in header'
  tag 'ASVS-14.4.3'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Content-Security-Policy') { should exist }
  end
end

control 'HTTP Header - Content Security Policy' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Content Security Policy'             # A human-readable title
  desc 'HTTP response contains Content Security Policy as http-equiv meta tag (useful for CDNs)'
  tag 'ASVS-14.4.3'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('body') { should include 'http-equiv="Content-Security-Policy"' }
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
