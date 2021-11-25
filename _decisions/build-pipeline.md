---
type: decision
acronym: build-pipeline
title: Github Actions for Build Pipeline
decision_type: must
status: _3_agreed
responsible: tra
deadline: 2021-10-22
priority: 2-medium
aspects:
    - devOps
    - techStack
todos:
    - (sb) Is Gitlab actions final? Then please state it this way.  
    - (sb) Why is Jenkins not seriously considered?
    - (sb) Please change title to express the decision made
history:
    v1:
        date: 2021-19-08
        comment: created initially
---

## Why is there need for such a decision?

We need to choose a tool for out build pipeline. It has to be comaptible with github.

## Additional sources for better understanding the background

tbd

## Viable Options

* GitHub Actions


## Alternatives not seriously considered

* Jenkins


## How is this decision evaluated?

During the evaluation, special attention was paid to compatibility with GitHub. In addition, it was ensured that as many programming languages as possible were supported.

## Resolution Details

Github actions is the perfect tool for this project, since all code is hosted on github. Furthermore there are many predefined actions the de v ops team can use.

## Reasons for the resolution

* Perfect integration with VCS

