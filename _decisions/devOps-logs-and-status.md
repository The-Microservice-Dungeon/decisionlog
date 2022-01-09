---
type: decision
acronym: devOps-logs-and-status
title: Logs and Status
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

we need a general procedure to check if a service is offline and which errors it writes to the log 

## Additional sources for better understanding the background

tbd

## Viable Options

* Pings and reading logs from a public folder in the docer container
* All services provide two GET Methods (/status & /logs) which proide the needed data


## Alternatives not seriously considered




## How is this decision evaluated?

* Discussion during team meeting
* resarch other projects


## Resolution Details

 Every service provides two routes (/status & /logs) which provide the service status (e.g. running) and all log data.
 The needed payload for this mehtods will be discribed in our [GitHub Repo](https://github.com/The-Microservice-Dungeon/devops)

## Reasons for the resolution

