---
type: decision
acronym: robot-dev-approach
title: Development approach of team robot
decision_type: team
belongs_to: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-10-25
priority: 2-medium
tags: 
todo:
history:
    v1:
        date: 2021-10-25
        comment: created initially and added contents
---

## Why is there need for such a decision?

The development approach of the team should be unified to better enable teamwork and to give the whole development process a standarsised procedure.

## Approach defined by the team

The team wants to go for a test-driven development approach.

## Alternatives not seriously considered

every other method for development

## How was this decision evaluated?

The development team met and discussed how they want to approach this project.

## Resolution Details

1. Create ticket in Jira
2. The person who works on a ticket moves it to the column "Writing Tests", creates a branch and writes the test which needs to be passed in order for the ticket to be considered completed
3. After writing the tests the ticked will be moved to "Writing Code"
4. Another person assigns the ticket to themselves and implements the code in such a way that the tests are passed
5. The person who implements the feature creates a pull request on GitHub and assigns one developer as reviewer. This reviewer should also be assigned to the ticket in Jira
6. After addressing the reviewer’s concerns (change code/discussion) the pull request will be cleared and the code can be merged into the main branch
7. The ticked is moved into the column "Done"
8. The ticked is completed

## Reasons for the resolution

The team wants a test-driven development approach to ensure that the implemented code is always testable during development. Therefore implementation in an already existing test framework will help the team to ensure the production of working code.
