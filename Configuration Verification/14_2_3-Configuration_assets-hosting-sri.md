# ASVS Requirement: V14.2.3 Assets Hosting and Subresource integrity

## ASVS:14.2.3

## ASVS Requirement description

Verify that if application assets, such as JavaScript libraries, CSS stylesheets or web fonts, are hosted externally on a content delivery network (CDN) or external provider, Subresource Integrity (SRI) is used to validate the integrity of the asset.

## User Story

**Feature_Name**: Validated hashes of external dependencies

**Story**:
As a Security Engineer\
I want to ensure that when I perform integrity checks against the hashes of any external dependencies
So that I confirm that the packages I tested are used and weren't altered

## Scenario

**Scenario_name**: Check all externally downloaded assets are verified with sub-resource integrity

**Gherkin syntax**:

```gherkin
Given an `asset` in my application hosted externally
When I declare the asset in my scripts and links
Then I instruct the browser to perform an integrity check on the asset loaded against a verified hash
```

`asset` in this context, refers to `Javascript libraries`, `CSS stylesheets` and/or `Web fonts`.

This is done through checking `<link rel=` or `<script src=` statements and verifying that `integrity=sha256-*` is set for each of them. An example is

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css" integrity="sha256-8EtRe6XWoFEEhWiaPkLawAD1FkD9cbmGgEy6F46uQqU= sha512-/5KWJw2mvMO2ZM5fndVxUQmpVPqaxZyYRTMrXtrprsyQ2zM0o0NMjU02I8ZJXeBP trmrPO4IAyCCRsydG0BJoQ==" crossorigin="anonymous">
```

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cwe.mitre.org/data/definitions/15>
