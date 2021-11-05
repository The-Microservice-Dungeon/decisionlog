---
type: decision
acronym: robot-tech-stack
title: Technology stack for Robot service
decision_type: team
service: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-10-22
priority: 1-high
aspects: 
    - techStack
todos:
history:
    v1:
        date: 2021-10-17
        comment: created initially 
    v2:
        date: 2021-10-21
        comment: Add Tech-Stack Decision   
    v3:
        date: 202110-27
        comment: added final techstack for dev-ops
---

## Why is there need for such a decision?

No development can start before the technology stack (esp. programming language) has been chosen by the team.

## Additional sources for better understanding the background

[Kotlin Documentation](https://kotlinlang.org/)  
[Spring Boot](https://spring.io/) vs. [Maven](https://maven.apache.org/)  
[MariaDB](https://mariadb.org/)  
[Gradle](https://gradle.org/)  
[H2 Database](https://www.h2database.com/html/main.html)  
[Apache Kafka](https://kafka.apache.org/)  

## Viable Options

- Kotlin as the main programming language (choice of the team)
- Spring as the web application framework (choice of the team)
- Maven or Gradle for Build-Management (team is leaning more towards Gradle, due to being newer and offering more options)
- H2 or MariaDB for data storage

## Alternatives not seriously considered

Currently no other alternatives are seriously considered. Options have been chosen based on team preferences and experiences. 

## How is this decision evaluated?

Ideas have been discussed with the development team
 
## Resolution Details

Build: Gradle  
Framework: Spring Boot 2.5.5  
Tech: Kotlin  
Version: Java 11  
Other:  
  - database
    -MariaDB
  - dependencies: 
      - Spring Starter Data JPA
      - Spring Starter Web
      - Spring for Apache Kafka
      - MariaDB Java Client
      - H2 Database

## Reasons for the resolution

Reasons for the decisions are mainly due to team experience with the chosen technologies (Kotlin, Spring) or wanting to try out new technologies (Gradle)
