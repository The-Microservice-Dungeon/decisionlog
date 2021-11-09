---
type: decision
acronym: conventions-for-rest-uris
title: Conventions for REST URIs
decision_type: must
status: _3_agreed
responsible: thu
deadline: 2021-10-29
priority: 2-medium
aspects:
    - api
    - convention
todos:
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-22
        comment: >
            Add convention draft
    v3:
        date: 2021-11-09
        comment: >
            No further comments -> agreed
---

## Why is there need for such a decision?

All REST APIs in this applications should have a similar structure.

## Additional sources for better understanding the background

- [Adidas API Guidelines](https://adidas.gitbook.io/api-guidelines/rest-api-guidelines)
- [Zalando API Guidelines](https://opensource.zalando.com/restful-api-guidelines/)
- [Microsoft API Guidelines](https://github.com/microsoft/api-guidelines/blob/vNext/Guidelines.md)
- [Best Practices in API Design](https://swagger.io/resources/articles/best-practices-in-api-design/)
- [RESTful web API Design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

## Viable Options

n/a, see resolution

## Alternatives not seriously considered

n/a, see resolution

## How is this decision evaluated?

No evaluation needed.

## Resolution details

**Structure the API around resources of our business entities**

- GOOD ✅: `/users/{id}/groups`
- BAD ❌: `/get-users/user-by-id/{id}?q=groups`

**No Verbs**

- GOOD ✅: **POST** `/users`
- BAD ❌: **POST** `/users/create-new`

**Use plural nouns for collectional resources**

- GOOD ✅: **GET** `/users/{id}`
- BAD ❌: **GET** `/user/{id}`

**Keep the URIs flat and unnested**

- BAD ❌: `/users/{id}/groups/{id}/roles/{id}`

*However keep in mind, that it might be necessary to use nested URIs when a subresource is only accessable via its parent.*

**Normalize the URIs (No trailing slash, no double-slash)**

- BAD ❌: `/users//{id}`
- BAD ❌: `/users//{id}/`

**Use kebab-case to improve readability**

- GOOD ✅: `/shopping-cart`
- BAD ❌: `/shopping_cart`
- BAD ❌: `/shoppingCart`
- BAD ❌: `/sHoPpInGcArT`

**Don't use matrix parameters, use query parameters**

- GOOD ✅: `/products?sort=price`
- BAD ❌: `/products;sort=price`

**Use multiple query parameters (also known as explode)**

- GOOD ✅: `/products?sort=price&sort=color`
- BAD ❌: `/products?sort=price,color`

## Reasons for the resolution

- Some aspects are well-defined by the REST paradigma itself and therefore mandatory
- Some aspects are best practices 
- And some aspects are a matter of taste but have to be decided in order to have a consistent API