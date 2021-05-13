# ASVS Requirement: V14.3.1 Error messages configured to eliminate unintended security disclosures

## ASVS:14.3.1

## ASVS Requirement description

Verify that web or application server and framework error messages are configured to deliver user actionable, customized responses to eliminate any unintended security disclosures.

## User Story

**Feature_Name**: Error messages without exposure of sensitive information

**Story**:
As a Security Engineer\
I want to ensure that error messages are configured or developed without exposing sensitive information
So that I can avoid any unintended security disclosures

## Scenarios

**Scenario_name**: Exception handling internally without sensitive information shown to user

**Gherkin syntax**:

```gherkin
Given an exception triggered in my application
When I handle it and generate associated error messages
Then I ensure that `sensitive information` isn't exposed
```

`sensitive information` may include different elements depending on the use case and specific application. But it will usually include information such as `debugging information`, `personal information`, `banners detailing software versions`, `application tracing information` or any other information that may expose details of the inner workings of the application

**Scenario_name**: Turn off verboseness of error messages (where configurable)

**Gherkin syntax**:

```gherkin
Given an exception triggered in my application
When I generate events from these exceptions
And where I have an ability to configure the verboseness of the error messages
Then I turn off verboseness for that exception
```

**Scenario_name**: Custom default error pages or messages which don't leak sensitive information

**Gherkin syntax**:

```gherkin
Given an exception triggered in my application
When I direct application users to error pages
Then I redirect them to custom default error pages
And ensure these pages don't leak sensitive information 
```

`sensitive information` may include different elements depending on the use case and specific application. But it will usually include information such as `debugging information`, `personal information`, `banners detailing software versions`, `application tracing information` or any other information that may expose details of the inner workings of the application

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

## External links

<https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet.html>
<https://cwe.mitre.org/data/definitions/209>
