### Content

Fragment is used for sharing queries.

Fragment need to extend an object type.

### Query

```graphql
query queryName {
  viewer {
    things: repository(name: "things") {
      ...repositoryFields
    }
    react_demos: repository(name: "react-demos") {
      ...repositoryFields
    }
  }
}

fragment repositoryFields on Repository {
  createdAt
}
```

### Result

```json
{
  "data": {
    "viewer": {
      "things": {
        "createdAt": "2019-05-17T17:04:39Z"
      },
      "react_demos": {
        "createdAt": "2017-10-20T13:45:47Z"
      }
    }
  }
}
```
