# V12: File and Resources Verification Requirements

## V12.1 File Upload Requirements

```gherkin
AS a Product Owner

I want restrictions set on the files which can be uploaded to the application

So that the application doesn't run out of resources to process the uploaded files.
```

## Scenario 1 : Do not accept large files

### 12.1.1

```gherkin
GIVEN the application has file upload capability
AND a maximum file size for uploaded files is defined  
WHEN a file of size larger than the maximum defined size is uploaded into the application  
THEN the file upload fails
AND and error message is displayed to that effect.
```

## Scenario 2 : Verify compressed files

### 12.1.2

```gherkin
GIVEN the application has a file upload capability  
AND a maximum file size for file is defined  
WHEN a compressed file is uploaded in to the application  
AND the file is being decompressed  
AND the decompressed file exceeds the maximum permissible file size  
THEN file decompression activity stops  
AND the decompressed file is discarded
```

## Scenario 3 : Restriction for the number of files per user

### 12.1.3

```gherkin
GIVEN the application has a file upload capability  
AND a maximum file size for file is defined  
AND a maximum number of files per user is defined  
WHEN  a user uploads files in excess of what is permitted per use
THEN  the file upload fails  
```

## File Integrity Requirements

### 12.2.1

## Scenario 1 : validate file type

```gherkin
GIVEN the application has a file upload capability  
AND the expected file types are known based on the file content
WHEN the files are uploaded in to the application  
THEN the upload fails if the expected file content does not match the uploaded file content.  
```

## File execution requirements

```gherkin
AS the product owner
I want the application to securely handle files
SO that the application is hardened against cybersecurity attacks  
```

## Scenario 1 : protect against path traversal

### 12.3.1

```gherkin
GIVEN the application accesses a file during its operation
AND the filename is dynamically built with parameters that the user can control
AND the filename is normalized
AND the normalized filename is not identical to the dynamically build filename
WHEN a specially crafted request is sent to the server e.g. ``../../../etc/passwd`` instead of ``bob``
THEN the request fails
AND an entry is logged with relevant information to the use case
```

## Scenario 2 : prevent disclosure or changes to local files

### 12.3.2

```gherkin
GIVEN the application has file uploaded capability  
WHEN a file is uploaded to the application  
THEN the file name is ignored
AND replaced with an application generated file name  
```

## Scenario 3 : prevent disclosure or execution of files

### 12.3.3

```gherkin
GIVEN the application has file upload capability  
AND the user submitted file names are validated or ignored  
WHEN a request to remotely execute or disclose the file is made to the application  
THEN the request is not serviced.  
```

## Scenario 5 : Prevent OS command injection

### 12.3.5

```gherkin
GIVEN the application has file upload capability  
AND the user provided file metadata is not used in the application API  
AND the user provided file metadata is not used in the application libraries
WHEN an OS command injection request is received
THEN the request is not serviced  
```

## Scenario 6 : prevent execute functionality from un-trusted sources

### 12.3.6

```gherkin
GIVEN the application supports execute functionality  
AND the trusted Content Distribution Networks for the application are known  
AND the trusted javascript libraries for the application are known  
AND the trusted node npm libraries for the application are known  
AND the trusted server side DLLs for the application are known  
WHEN a request to execute is received from an un-trusted source
THEN the request is not serviced  
```

## V12.4 File Storage Requirements

```gherkin
AS a product owner  
I want the files uploaded to the application to be handled securely
SO as to reduce the risk of cyber attacks using files as vector.
```

## Scenario 1 : un-trusted file storage

### 12.4.1

```gherkin
GIVEN the application has file upload capability  
WHEN a file is uploaded in to the application  
THEN the file is stored outside the web root  
AND the file has limited permissions  
AND the file is validated  
```

## Scenario 2 : malware scan for uploaded files

### 12.4.2

```gherkin
GIVEN the application has file uploaded capability  
AND content inspection is enabled at the SGRE network infrastructure  
OR SGRE managed malware inspection is enabled at the file origin
WHEN a malware infected file is uploaded in to the application
THE the upload fails  
```

## V12.5 File Download Requirements

```gherkin
AS a product owner  
I want the application to securely handle requests to uploaded files  
SO that the application is less prone to information disclosure attacks  
```

## Scenario 1 : restricted file serving

### 12.5.1

```gherkin
GIVEN files can be downloaded from the application  
WHEN  a file download request is placed by the client  
AND the requested file is a backup file (eg: .bak) or temporary working file (eg: .swp) or compressed files (eg: .zip, .tzr.gz)
THEN the request is denied  
```

## Scenario 2 : restricted access to uploaded files

### 12.5.2

```gherkin
GIVEN  the application as file upload capability  
AND files are uploaded to the application
WHEN a request is placed by the client on the uploaded file  
AND the request is received as HTML or Javascript content  
THEN the request is denied  
```

## Scenario 3 : prevent reflective file download

### 12.5.3

```gherkin
GIVEN the application has file upload capability  
AND the user submitted filename is ignored or validated  
AND the response content-type header is set to text/plain  
AND the content disposition has a fixed name  
WHEN reflected file download is attempted by a user
THEN the request fails  
```

## V12.6 SSRF Protection Requirements

```gherkin
AS a product owner  
I want applications to speak to whitelisted destinations  
SO that the application is less prone to Server-side request forgery attacks  
```

## Scenario 1 : whitelisted request destinations

### 12.6.1

```gherkin
GIVEN a whitelist of resources and systems an application can send requests is configured
WHEN a request is made by the application to a destination not in the whitelist  
THEN the request is dropped
```
