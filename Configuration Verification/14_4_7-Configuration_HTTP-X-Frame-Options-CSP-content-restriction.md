## ASVS Requirement: V14.4.7 Verify HTTP X-Frame-Options or CSP frame-ancestors restrict content from being embedded in 3rd party sites
## ASVS:14.4.7

## ASVS Requirement description
Verify that a suitable X-Frame-Options or Content-Security-Policy: frame-ancestors header is in use for sites where content should not be embedded in a third-party site.

## User Story
**Feature_Name**: Restrict content from being embedded in 3rd party sites

**Story**:
As a Security Engineer\
I want to restrict where content can be embedded from
So that I can have control over which 3rd parties can embedded content I produce

## Scenario
**Scenario_name**: Ensure X-Frame-Options header is enabled in all HTTP responses

**Gherkin syntax**:
```gherkin
	Given an HTTP response
	And an HTTP Security header
	When confirming existing HTTP headers
	Then X-Frame-Options header is defined
```

**Scenario_name**: Ensure X-Frame-Options header is appropriately configured

**Gherkin syntax**:
```gherkin
    Given an HTTP response
    And an HTTP Security header
    When confirming existing HTTP headers
    Then X-Frame-Options exists
    And is configured for allowing same origin
```
**Scenario_name**: Ensure Content-Security-Policy header and frame-ancestors directive is enabled in all HTTP responses

**Gherkin syntax**:
```gherkin
	Given an HTTP response
	And an HTTP Security header
	When confirming existing HTTP headers
	Then Content-Security-Policy header is defined
```

**Scenario_name**: Ensure Content-Security-Policy header and frame-ancestors directive is appropriately configured

**Gherkin syntax**:
```gherkin
    Given an HTTP response
    And an HTTP Security header
    When confirming existing HTTP headers
    Then X-Frame-Options exists
    And is configured for allowing same origin
```

Bear in mind though, the Content-Security-Policy HTTP header has a `frame-ancestors` directive which obsoletes the X-Frame-Options header for supporting browsers.

You should consider and have done the assesment on the mode and solution you need before using the tests below

## Validations

**Chef Inspec**

```ruby
control 'HTTP Header - X-Frame-Options' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'X-Frame-Options exists'             # A human-readable title
  desc 'HTTP response contains X-Frame-Options'
  tag 'ASVS-14.4.7'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.x-frame-options') { should exist }
  end
end

control 'HTTP Header - X-Frame-Options' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'X-Frame-Options configuration'             # A human-readable title
  desc 'HTTP response contains X-Frame-Options'
  tag 'ASVS-14.4.7'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.x-frame-options') { should exist }
    its('headers.x-frame-options') { should cmp `SAMEORIGIN` }
  end
end
```

```ruby
control 'HTTP Header - CSP with frame-ancestors' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'X-Frame-Options exists'             # A human-readable title
  desc 'HTTP response contains CSP with frame-ancestors'
  tag 'ASVS-14.4.7'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Content-Security-Policy') { should exist }
    its('headers.Content-Security-Policy') { should include `frame-ancestors` }
  end
end
```
**OPA**

TBC

**External Tests**

TBC

**External link**
https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
https://cwe.mitre.org/data/definitions/346
https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options
https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors