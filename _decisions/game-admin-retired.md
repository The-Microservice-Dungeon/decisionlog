---
type: decision
acronym: game-admin-retired
title: Admins are retired in Game Service
decision_type: must
service: game
status: _3_agreed
responsible: fgr;mba
deadline: 
priority: 2-medium
aspects: 
    - api
todo:
history:
    v1:
        date: 2021-12-02
        comment: created initially
---

## Why is there need for such a decision?

At the beginning of the project it was decided to add admin properties to the game service.

## Additional sources for better understanding the background

In the further course it turned out there is no need of such information. 

## Viable Options

Deleting the admin properties from the async api. In addition one developer has gone out who should implement this. 

## Alternatives not seriously considered

The developers implement the open issue which would results in more workload for them.

## How is this decision evaluated?

In the Sprint planning with the Team and supervisor.

## Resolution Details

The admin properties from the async api are deleted.
