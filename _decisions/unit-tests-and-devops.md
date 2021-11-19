---
type: decision
acronym: unit-tests-and-devops
title: Unit Tests and DevOps
decision_type: must
status: _3_agreed
responsible: aha;tra;sbe
deadline: 2021-11-19
priority: 1-high
todo:
aspects:
    - devOps
    - qualityAssurance
history:
    v1:
        date: 2021-11-19
        comment: created initially
---

## Why is there need for such a decision?

In the FAE/DDD meeting on 19.11.2021, it was decided that all services must implement unit tests.
As the deployment is handled via devOps and the service should not be deployed if the tests fail,
the unit tests should be run via devOps pipeline.

## Additional sources for better understanding the background

n/a

## Viable Options

The unit tests should be run and validated on the devOps pipeline. If the test fails, the service
won't be deployed.

## Alternatives not seriously considered

The unit tests are run locally before pushing to the repository.

## How is this decision evaluated?

n/a

## Resolution Details

Unit tests must be executed on the pipeline.
Services won't be deployed if their tests fail.
Teams can contact the devOps team for additional
information on how to implement unit tests on the pipeline.

## Reasons for the resolution

Evaluating the unit tests locally is not a good option, because deployment should reliably be prevented if the tests fail.
Furthermore, running unit tests on the pipeline is a best practice.
