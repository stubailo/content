---
alias: ow2yei7mew
path: /docs/reference/cli/project-files
layout: REFERENCE
description: The Graphcool CLI lets you work with the schema of a project. You can easily create a new project or update the schema of an existing one.
tags:
  - cli
related:
  further:
  more:
---

# The project.graphcool File

Working with the `project.graphcool` file is a central part of using the Graphcool CLI. They contain the project's [GraphQL schema](!alias-ahwoh2fohj) as well as additional metadata such as the **project id** and the **version number** of the schema. This is how a `project.graphcool` file looks like:

```graphql
# project: cj2deyxfmpmwi0104pce2xucz
# version: 3

type Tweet {
  createdAt: DateTime!
  id: ID! @isUnique
  owner: User! @relation(name: "UserOnTweet")
  text: String!
  updatedAt: DateTime!
}

type User {
  createdAt: DateTime!
  id: ID! @isUnique
  updatedAt: DateTime!
  name: String!
  tweets: [Tweet!]! @relation(name: "UserOnTweet")
}
```

Every change to the project schema done by using the Console or the CLI will increment the schema version.

> Read more about types, fields, relations and directives in the [data schema section](!alias-ahwoh2fohj).
