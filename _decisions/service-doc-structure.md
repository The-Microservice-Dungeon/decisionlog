---
type: decision
acronym: service-doc-structure
title: Structure for team developer documentation
decision_type: must
status: _3_agreed
responsible: tra;thu
deadline: 2021-10-22
priority: 3-low
aspects: 
    - documentation
history:
    v1:
        date: 2021-10-08
        comment: created initially 
    v2:
        date: 2021-10-19
        comment: took task
    v3:
        date: 2021-11-05
        comment: Add best-pracitices and structure recommendations
    v3:
        date: 2021-11-09
        comment: >
            Add small note about the beta state of AsyncAPI studio
---

## Why is there need for such a decision?

We need to have a common base structure in the developer documentation for each service (what issues need to be 
covered), so that you are sure to find the required aspects. 

## Additional sources for better understanding the background

- n/a

## Viable Options

- see resolution


## Alternatives not seriously considered

- n/a


## How is this decision evaluated?

The decision was evaluated by thinking about the aspects required by each developer team 
to gather informations about the other services.
 
## Resolution Details

In the following sections are some best practices and recommendations

You **MUST** define the following sections:
- **Service:** Describe what your services tasks are and what the boundaries are. 
- **Links:** Provide useful links to external ressources, these may include service-specific documents, ressources, but at least
    - Permalink to the Swagger Editor with your API specification: `https://editor.swagger.io/?url=https://raw.githubusercontent.com/The-Microservice-Dungeon/gamelog/main/docs/api-spec.yaml`
    - Permalink to AsyncAPI Studio or AsyncAPI Playground with your event specification:
        - `https://studio.asyncapi.com/?url=https://raw.githubusercontent.com/The-Microservice-Dungeon/gamelog/main/docs/event-spec.yaml`<br/>
        ⚠️ AsyncAPI Studio is still in beta and was released just a couple days before the writing day of this document. Personally, I experienced some Memory Leaks and would recommend to stick to the playground when **writing** the specification [Open Issue #171](https://github.com/asyncapi/studio/issues/171). In order to view the spec it should be perfectly fine to use AsyncAPI studio.
        - `https://playground.asyncapi.io/?url=https://raw.githubusercontent.com/The-Microservice-Dungeon/gamelog/main/docs/event-spec.yaml`

You **Must** follow the following practices:
- Whenever you are referring to another documentation, section or resource provide a valid link to it


## Reasons for the resolution

- n/a