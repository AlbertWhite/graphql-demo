### Content

Argument can be passed as variable. Variable need to be passed to query level.

If a variable is required, we must add a !.

Variable is accessable to fragment.

### Query

```graphql
query queryName($firstIndex: Int = 1) {
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
  issues(first: $firstIndex) {
    nodes {
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
        "createdAt": "2019-05-17T17:04:39Z",
        "issues": {
          "nodes": [
            {
              "createdAt": "2019-05-17T17:10:15Z"
            }
          ]
        }
      },
      "react_demos": {
        "createdAt": "2017-10-20T13:45:47Z",
        "issues": {
          "nodes": []
        }
      }
    }
  }
}
```
