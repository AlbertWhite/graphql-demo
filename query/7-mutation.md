### Content

Mutation type is used for modifying the data.

For a mutation, it is important to know its input type and response payload.

### Query

```graphql
mutation addCommentToIssue($ID: ID!, $body: String!) {
  addComment(input: { subjectId: $ID, body: $body }) {
    commentEdge {`  
      node {
        body
      }
    }
  }
}
```

### Variable

```json
{ "id": "MDU6SXNzdWU0NDU1MzczMjc=", "body": "hello world" }
```

### Result

```json
{
  "data": {
    "addComment": {
      "commentEdge": {
        "node": {
          "body": "hello world"
        }
      }
    }
  }
}
```
