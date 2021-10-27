---
type: decision
acronym: map-tech-stack
title: Technology stack for Map service
decision_type: team
belongs_to: map
status: _3_agreed
responsible: sbe;psc
deadline: 
priority: 1-high
tags: 
    - tech-stack
history:
    v1:
        date: 2021-10-17
        comment: created initially    
    v2:
        date: 2021-10-25
        comment: decided on ruby and rails
---

## Why is there need for such a decision?

No development can start before the technology stack (esp. programming language) has been chosen by the team.

## Additional sources for better understanding the background

Even though everyone in the Team is familiar with Java & Spring Boot we decided against it for the reasons that we would like to use a stack that is more "fun".

## Viable Options

- Java and Spring Boot
- Java and Quarkus
- Elixir and Phoenix
- Ruby and Rails

## Alternatives not seriously considered

- Rust and Actix

## How is this decision evaluated?

Fun should not be the only reason for choosing a technology, so we were also looking for the following points in another Techstack:

- How well is the technology documented?
- Are there existing libraries/a framework for rest apis, kafka, tests & mockups?

We decided against Elixir and Phoenix, because only one of our Team Members is very familiar with the stack.
 
## Resolution Details

We decided to use Ruby and Rails, Postgresql as database and Rspec as testing framework

## Reasons for the resolution

3 of our Teammembers are working at Railslove. Another one is a former employee of Railslove. With that experience Ruby and Rails was a perfect choice for this project.
