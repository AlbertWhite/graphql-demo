### Content

1. Field select for string or array
2. Sub-selection for object shaped field
3. Pass argument to field

### Query

```graphql
query queryName {
  viewer {
    repositories(first: 2) {
      nodes {
        name
        issues(first: 2) {
          nodes {
            title
          }
        }
      }
    }
  }
}
```

### Result

```json
{
  "data": {
    "viewer": {
      "repositories": {
        "nodes": [
          {
            "name": "Momenthere",
            "issues": {
              "nodes": []
            }
          },
          {
            "name": "MomentHereServer",
            "issues": {
              "nodes": []
            }
          }
        ]
      }
    }
  }
}
```
