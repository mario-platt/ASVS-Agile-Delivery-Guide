## ASVS Requirement: V2.1.9
## ASVS:.2.1.9

## ASVS Requirement description
Verify that there are no password composition rules limiting the type of characters permitted. There should be no requirement for upper or lower case or numbers or special characters.

## User Story
**Feature_Name**: absence of password composition rules

**Story**:
As a Security Engineer\
I want to unrestrict users from password composition rules limiting the types of characters permitted\
So that they can set passwords or passphrases which are memorable to them

## Scenario
**Scenario_name**: absence of password composition rules

**Gherkin syntax**:
```gherkin
Given the setting of a user password
When I validate password strength against my password policy
Then I don't constrain users choice of characters for their password
But I ensure the password is at least 12 characters
```
12 characters is a reference to requirement 2.1.1

From the `SKF`:
A product''s design should require adherance to an appropriate password policy. Specific password requirements depend strongly on contextual factors, but it is recommended to contain the following attributes: Enforcement of a minimum and maximum length Restrictions against password reuse Restrictions against using common passwords Restrictions against using contextual string in the password (e.g., user id, app name) Depending on the threat model, the password policy may include several additional attributes. Complex passwords requiring mixed character sets (alpha, numeric, special, mixed case) Increasing the range of characters makes the password harder to crack and may be appropriate for systems relying on single factor authentication. Unfortunately, a complex password may be difficult to memorize, encouraging a user to select a short password or to incorrectly manage the password (write it down). Another disadvantage of this approach is that it often does not result in a significant increases in overal password complexity due to people''s predictable usage of various symbols. Large Minimum Length (encouraging passphrases instead of passwords) Increasing the number of characters makes the password harder to crack and may be appropriate for systems relying on single factor authentication. A disadvantage of this approach is that selecting a good passphrase is not easy and poor passwords can still be generated. Some prompting may be needed to encourage long unpredictable passwords. Randomly Chosen Secrets Generating a password for the user can help make sure that length and complexity requirements are met, and can result in secure passwords being used. A disadvantage of this approach is that the resulting password or passpharse may be too difficult to memorize, encouraging them to be written down. Password Expiration Requiring a periodic password change can reduce the time window that an adversary has to crack a password, while also limiting the damage caused by password exposures at other locations. Password expiration may be a good mitigating technique when long complex passwords are not desired. See NIST 80063B https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.80063b.pdf Sections: 5.1.1, 10.2.1, and Appendix A for further information on password requirements.

## Validations

**Chef Inspec**

TBC

**OPA**

TBC

**External Tests**

TBC

**External link**\