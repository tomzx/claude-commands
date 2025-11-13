Generate or update API documentation.

## Instructions

1. **Identify API Type**
   - REST API
   - GraphQL API
   - gRPC API
   - WebSocket API

2. **Choose Documentation Format**
   - **OpenAPI/Swagger**: REST APIs (recommended)
   - **GraphQL Schema**: GraphQL APIs
   - **Protocol Buffers**: gRPC APIs
   - **Markdown**: General documentation

3. **Extract API Information**
   - Endpoints/routes
   - HTTP methods
   - Request parameters (path, query, body)
   - Request/response schemas
   - Authentication requirements
   - Error responses
   - Rate limiting
   - Examples

4. **Document Each Endpoint**

   For each API endpoint, include:
   - **Method and Path**: `GET /api/users/{id}`
   - **Description**: What the endpoint does
   - **Authentication**: Required auth method
   - **Path Parameters**: Route parameters
   - **Query Parameters**: Optional filters, pagination
   - **Request Body**: Schema and example
   - **Response**: Schema and examples (success and error)
   - **Status Codes**: Possible HTTP status codes
   - **Examples**: Real-world usage examples

5. **Generate Documentation**

   **Using OpenAPI/Swagger:**
   - Check for existing `openapi.yaml` or `swagger.json`
   - Generate from code annotations:
     - Python: `apispec`, `drf-spectacular`, `fastapi` (auto)
     - Node.js: `swagger-jsdoc`, `tsoa`
     - Go: `swaggo/swag`
   - Validate schema: `swagger-cli validate openapi.yaml`
   - Generate interactive docs:
     - Swagger UI: `https://swagger.io/tools/swagger-ui/`
     - ReDoc: `https://github.com/Redocly/redoc`

   **Using Code Comments:**
   - Add docstrings/comments to API handlers
   - Use standard formats (JSDoc, Python docstrings)
   - Include examples in comments

6. **API Documentation Structure**

```markdown
# API Reference

## Authentication

Describe authentication methods (API keys, OAuth, JWT, etc.)

## Base URL

`https://api.example.com/v1`

## Endpoints

### Get User

`GET /users/{id}`

Retrieves a user by ID.

**Path Parameters:**
- `id` (integer, required): User ID

**Query Parameters:**
- `include` (string, optional): Related resources to include (comma-separated)

**Response (200 OK):**
```json
{
  "id": 123,
  "name": "John Doe",
  "email": "john@example.com"
}
```

**Error Responses:**
- `404 Not Found`: User does not exist
- `401 Unauthorized`: Invalid or missing authentication

**Example:**
```bash
curl -H "Authorization: Bearer TOKEN" \
  https://api.example.com/v1/users/123
```
```

7. **Include Common Information**
   - Rate limiting policy
   - Pagination approach
   - Error format
   - Versioning strategy
   - Common headers
   - CORS policy

8. **Add Examples**
   - cURL examples
   - Code examples (Python, JavaScript, etc.)
   - Request/response examples for common scenarios
   - Error handling examples

## Best Practices

- Keep documentation in sync with code (automate if possible)
- Use consistent formatting and terminology
- Include realistic examples
- Document error cases, not just happy paths
- Version your API and documentation
- Provide changelog for API changes
- Include getting started guide
- Add interactive API explorer (Swagger UI, Postman)

## Output

Provide:
- **API Inventory**: List of all endpoints
- **OpenAPI Spec**: Generated OpenAPI/Swagger specification (if applicable)
- **Documentation**: Complete API reference documentation
- **Examples**: Code examples for common use cases
- **Interactive Docs**: Link to Swagger UI or similar
- **Changelog**: Recent API changes
