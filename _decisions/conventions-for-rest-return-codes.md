---
type: decision
acronym: conventions-for-rest-return-codes
title: Conventions for REST return codes and error handling
decision_type: must
belongs_to: api
status: _1_open
responsible: mba
deadline: 2021-10-29
priority: 3-low
tags:
    - basic-principle
todos:
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-18
        comment: took decision
    v3:
        date: 2021-10-21
        comment: decision explained
---

## Why is there need for such a decision?

This should be uniform across the REST APIs because the response to a request no matter which service is involved 
should be clear.

## Additional sources for better understanding the background

[Best Practices for REST API Error Handling](https://www.baeldung.com/rest-api-error-handling-best-practices)

## Viable Options

* HTTP status codes are defacto standard for REST calls.

## Alternatives not seriously considered

* tbd

## How is this decision evaluated?

No evaluation needed.

 
## Resolution Details

#### 200 - OK
#### 300 - Redirection
#### 400 - Bad Request
#### 401 - Unauthorized
#### 500 - Internal Server Error

## Reasons for the resolution

The best practices for REST error handling are HTTP response messages. 
HTTP Status Codes are clear defined in [RFC 2616](https://www.ietf.org/rfc/rfc2616.txt).
