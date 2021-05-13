# ASVS Requirement: V14.4.6 Verify HTTP Strict Transport Security exists and is configured appropriately

## ASVS:14.4.6

## ASVS Requirement description

Verify that a suitable "Referrer-Policy" header is included, such as "no-referrer" or "same-origin".

## User Story

**Feature_Name**: Referrer-Policy configured to control extent to which sensitive information can be forwarded

**Story**:
As a Security Engineer\
I want to ensure that I enable Referrer-Policy
So that I can control how much referrer information, which may be sensitive, is included with requests

## Scenario

**Scenario_name**: Ensure Referrer-Policy header is enabling in all HTTP responses

**Gherkin syntax**:

```gherkin
 Given an HTTP response
 And an HTTP Security header
 When confirming existing HTTP headers
 Then Referrer-Policy header is defined
```

**Scenario_name**: Ensure Referrer-Policy header is appropriately configured

**Gherkin syntax**:

```gherkin
    Given an HTTP response
    And an HTTP Security header
    When confirming existing HTTP headers
    Then Referrer-Policy exists
    And is configured acccording to identified needs
```

Bear in mind though, that when`Referrer-Policy` header is undefined, it defaults to `strict-origin-when-cross-origin` which is a safe setting which sends origin, path and query strings when it'a a same-origin request, and sends only origin when protocol level stays the same (HTTPS to HTTPS), but does not send the header to less secure destinations (HTTPS to HTTP). Other possible values are `no-referrer`,`no-referrer-when-downgrade`,`origin`,`origin-when-cross-origin`,`same-origin`,`strict-origin` and `unsafe-url` which should generally be avoided as it sends all available information.

You should consider and have done the assesment on the mode you need, prior to integrating the tests suggested below

## Validations

### Chef Inspec

```ruby
control 'HTTP Header - Referrer-Policy' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Referrer-Policy exists'             # A human-readable title
  desc 'HTTP response contains Referrer-Policy'
  tag 'ASVS-14.4.6'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Referrer-Policy') { should exist }
  end
end

control 'HTTP Header - Referrer-Policy' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Referrer-Policy configuration'             # A human-readable title
  desc 'HTTP response contains Referrer-Policy'
  tag 'ASVS-14.4.6'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Referrer-Policy') { should exist }
    its('headers.Referrer-Policy') { should cmp `same-origin` }
  end
end
```

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html>
<https://cwe.mitre.org/data/definitions/116>
<https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy>
