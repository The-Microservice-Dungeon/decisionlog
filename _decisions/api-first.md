---
type: decision
acronym: api-first
title: APIs are specified in "API first" style
decision_type: must
status: _3_agreed
responsible: sbe
deadline: 2021-10-22
priority: 1-high
aspects:
    - principle
    - api
todos:
    - ausformulieren
history:
    v1:
        date: 2021-10-08
        comment: created initially
---

## Resolution Details

We follow an API-first strategy in the project: First specify the API, then implement it. 

## Why is there need for such a decision?

In a distributed environment, APIs are the main point of interaction. Their implementation style - first the API
spec, or first the service? - need to be determined right away.

## Reasons for the resolution

The whole project is API-driven, as the robot service will have to implement against the APIs. Therefore, the
APIs need to be done first.

## Additional sources for better understanding the background

n/a

## Viable Options

n/a

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

n/a


