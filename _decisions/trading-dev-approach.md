---
type: decision
acronym: trading-dev-approach
title: Development approach of trading service team
decision_type: team
service: trading
status: _3_agreed
responsible: tla;tpa
deadline:
priority: 2-medium
tags: 
todo:
history:
    v1:
        date: 2021-10-28
        comment: created initially and added contents
    v2:
        date: 2021-10-31
        comment: added decisions from latest team meeting
---

## Why is there need for such a decision?

The team's development approach should be standardized to enable better teamwork and give the entire development process a standardized procedure.

## Approach defined by the team

The team wanted to use trello as the tool to coordinate the tasks during development. 

## Alternatives not seriously considered

Github Projects, Waterfall etc.

## How was this decision evaluated?

The team discussed in a discord call and the product owners discussed experiences from past projects.

## Resolution Details

The team uses Trello for the development of the service. Several columns have been proposed, the purpose and use of which is described below:

### User Stories
This is where the product owners enter their user stories. In these, the requirements for the service are formulated from the user's point of view. These should answer at least the following questions. **Who?** Which other service in the entire system? **What?** What exactly does said service require? **Why?** What is the benefit to the service? (Will be used for more detailed discussion)

### Tasks
The tasks are formed from the user stories in Sprint Planning. Initially, the development team should independently formulate the tasks necessary for a user story. However, it is often useful to discuss the individual tasks with the product owner again if there are any questions.

### Doing
Once all the tasks in a sprint have been defined, the developers decide among themselves which tasks they will complete and when. When a developer starts a certain task, he signals this by dragging the respective task into the 'doing' column.

### Review/Testing
Once a task is completed, a pull request is created in github and assigned to another developer (not the one who completed the task). This developer checks if all tests written by the developer are successful and if the task has been completely implemented according to the corresponding formulation. if the task is not finished, the task must be returned to the 'doing' column and the developer must add the missing tasks or fix the errors found. The errors and missing functions are recorded in the pullrequest and the pull request is rejected.

### Done
If the reviewer has checked the task, the tests have been run successfully and all functionalities have been implemented, the pull request is accepted and the tasks are dragged to the done column. if all tasks of a user story have been completed, this is also dragged to done in consultation with the product owner.

### Open Questions
If open questions arise during the development, they should be recorded with a card in this column. Subsequently, this question can be referenced during discussions or chats and any results can be recorded in it.


## Reasons for the resolution
With this approach, the developers can determine their own course of action within the development process. They receive specifications from the user stories and can develop the system on the basis of these. The close exchange with the product owner during the derivation of the tasks from the user stories can ensure that the requirements are implemented in full. With the additional columns, the development process is easily visualized and it is easier to see what progress is being made with which functionality.
