---
type: decision
acronym: unit-testing
title: Unit Testing of Business Logic
decision_type: must
status: _3_agreed
responsible: aha;thu;tra;psc
deadline: 2021-11-19
priority: 1-high
todo:
aspects:
    - qualityAssurance
history:
    v1:
        date: 2021-11-19
        comment: created initially
---

## Why is there need for such a decision?

In one of the last FAE/DDD meetings, it was mentioned that services should be
developed according to Test-Driven Development. This mandates the usage of unit tests.

A decision is needed on what parts of the service should be validated by unit tests.

## Additional sources for better understanding the background

n/a

## Viable Options

- Test only the internal business logic
  - this ensures that the internal data processing works correctly
  - this is probably the most important part of the unit tests
- Also test the API calls
  - this ensures that the API works correctly and that major issues are resolved before the integration test phase
  - consumes additional time and resources

## Alternatives not seriously considered

Some teams have written tests for parts of their tech stack, e.g. Spring or Kafka.
We agreed that this doesn't make any sense.

## How is this decision evaluated?

n/a

## Resolution Details

Teams should implement unit tests for the internal business logic as well as for their API.

## Reasons for the resolution

Implementing unit tests for the internal business logic is the bare minimum.
Unit tests for the APIs require additional time from the teams, but running into major problems during the integration
testing phase would mess up the schedule for the whole project.
Thus, unit tests are required for the APIs as well, so the risk of major hickups at the integration testing
phase is massively reduced.
