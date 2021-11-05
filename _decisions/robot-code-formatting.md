---
type: decision
acronym: robot-code-formatting
title: Code formatting decision
decision_type: team
service: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-11-05
priority: 3-low
aspects: 
todo:
history:
    v1:
        date: 2021-11-05
        comment: created initially and added contents
---

## Why is there need for such a decision?

It's preferable to avoid commits that add no value to the project. This decision seeks to avoid commits that are mainly formatting changes.

## Additional sources for better understanding the background

[Ktlint Gradle](https://github.com/JLLeitschuh/ktlint-gradle)  

## Approach defined by the team

The team has decided for themselves to use the ktLint plugin in order to auto format the code before a commit.

## How was this decision evaluated?

The development team met and chose this convention for their own development workflow.

## Resolution Details

The plugin is added to the project. To enable the git pre commit hook, the following gradle task is run: 

`./gradlew addKtlintFormatGitPreCommitHook`

