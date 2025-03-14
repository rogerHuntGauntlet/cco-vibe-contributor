# CCO-VIBE API Documentation

## Overview

This document provides detailed information about the CCO-VIBE API endpoints, their usage, and examples.

## Base URL

```
Production: https://api.cco-vibe.com/v1
Staging: https://staging-api.cco-vibe.com/v1
Development: http://localhost:3000/api/v1
```

## Authentication

All API requests require authentication using JWT tokens. Include the token in the Authorization header:

```http
Authorization: Bearer <your_jwt_token>
```

## Rate Limiting

- 100 requests per minute per IP address
- 1000 requests per hour per user
- Rate limit headers are included in responses

## Endpoints

### Authentication

#### POST /auth/login
Authenticate a user and receive a JWT token.

**Request:**
```json
{
  "email": "user@example.com",
  "password": "secure_password"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "user_123",
    "email": "user@example.com",
    "name": "John Doe"
  }
}
```

#### POST /auth/register
Register a new user account.

**Request:**
```json
{
  "email": "user@example.com",
  "password": "secure_password",
  "name": "John Doe"
}
```

**Response:**
```json
{
  "id": "user_123",
  "email": "user@example.com",
  "name": "John Doe"
}
```

### Projects

#### GET /projects
List all projects accessible to the authenticated user.

**Parameters:**
- `page` (optional): Page number for pagination
- `limit` (optional): Items per page (default: 20)
- `sort` (optional): Sort field (created_at, updated_at)
- `order` (optional): Sort order (asc, desc)

**Response:**
```json
{
  "data": [
    {
      "id": "project_123",
      "name": "Example Project",
      "description": "Project description",
      "created_at": "2024-03-14T12:00:00Z",
      "updated_at": "2024-03-14T12:00:00Z"
    }
  ],
  "meta": {
    "total": 100,
    "page": 1,
    "limit": 20
  }
}
```

#### POST /projects
Create a new project.

**Request:**
```json
{
  "name": "New Project",
  "description": "Project description",
  "settings": {
    "visibility": "private",
    "collaboration": "team"
  }
}
```

**Response:**
```json
{
  "id": "project_123",
  "name": "New Project",
  "description": "Project description",
  "created_at": "2024-03-14T12:00:00Z",
  "updated_at": "2024-03-14T12:00:00Z"
}
```

### Tasks

#### GET /projects/{projectId}/tasks
List all tasks in a project.

**Parameters:**
- `status` (optional): Filter by status (open, in_progress, completed)
- `assignee` (optional): Filter by assignee ID
- `page` (optional): Page number
- `limit` (optional): Items per page

**Response:**
```json
{
  "data": [
    {
      "id": "task_123",
      "title": "Implement feature",
      "description": "Task description",
      "status": "open",
      "assignee": {
        "id": "user_123",
        "name": "John Doe"
      },
      "created_at": "2024-03-14T12:00:00Z",
      "updated_at": "2024-03-14T12:00:00Z"
    }
  ],
  "meta": {
    "total": 50,
    "page": 1,
    "limit": 20
  }
}
```

## Error Handling

All errors follow this format:

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message",
    "details": {
      "field": "Additional error details"
    }
  }
}
```

### Common Error Codes

- `UNAUTHORIZED`: Authentication required or failed
- `FORBIDDEN`: Permission denied
- `NOT_FOUND`: Resource not found
- `VALIDATION_ERROR`: Invalid input data
- `RATE_LIMITED`: Too many requests
- `INTERNAL_ERROR`: Server error

## Webhooks

### Configuration

Webhooks can be configured in the project settings. Each webhook requires:
- URL endpoint
- Secret key for signature verification
- Events to subscribe to

### Events

- `project.created`
- `project.updated`
- `task.created`
- `task.updated`
- `task.deleted`
- `comment.created`
- `comment.updated`

### Webhook Payload

```json
{
  "event": "task.created",
  "timestamp": "2024-03-14T12:00:00Z",
  "project_id": "project_123",
  "data": {
    "id": "task_123",
    "title": "New task",
    "description": "Task description"
  }
}
```

## SDK Examples

### JavaScript/TypeScript

```typescript
import { CCOVibe } from '@cco-vibe/sdk';

const client = new CCOVibe({
  apiKey: 'your_api_key',
  environment: 'production'
});

// List projects
const projects = await client.projects.list({
  page: 1,
  limit: 20
});

// Create task
const task = await client.tasks.create({
  projectId: 'project_123',
  title: 'New task',
  description: 'Task description'
});
```

## Best Practices

1. **Rate Limiting**
   - Implement exponential backoff
   - Cache responses when possible
   - Use bulk endpoints for multiple operations

2. **Error Handling**
   - Always check for error responses
   - Implement proper retry logic
   - Log detailed error information

3. **Authentication**
   - Rotate API keys regularly
   - Use environment variables for sensitive data
   - Implement proper token refresh logic

4. **Performance**
   - Use pagination for large datasets
   - Implement request batching
   - Cache frequently accessed data 