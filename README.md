# FUTURE_CS_03

# Cyber Security Task 3 – API Security Risk Analysis

## About the Project

This project was completed as part of **Future Interns Cyber Security Task 3 – API Security Risk Analysis**.

The objective was to perform a **read-only security assessment** of public/demo APIs and identify common API security risks while documenting the findings in a professional security report.

## APIs Tested

### JSONPlaceholder

https://jsonplaceholder.typicode.com

### ReqRes

https://reqres.in

The APIs were selected because they are public/demo services intended for API testing and learning.

## Tools Used

* Postman
* Kali Linux
* Terminal
* Microsoft Word
* PDF documentation

## Scope

The assessment was limited to selected public/demo API endpoints.

Testing included:

* GET requests
* Authentication requirement checks
* Response and header inspection
* Access-control observations
* Invalid-input handling
* HTTP/HTTPS transport behavior
* Rate-limit indicators

### Out of Scope

The following activities were not performed:

* Credential guessing
* Authentication bypass
* Exploitation
* POST/PUT/PATCH/DELETE testing
* Flooding or DoS testing
* Automated enumeration
* Testing private or production systems

## Methodology

The assessment followed a controlled read-only approach:

1. Select public/demo APIs.
2. Review the available API documentation.
3. Configure API requests in Postman.
4. Send selected GET requests.
5. Inspect HTTP status codes and response bodies.
6. Inspect response headers.
7. Check authentication requirements.
8. Observe access-control behavior.
9. Test controlled invalid identifiers.
10. Review transport security behavior.
11. Review available rate-limit indicators.
12. Classify identified risks.
13. Document business impact and remediation recommendations.

## Security Areas Reviewed

The assessment considered the following API security risks:

* Open or unauthenticated endpoints
* Excessive data exposure
* Weak or missing authentication
* Authorization and potential BOLA risks
* Rate limiting
* Input validation
* Security headers and technology disclosure
* HTTP/HTTPS transport protection

## Key Findings

### F01 – API Data Served Over HTTP

**Severity:** Low

The assessment observed that a JSONPlaceholder endpoint returned API data over HTTP when redirects were disabled.

This was assessed as a transport-security weakness in the context of the public test API.

**Recommendation:**

* Enforce HTTPS-only access.
* Use HTTPS URLs as the standard API base URLs.
* Maintain proper certificate validation.
* Consider HSTS where appropriate.

### F02 – Header Information / Technology Disclosure

**Severity:** Low

Response headers exposed technology/framework-related information that could provide unnecessary implementation details.

**Recommendation:**

* Remove optional technology-identifying headers where practical.
* Review error responses for unnecessary implementation details.
* Avoid exposing internal infrastructure information.

## Positive Security Observations

### Missing API Key Rejected

The ReqRes protected endpoint rejected a request without the required API key and returned a `401` response.

### Invalid IDs Returned Controlled Errors

Invalid/non-existent user identifiers returned controlled `404` responses rather than exposing unexpected data.

## Limitations

This assessment was intentionally limited to selected read-only GET requests against public/demo APIs.

No valid credentials, private accounts, source code, backend configuration, application logs, dependency review, or full TLS configuration audit were available.

Therefore, the assessment does not claim that the APIs are completely secure or completely insecure.

## Evidence

The `Screenshots/` directory contains the Postman evidence used during the assessment.

The evidence is numbered **E01–E19** to correspond with the evidence register in the security report.

## Report

The complete security assessment is available in:

`Report/API_Security_Risk_Analysis.pdf`

## Disclaimer

This assessment was conducted only against public/demo APIs within the permitted scope of the Future Interns Cyber Security Task 3.

No unauthorized exploitation, credential attacks, DoS testing, or testing of private/production systems was performed.

## Author

**R Aniruthvishwak**

Cyber Security Student
Future Interns – Cyber Security Task 3
