---
type: decision
acronym: service-doc-platform
title: Platform for team developer documentation
decision_type: must
belongs_to: qualityAssurance
status: _3_aggreed
responsible: tra;thu
deadline: 2021-10-22
priority: 2-medium
aspects:
    - documentation
todos:
history:
    v1:
        date: 2021-10-08
        comment: created initially 
    v2: 
        date: 2021-10-17
        comment: took task      
    v3:
        date: 2021-11-05
        comment: Adapt GitHub Wiki 
---

## Why is there need for such a decision?

We need to have a uniform way how to find developer documentation for a service, so that you don't need to
look in five different places if you walk through services. 

## Additional sources for better understanding the background

* n/a

## Viable Options

- GitBook
- GitHub Pages
- GitHub Wiki


## Alternatives not seriously considered

- Word
- Paper & Pen

## How is this decision evaluated?

- Time to deployment (or in this case time to writing)
- User-friendliness
 
## Resolution Details

- We use GitHub Wiki
    - Allows different formats

## Reasons for the resolution

- GitBook is now more commercialized and does not provide an easy collectively-usable documentation
- GitHub Pages needs a longer training period and more effort than GitHub Wiki
- GitHub Pages is more flexible but adds complexity as a tradeoff

