# ASVS-Agile-Delivery-Guide

Welcome to the Agile Delivery Guide.

The OWASP ASVS Standard is the de facto application security standard and a wonderful document to support the setting of security requirements.

As much as there's been great work in developing the standard itself, supported by other OWASP Projects such as SAMM, SKF, and OWASP Cheatsheets, we believe a piece that is still largely missing is guidance and open source documentation on how to integrate the delivery of these into Agile delivery methods.

For that reason, we've created this ASVS Agile Delivery Guide which will provide the following for each of the requirements in OWASP ASVS.

- **User Stories** - inclusive of `Feature names` and actual `User Stories` relating to the requirement. For now, they'll be written either as a `Security Engineer` persona (for the purely technical validations) and as `Security Manager` persona for the Governance related validations
- **Scenarios** - inclusive of `Scenario names` and also the related `Gherkin syntax` for the identified scenario.
- **Validations** - there will be a mix of creating content using Policy-as-Code DSLs (such as Chef Inspec or OPA), but also to link into other projects which have already developed validations and exist "scattered" through different open source projects (2 examples would be https://dev-sec.io/baselines/ and https://github.com/BlazingWind/OWASP-ASVS-4.0-testing-guide , among others)

The three main drivers for this initiative are the following:
- Help traditional Compliance teams getting used to framing their requirements as User Stories, so they can be more easily integrated into Agile delivery
- Provide a set of 'off the shelf' stories that can be used and adapted universally
- Help traditional Compliance teams with a route to develop skills in developing security requirements as code, by having clear Scenarios which help inform the structure for a Compliance-as-Code validation

# Repo Structure
The repo will be structured with one folder per ASVS requirement, and within it individual files for each requirement, to make it easy to navigate and with a standard naming convention

# File structure and example

The following structure is to be adhered to for the individual files.

## ASVS Requirement: V14.4 HTTP Security Headers Requirements
## ASVS:14.4.1

## ASVS Requirement description
Verify that every HTTP response contains a Content-Type header. text/*, /+xml and application/xml content types should also specify a safe character set (e.g., UTF-8, ISO-8859-1).

## User Story
**Feature_Name**: HTTP Response content type header specifies safe character set

**Story**:\
As a Security Engineer\
I want to allow safe character sets only in HTTP responses\
So that I can prevent obfuscation attacks that could hide malicious input\

## Scenario
**Scenario_name**: Specify allowed character sets

**Gherkin syntax**:
Given an HTTP response\
And an HTTP Security header\
When specifying allowable character sets\
Then only allow UTF-8 or ISO-8859-1

## Validations

**Chef Inspec**

```ruby
control 'HTTP Header - Content type' do                        # A unique ID for this control\
  impact 0.7                                # The criticality, if this control fails.\
  title 'Safe character set'             # A human-readable title\
  desc 'HTTP response contains content type header with safe character set'\
  tag 'ASVS-14.4.1'\
  tag 'ISO27001-14.1.2'\
  describe http('http://192.168.0.6:3000') do                  # The actual test\
    its('headers.Content-type') { should cmp 'text/html; charset=utf-8' }\
  end\
end\
```

**OPA**

TBC

**External link**
insert URL
