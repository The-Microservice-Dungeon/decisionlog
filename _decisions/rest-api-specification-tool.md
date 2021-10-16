---
type: decision
acronym: rest-api-specification-tool
title: Tool for specifying REST APIs
decision_type: must
belongs_to: api
status: _2_draft
todos:
responsible: fgr;ngi
deadline: 2021-10-22
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-16
        comment: added reasoning and conclusion for this decision
---

## Why is there need for such a decision?

We need to have one tool to specify and document all APIs, as these must be easy to discover. 

## Additional sources for better understanding the background

Knowledge about the 4 levels of maturity of a REST API ([Richardson Maturity Model](https://developers.redhat.com/blog/2017/09/13/know-how-restful-your-api-is-an-overview-of-the-richardson-maturity-model))

## Viable Options

# Postman
one of the first API documentation tool
able to document the API lifecycle: design, testing, documentation, mocking

# Swagger
offers an editor with syntax auto-completion and error feedback
APIs can be mocked and tested

# OpenAPI
it's an advancement of Swagger (v 2.0 of both tools were exactly the same)
basically the same as Swagger with the newest updates

# Spring REST Docs
Alternative to the other API documentation tools, very close to the other spring tools. Therefore useful if you also use spring for your actualy REST API.
test-driven approach, docu written either as Spring MVC tests, Spring Webflux's _WebTestClient_ or REST-Assured

## Alternatives not seriously considered

Excel tables: they are able to do this job but at a serious loss of readability, they also offer zero functionality for testing/mocking/verification

## How is this decision evaluated?

Postman was one of the first API documentation tools and the others derived their knowledge from it. Swagger became the standard afterwards and is now slowly replaced by OpenAPI, which is basicly the same with the newest updates. 

The Spring REST Docs use documentation in a test-driven approach which is not within the scope of our usage of an API docu tool and may require much more initial training to work with to understand the features we do not need.
 
## Resolution Details

OpenAPI as the most recent generally usable tool which focuses on documentation while also providing an optional mocking feature to test the APIs
[OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification)

## Reasons for the resolution

OpenAPI is not dependent on the usage of any other tools, therefore every context team can use it without technical restrictions. It also offers the functionality we need without laying too much focus on features we do not need (it's not test-driven)

# Sources

[Spring REST Docs](https://spring.io/projects/spring-restdocs#overview)
[Swagger](https://swagger.io/tools/swaggerhub/features/)
[Postman](https://www.postman.com/)

[REST Assured](https://www.guru99.com/rest-assured.html)

