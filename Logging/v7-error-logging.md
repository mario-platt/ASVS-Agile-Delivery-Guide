# Application log requirements

```gherkin
As an application Owner
I want the applicaton to log events
So that incident detection and response can be triggered
```

## Scenario 1: Unexpected Input / security sensitive error

### 7.4.1

```gherkin
GIVEN an application receives unexpected input
WHEN an error occurs
THEN log event with a unique ID for support personnnel to investigate
```

## Scenario 2

### 7.4.2

7.4.2  Verify that exception handling (or a functional equivalent) is used across the codebase to account for expected and unexpected error conditions.

## Scenario 3

### 7.4.3

7.4.3  Verify that a "last resort" error handler is defined which will catch all unhandled exceptions.
