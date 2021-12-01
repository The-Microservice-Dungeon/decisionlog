---
type: decision
acronym: env-vari
title: .env variables for db connections
decision_type: must
status: _3_agreed
responsible: tra
deadline: 2021-11-25
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

All services need to provide us the nessesary information for the db connection

## Additional sources for better understanding the background

tbd

## Viable Options

* .env varables



## Alternatives not seriously considered




## How is this decision evaluated?

* Discussion during team meeting
* resarch other projects
* Docker documentation


## Resolution Details

 Every service needs to create a .env file which contains the needed variables
 The variables will be discribed in our [GitHub Repo](https://github.com/The-Microservice-Dungeon/devops/wiki/Environment-Variables)

## Reasons for the resolution

