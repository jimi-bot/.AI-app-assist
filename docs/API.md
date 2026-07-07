# API Documentation

## Endpoints

### Health Check
```
GET /health
```

Returns:
```json
{ "status": "ok", "timestamp": "2024-01-01T00:00:00.000Z" }
```

### Generate Code
```
POST /api/generate-code
```

Request:
```json
{
  "description": "Create a React component for user authentication",
  "language": "typescript",
  "framework": "react",
  "context": "Using Firebase for authentication"
}
```

Response:
```json
{
  "success": true,
  "data": {
    "id": "uuid",
    "suggestion": "...",
    "code": "...",
    "explanation": "...",
    "nextSteps": ["..."],
    "tokensUsed": { "prompt": 100, "completion": 200, "total": 300 }
  },
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

### Debug Issue
```
POST /api/debug
```

Request:
```json
{
  "description": "TypeError: Cannot read property 'map' of undefined",
  "context": "array.map(...) in useEffect hook",
  "language": "typescript",
  "codeSnippet": "const items = data.map(item => item.id);"
}
```

### Architecture Suggestions
```
POST /api/architecture
```

Request:
```json
{
  "description": "Real-time chat application",
  "context": "Expecting 10k concurrent users",
  "constraints": ["use Node.js", "AWS deployment"]
}
```

### Generate Documentation
```
POST /api/documentation
```

Request:
```json
{
  "description": "API endpoint for user registration",
  "context": "RESTful API with email verification",
  "language": "typescript"
}
```

### Generate Tests
```
POST /api/tests
```

Request:
```json
{
  "description": "Function that calculates factorial",
  "context": "Should handle edge cases",
  "language": "typescript",
  "framework": "jest"
}
```

### Get Conversation History
```
GET /api/history
```

Response:
```json
{
  "success": true,
  "data": [
    {
      "role": "user",
      "content": "...",
      "timestamp": "2024-01-01T00:00:00.000Z"
    },
    {
      "role": "assistant",
      "content": "...",
      "timestamp": "2024-01-01T00:00:00.000Z"
    }
  ],
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

### Reset Conversation
```
POST /api/reset
```

Response:
```json
{
  "success": true,
  "data": "Context reset successfully",
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

## Error Handling

All endpoints return errors in the following format:

```json
{
  "success": false,
  "error": "Error message",
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

Common HTTP status codes:
- `200` - Success
- `400` - Bad request
- `404` - Not found
- `500` - Server error
