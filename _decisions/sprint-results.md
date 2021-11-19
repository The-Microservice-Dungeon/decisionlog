---
type: decision
acronym: sprint-results
title: Sprint results
decision_type: must
status: _2_draft
responsible: psc
deadline: 2021-11-20
priority: 2-medium
todo:
aspects:
    - convention
history:
    v1:
        date: 2021-11-18
        comment: created draft
---

## Why is there need for such a decision?
Currently, the status of the main branch varies across all services. This makes it difficult to estimate how far the services are in the overall development. 

## Additional sources for better understanding the background
[Scrum](https://de.wikipedia.org/wiki/Scrum)

## Viable Options
\-

## Alternatives not seriously considered
\-

## How is this decision evaluated?
\-

## Resolution Details
For the completion of the sprint, all features developed in the sprint are merged into the main branch.

## Reasons for the resolution
A sprint represents an incremental extension of the software, this should also be reflected in the final product. At the end of each sprint there should be a current version in the `main` branch of the repository.