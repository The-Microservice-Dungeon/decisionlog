---
type: decision
acronym: dependency-graph
title: Dependency graph for the overall service landscape
decision_type: should
status: _2_draft
priority: 3-low
responsible: sbe;cpo
aspects: 
    - model
todos:
    - (sb) finalize description
deadline: 2021-10-22
history:
    v1:
        date: 2021-10-21
        comment: created initially
    v2:
        date: 2021-10-22
        comment: made into a new decision (sb)          
---

## Why is there need for such a decision?

We need to know which services are allowed to call which other services by synchronous call, in order to avoid
cyclic dependencies.

## Additional sources for better understanding the background

n/a

## Viable Options

n/a

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Discussion in the DDD/FAE workshops, resolution of conflicts between services.
 
## Resolution Details

This is this the current model. Currently, there are five services (Game, Robot, Map, Trading, GameLog). The model will be
iteratively updated as discussions clear up the responsibilities. 

![Subdomain-Model-v1](./images/subdomain-model_v1.png "Subdomain-Model-v1")

## Reasons for the resolution

tbd.

