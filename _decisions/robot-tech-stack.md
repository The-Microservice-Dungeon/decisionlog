---
type: decision
acronym: robot-tech-stack
title: Technology stack for Robot service
decision_type: team
belongs_to: robot
status: _2_draft
responsible: ngi;cpo
deadline: 2021-10-22
priority: 1-high
tags: 
    - tech-stack
history:
    v1:
        date: 2021-10-17
        comment: created initially 
    v2:
        date: 2021-10-21
        comment: Add Tech-Stack Decision   
---

## Why is there need for such a decision?

No development can start before the technology stack (esp. programming language) has been chosen by the team.

## Additional sources for better understanding the background

tbd.

## Viable Options

- Kotlin as the main programming language (choice of the team,)
- Spring as the web application framework (choice of the team)
- Maven or Gradle for Build-Management (team is leaning more towards Gradle, due to being newer and offering more options)
- H2 or MariaDB for data storage

## Alternatives not seriously considered

- Currently no other alternatives are seriously considered. Options have been chosen based on team preferences and experiences. 

## How is this decision evaluated?

- Ideas have been discussed with the development team
 
## Resolution Details

- The viable options have mostly been accepted

## Reasons for the resolution

- Reasons for the decisions are mainly due to team experience with the chosen technologies (Kotlin, Spring) or wanting to try out new technologies (Gradle)
