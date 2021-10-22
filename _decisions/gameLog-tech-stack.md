---
type: decision
acronym: gameLog-tech-stack
title: Technology stack for GameLog service
decision_type: team
belongs_to: gameLog
status: _2_draft
responsible: thu;aha
deadline: 2021-10-22
priority: 1-high
tags: 
    - tech-stack
todos:
    - (sb) Java or Kotlin - what is it now? (When we decide that mixed language is ok, then just remove this todo)
    - (sb) set status to _3_agreed, once it has been really finalized
history:
    v1:
        date: 2021-10-17
        comment: created initially    
    v2:
        date: 2021-10-20
        comment: Add Tech-Stack Decision
    v3:
        date: 2021-10-22
        comment: >
            Restructure the tech stack decisions
            Add Grafana and Prometheus to the tech stack
---

## Why is there need for such a decision?

No development can start before the technology stack (esp. programming language) has been chosen by the team.

## Additional sources for better understanding the background

n/a

## Viable Options

**Programming Language:**

- Java / Kotlin as Language since it is taught in AP1/AP2, PP and ST1/2

**Frameworks:**
- Spring as Application framework since it is taught in (at least) ST2

**Dashboard:**

During the [Event and Command List decision](../gameLog-event-and-command-list) we came up with the idea to provide a live dashboard of some metrics like the leaderboards, granted trophies and additional gamelog activities. To achieve this we need additional software for creating such a dashboard.

- Grafana
- InfluxDB

**Metric Data Source:**

If we decide tu use Grafana, we need to provide a data source for the dashboard. The possibilties here are huge, but we consider three of them as valid:

- Provide a metric API over REST as JSON
- Prometheus
- InfluxDB

## Alternatives not seriously considered

**Programming Language:**

- Nearly every other language: We can't assume any experiences with techonlogies 
offside the standard curriculum of the computer science Bachelor's degree at the TH Köln. 

**Frameworks:**

- Quarkus, Micronaut, Grails, JakarataEE: Not Taught at the Bachelor's degree

**Dashboard:**

- Develop a custom Frontend: Way to much effort.

**Metric Data Source:**

- SQL
    - This might be a fallback if everything else fails
    - SQL is not a time-series database and therefore not really appropiate to store metrics
- Other data sources listed [in the grafana docs](https://grafana.com/docs/grafana/latest/datasources/)

## How is this decision evaluated?

**Programming Language:**

Curriculum of the bachelors degree
 
**Framework:**

Curriculum of the bachelors degree

**Dashboard:**

- Personal experience
- Available Documentation in the Web

**Metric Data Source:**

- Technical compatibility to the application framework
- Compatibility to the chosen dashboard
- Personal experience
- Popularity / available documentation in the web

## Resolution Details

**Programming Language:**

- Java or Kotlin

**Framework:**

- Spring

**Dashboard:**

- Grafana

**Metric Data Source:**

- Prometheus
- JSON

## Reasons for the resolution

**Programming Language:**

- No coder attended at meeting
- Taught in the Bachelor's degree

**Framework:**

- No coder attended at meeting
- Taught in the Bachelor's degree

**Dashboard:**

- Grafana is highly flexible and more technology-agnostic
- Grafana has a big eco-system of plugins
- Documentation of InfluxDB is more confusing 
- InfluxDB has a steep learning curve
- Grafana has a nicer look and feel

**Metric Data Source:**

- Prometheus is wide-spread, rather simple
- Prometheus is supported by Spring
- Documentation of InfluxDB is more confusing 
- Plain JSON over REST since we decide to aggregate the leaderboard and grant trophies directly in our service
    - Unnatural to expose as a metric
    - The REST Endpoints regarding the Leaderboard and trophies will function as a "fallback" so that game results are availabel even if the idea using a dashboard fails.
- InfluxDB has a steep learning curve