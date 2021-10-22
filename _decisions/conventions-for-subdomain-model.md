---
type: decision
acronym: conventions-for-subdomain-model
title: Conventions how to document (sub-)domain models in the teams
decision_type: should
belongs_to: model
status: _2_draft
priority: 3-low
responsible: cpo
tags: 
    - subdomain-model
    - documentation
todos:
    - (sb) Misunderstanding - this decision is about _conventions_ how to document domain models.
    - (sb) Text could be kept and re-labelled "Dependency Graph for all Dungeon services"
deadline: 2021-10-22
history:
    v1:
        date: 2021-10-21
        comment: created initially
    v2:
        date: 2021-10-21
        comment: created first draft          
---

## Why is there need for such a decision?

Team subdomain models are very important information for understanding purpose and APIs of a service. There 
must be some conventions and standards (which tool(s), which notation, what information should be visible ...) 
in order to compare the models. 

## Additional sources for better understanding the background

* tbd

## Viable Options

### Current Model
[Subdomain-Model-v1](./images/subdomain-model_v1.png "Subdomain-Model-v1")

This is this the current model. Currently, there are five services (Game, Robot, Map, Trading, GameLog). The model will be
iteratively updated as discussions clear up the responsibilities.

#### Game
//TODO: Explain responsibilities and ownership of aggregates
#### Robot
//TODO: Explain responsibilities and ownership of aggregates
#### Map
//TODO: Explain responsibilities and ownership of aggregates
#### Trading
//TODO: Explain responsibilities and ownership of aggregates
#### GameLog
//TODO: Explain responsibilities and ownership of aggregates

## Alternatives not seriously considered

* tbd


## How is this decision evaluated?

tbd
 
## Resolution Details

tbd

## Reasons for the resolution

tbd

