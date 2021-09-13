![Just a Jin](https://github.com/matmar10/just-a-jin/blob/master/logo.png?raw=true "Just a Jin Logo")

Automagically jin-erate just-api tests from your Open API spec. Why jin? Because jins are magic!

```Bash
npm install -g just-a-jin just-api
just-a-jin openapi.json -o test/
```

## Why?

[OpenAPI](https://www.openapis.org/) is the best way to define and document REST APIs. But how about testing?

[Just API](https://kiranz.github.io/just-api/) is a simple yet powerful way to write comprehensive tests for REST APIs.

-- but --

How can you verify if your OpenAPI spec is correct? Wouldn't it be great if there was a tool that could automagically generate just-api tests from your Open API spec?

There is!

## Configuration

```Yaml
---

tests:
  # provide a list of unique operation IDs
  - registerWithUsernamePassword
  - registerWithEmailPassword
  - getUserProfile

  # or, specify additional test to run before/after the auto-generated one(s)
  - operationId: login
    before:
      - ./test/register-random-user.yml
      - ./test/verify-email.yml
    after:
      - ./test/logout.yml
```
