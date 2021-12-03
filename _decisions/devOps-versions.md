---
type: decision
acronym: devOps-versions
title: versioning for services
decision_type: must
status: _3_agreed
responsible: tra
deadline: 2021-12-03
priority: 2-medium
aspects:
    - devOps
    - techStack
todos:
    
history:
    v1:
        date: 2021-11-25
        comment: created initially & decided
---

## Why is there need for such a decision?

Each service should use versioning in order to be able to revert a change.

## Additional sources for better understanding the background

* A new version of the service could be broken

## Viable Options

* versioning handled by teams
* versioning handled by devOps



## Alternatives not seriously considered




## How is this decision evaluated?

* team decision


## Resolution Details

* Each team should use a git tag for versioning on ervery realease artifact

## Reasons for the resolution

