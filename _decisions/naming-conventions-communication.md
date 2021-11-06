---
type: decision
acronym: naming-conventions-communication
title: What naming conventions should the services follow when communicating?
decision_type: must
status: _2_draft_
responsible: tpa;
priority: 2-medium
todo:
aspects:
    - documentation
    - convention
history:
    v1:
        date: 2021-11-06
        comment: created initially
---

## Why is there need for such a decision?

It has already been decided that the API routes use kebab case. In order to further standardize the communication between the services, it is also necessary to specify in which style the variables within the objects used for communication are named.

## Additional sources for better understanding the background

[ECMA-404](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf)
[Google JSONC Styleguide](https://google.github.io/styleguide/jsoncstyleguide.xml)
[Facebook JavaScript API](https://developers.facebook.com/docs/javascript/examples)
[Amazon Web Services ](http://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html#aws-ip-syntax)

## Viable Options

    - snake_case
    - camelCase
    - kebab-case
    - YELLING_SNAKE-KEBAB_CASE

## Alternatives not seriously considered

### Kebab-Case

The main reason to use kebab case is that it improves readability for SEO relevant systems. Also, it is a widely used standard, especially at the end of the URL ((Designing Web APIs
by Brenda Jin, Saurabh Sahni, Amir Shevat)[https://www.oreilly.com/library/view/designing-web-apis/9781492026914/]). However, it is not considered for the names of keys within an object in this system. This decision is based on the fact that none of the used development languages use this style for naming variables.
It has already been decided that the API routes use kebap case. In order to further standardize the communication between the services, it is also necessary to specify in which style the variables within the objects used for communication are named.

## How is this decision evaluated?

By researching online for known standards and looking at large established projects.

## Resolution Details

```
camelCase
```

## Reasons for the resolution

Finding the right naming style depends heavily on the technology stack used. Since the technologies used in this project mainly use the camelCase internally, this was also chosen as the standard.
