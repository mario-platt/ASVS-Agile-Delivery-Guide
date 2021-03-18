## ASVS Requirement: V14.4.2 API responses contain Content-disposition
## ASVS:14.4.2

## ASVS Requirement description
Verify that all API responses contain Content-Disposition: attachment; filename="api.json" (or other appropriate filename for the content type).

## User Story
**Feature_Name**: HTTP response defines how content can be displayed

**Story**:
As a Security Engineer\
I want to define Content-disposition in my API responses
So that I constrain how the content is interpreted and processed by browsers

## Scenario
**Scenario_name**: Validate Content-Disposition is defined for the scope

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
control 'HTTP Header - Content Disposition' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Content disposition restriction'             # A human-readable title
  desc 'HTTP response Content-Disposition header with inline'
  tag 'ASVS-14.4.2'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('headers.Content-Disposition') { should cmp 'inline' }
  end
end

control 'HTTP Header - Content Disposition' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Content Disposition restriction'             # A human-readable title
  desc 'HTTP response Content-Disposition header with attachment and specifies file name'
  tag 'ASVS-14.4.2'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    its('headers.Content-Disposition') { should cmp 'attachment; filename=' }
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
