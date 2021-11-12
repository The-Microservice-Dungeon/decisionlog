---
type: decision
acronym: time-format
title: Time format for communication
decision_type: must
status: _3_agreed
responsible: psc
deadline: 2021-11-10
priority: 2-medium
todo:
aspects:
    - convention
history:
    v1:
        date: 2021-11-08
        comment: created draft
---

## Why is there need for such a decision?
Time formats and information can appear in many places in the system (e.g. via events). The complexity of the player services in the hackathon should be reduced. It is therefore appropriate to standardise communicated date formats across the system landscape.

## Additional sources for better understanding the background
[Wikipedia: ISO-8601](https://de.wikipedia.org/wiki/ISO_8601)

## Viable Options
- `2007-08-31T16:47+00:00` - 16:47 on August 31, 2007 in UTC time zone.
- `2007-12-24T18:21Z` - 18:21 on December 24, 2007, in the UTC time zone
- `2009-06-30T18:30:00+02:00` - 18:30:00 on June 30, 2009 in Vienna (CEST - daylight saving time)
- ...

## Alternatives not seriously considered
\-

## How is this decision evaluated?
\-

## Resolution Details
All dates exposed via APIs or events are recorded in UTC in the following format:

`yyyy-MM-dd'T'HH:mm:ss'Z'` --> `2007-12-24T18:21:03Z`


## Reasons for the resolution
The decision is based on Rewe Digital's findings from a presentation in FAE (WS2019). In a nutshell: To avoid misunderstandings due to different systems, time zones, etc., each communicated time is specified in standard UTC. Each client/service can then adapt and convert this for its own purposes.
