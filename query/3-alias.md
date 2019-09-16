### Content

Alias is used for :

1. rename the field in result
2. if we query the same field twice, use alias to avoid collision.

### Query

```graphql
query queryName {
  viewer {
    things: repository(name: "things") {
      createdAt
    }
    react_demos: repository(
      name: "react-demos"
    ) {
      createdAt
    }
  }
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
