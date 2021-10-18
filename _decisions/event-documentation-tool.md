---
type: decision
acronym: event-documentation-tool
title: Tool for specifying and documenting events
decision_type: must
belongs_to: api
status: _1_open
todos:
responsible: thu;tla;tpa;
deadline: 2021-10-22
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-14
        comment: > 
            add first thoughts about the possible options and decision evaluation
---

## Why is there need for such a decision?

We need to have one tool to specify and document all domain events, as services need to start implementing them soon. 

## Additional sources for better understanding the background

- [Schema and Topic Design in Event-Driven Systems (featuring Kafka!)](https://medium.com/flippengineering/schema-and-topic-design-in-event-driven-systems-featuring-kafka-a555ddfdb8d8)
- [Zalando API Guidelines: Events](https://opensource.zalando.com/restful-api-guidelines/#events)
- [CloudEvents](https://cloudevents.io/)

## Viable Options

- [AsyncAPI](https://www.asyncapi.com/)
- [OpenAPI/Swagger](https://swagger.io/specification/) or plain [JSON Schema](https://json-schema.org/) *(just specify the payload)*

## Alternatives not seriously considered

- Informal description for event and payload with e.g. Markdown

An informal description - especially for the event payloads - is not a sufficient way of specifying events. This method won't adapt well 
to changes and lacks in the tooling. For example the defined schema would not be checked for syntactically correctness.

## How is this decision evaluated?

- AsyncAPI 
    - There are [examples given](https://github.com/asyncapi/spec/tree/master/examples) in the corrisponding project repository.
      These examples are evaluated whether they may fit into the microservice dungeon project regarding their features, opportunities and complexity.
    - Available Tooling and technical compatibility
- OpenAPI/Swagger 
    - Approach would only define the payload schemas as JSON Schema Objects. This approach can be evaluated using the examples above (AsyncAPI schemas are [compatible to OpenAPI](https://www.asyncapi.com/docs/getting-started/coming-from-openapi) schemas).
 
## Resolution Details

tbd

## Reasons for the resolution

tbd
