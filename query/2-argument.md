### Query

```graphql
query queryName {
  viewer {
    repository(name: "things") {
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
      "repository": {
        "createdAt": "2019-05-17T17:04:39Z"
      }
    }
  }
}
```
