### Content

Directive is similar to variable, but it is used not for argument, but for including / skipping field.

### Query

```graphql
query queryName($firstIndex: Int!, $showTitle: Boolean!) {
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
      title @include(if: $showTitle)
    }
  }
}
```

### Variable

```json
{ "firstIndex": 1, "showTitle": false }
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
