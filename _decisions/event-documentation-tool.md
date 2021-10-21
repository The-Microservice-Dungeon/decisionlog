---
type: decision
acronym: event-documentation-tool
title: Tool for specifying and documenting events
decision_type: must
belongs_to: api
status: _2_draft
todos:
responsible: thu;tla;tpa;
deadline: 2021-10-22
priority: 2-medium
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-14
        comment: > 
            add first thoughts about the possible options and decision evaluation
    v3:
        date: 2021-10-21
        comment: >
            make decision to use AsyncAPI as the preferred way to document events
---

## Why is there need for such a decision?

We need to have one tool to specify and document all domain events, as services need to start implementing them soon. 

## Additional sources for better understanding the background

- [Schema and Topic Design in Event-Driven Systems (featuring Kafka!)](https://medium.com/flippengineering/schema-and-topic-design-in-event-driven-systems-featuring-kafka-a555ddfdb8d8)
- [Zalando API Guidelines: Events](https://opensource.zalando.com/restful-api-guidelines/#events) 
- [CloudEvents](https://cloudevents.io/) <sub>(Event schema developed by the CNCF)</sub>
- [ARE YOU AN API ARCHITECT? APPLY THESE STANDARDS FOR DEFINING EVENT-DRIVEN AND RESTFUL APIS](https://vedcraft.com/architecture/standards-for-defining-event-driven-and-restful-apis/)

## Viable Options

- [AsyncAPI](https://www.asyncapi.com/)
- [OpenAPI/Swagger](https://swagger.io/specification/) or plain [JSON Schema](https://json-schema.org/) *(just specify the payload)*

## Alternatives not seriously considered

### Informal description for event and payload with e.g. Markdown

An informal description - especially for the event payloads - is not a sufficient way of specifying events. This method won't adapt well 
to changes and lacks in the tooling. For example the defined schema would not be checked for syntactically correctness.

### UML
The main goal of UML is to present complex issues and interactions in a clear and concise manner. One of the many possibilities that UML offers for modeling system architectures is the possibility to model events and interactions within a system.
To document the events in the system being developed, sequence diagramms would be appropiate. This makes it possible to define the communication flow within the system and, for example, to distinguish between synchronous and asynchronous messages.
However, UML is best at modeling object-oriented systems. Modeling a distributed system with multiple services and the communication could quickly become to complex. In addition, it could be difficult to define the exact form of the messages sent in UML.

## How is this decision evaluated?

To evaluate, which of the two viable options to choose, both were examinated in detail. Informations and previews on both tools:
- AsyncAPI 
    - There are [examples given](https://github.com/asyncapi/spec/tree/master/examples) in the corrisponding project repository.
      These examples are evaluated whether they may fit into the microservice dungeon project regarding their features, opportunities and complexity.
    - Available tooling and technical compatibility
    - Using a hands-on example: [Specification documentation as HTML](https://tobi6112.github.io/AsyncAPI-Sample/) and the corresponding [Repository](https://github.com/tobi6112/AsyncAPI-Sample)
- OpenAPI/Swagger 
    - Approach would only define the payload schemas as JSON Schema Objects. This approach can be evaluated using the examples above (AsyncAPI schemas are [compatible to OpenAPI](https://www.asyncapi.com/docs/getting-started/coming-from-openapi) schemas).
 
## Resolution Details

Both of the Options are considered viable solutions for documenting Events. In direct comparison **AsyncAPI** seems to be the better Option for the purpose of this project.

## Reasons for the resolution
**Industry Standard**
AsyncAPI is [becoming the Industry Standard for defining asynchronous APIs](https://vedcraft.com/architecture/standards-for-defining-event-driven-and-restful-apis/). This brings the advantage, that developers have a high chance of beeing familiar with the tool.

**Machine Readable**
AsyncAPI is written in a machine-readable format and can be read by machines using [parsers](https://www.asyncapi.com/tools/parsers). Due to this fact it is also possible to generate code from the specfication and validate the syntactical correctness.

**Code Generation**
Just like OpenAPI there is a [Code Generation Tool](https://www.asyncapi.com/tools/generator) available to generate boilerplate code from the specification.
Especially useful is the HTML & Markdown generator, so that it is possbile to use the Specification as a documentation source.

In Addition it is possible to generate code using Kafka for:
- Node.js (Hermes)
- Java (Spring / Spring Cloud)

While above generators are capable of generating the whole application with [Modelina](https://www.asyncapi.com/tools/modelina) it is also possible to generate only model definitions for:
- Java
- TypeScript
- JavaScript
- Go
- C#

**Versioning (Evolving API)**
AsyncAPI allows versioning the specification and therefore is able to monitor changes to the specification.

**Compatible to OpenAPI**
In order to use the AsyncAPI spec it is not necessary to learn new syntax for the schema definition, since it is compatible and interchangeable to OpenAPI, which is used for the REST-API Specification

**Technolgy Agnostic**
Even if we're using Kafka it is also possible to specify events using other platforms and therefore worth the experience.
