# ASVS Requirement: V14.4.5 Verify HTTP Strict Transport Security exists and is configured appropriately

## ASVS:14.4.5

## ASVS Requirement description

Verify that HTTP Strict Transport Security headers are included on all responses and for all subdomains, such as Strict-Transport-Security: max-age=15724800; includeSubdomains.

## User Story

**Feature_Name**: HTTP response prevents client exposure to transmission of sensitive information unencrypted

**Story**:
As a Security Engineer\
I want to ensure that I enable Strict Transport security
So that I can prevent exposure to man-in-the-middle attacks suh as protocol downgrade or cookie hijacking

## Scenario

**Scenario_name**: Ensure Strict Transport security is enabled on all HTTP responses

**Gherkin syntax**:

```gherkin
 Given an HTTP response
 And an HTTP Security header
 When confirming existing HTTP headers
 Then Strict-Transport-Security exists
```

**Scenario_name**: Ensure Strict Transport security is appropriately configured

**Gherkin syntax**:

```gherkin
Given an HTTP response
And an HTTP Security header
When confirming existing HTTP headers
Then Strict-Transport-Security exists
And is configured with a maximum age
And includes sub-domains
```

## Validations

### Chef Inspec

```ruby
control 'HTTP Header - Strict-Transport-Security' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Strict-Transport-Security exists'             # A human-readable title
  desc 'HTTP response contains Strict-Transport-Security'
  tag 'ASVS-14.4.5'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Strict-Transport-Security') { should exist }
  end
end

control 'HTTP Header - Strict-Transport-Security' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Strict-Transport-Security configuration'             # A human-readable title
  desc 'HTTP response contains Strict-Transport-Security'
  tag 'ASVS-14.4.5'
  tag 'ISO27001-14.1.2'
  describe http('$URL') do                  # The actual test
    it('headers.Strict-Transport-Security') { should exist }
    its('headers.Strict-Transport-Security') { should include `max-age` }
    its('headers.Strict-Transport-Security') { should include  `includeSubDomains`}
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
<https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition>
