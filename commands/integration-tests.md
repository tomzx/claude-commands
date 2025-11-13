Write and run integration tests for the application.

## Instructions

1. **Understand Integration Points**
   - Identify system components that need integration testing:
     - API endpoints
     - Database interactions
     - External services (APIs, message queues, etc.)
     - File system operations
     - Authentication/authorization flows
     - Multi-component workflows

2. **Set Up Test Environment**
   - Configure test database or use in-memory database
   - Set up test fixtures and seed data
   - Configure mocks for external services (or use test instances)
   - Set environment variables for testing
   - Ensure test isolation (tests don't affect each other)

3. **Write Integration Tests**
   - Test complete workflows end-to-end
   - Verify data flows between components
   - Test API contracts (request/response)
   - Verify database transactions and rollbacks
   - Test error scenarios across component boundaries
   - Verify authentication and authorization

4. **Integration Test Patterns**
   - **API Testing**: Test HTTP endpoints with real requests
   - **Database Testing**: Verify queries, transactions, migrations
   - **Service Integration**: Test interactions with external services
   - **End-to-End Flows**: Test user journeys through the system
   - **Contract Testing**: Verify API contracts between services

5. **Run Integration Tests**
   - Execute integration test suite
   - Verify all tests pass
   - Check test execution time
   - Review test logs for warnings or issues

6. **Common Tools**
   - Python: `pytest` with `pytest-django`, `pytest-flask`, or `httpx`
   - JavaScript: `supertest`, `jest`, `playwright`
   - Go: `httptest`, `testcontainers`
   - Rust: `actix-test`, `reqwest`

## Best Practices

- Keep integration tests separate from unit tests
- Use test containers or docker-compose for dependencies
- Clean up test data after each test
- Make tests idempotent (can run multiple times)
- Use realistic test data
- Test both happy paths and error scenarios
- Mock external services to avoid flaky tests
- Keep integration tests fast enough to run frequently

## Output

Provide an integration test report:
- **Test Scope**: What integration points are covered
- **Test Environment**: How test environment is configured
- **Tests Written**: Number and description of integration tests
- **Test Results**: Pass/fail status for each test
- **Coverage**: What workflows and integrations are tested
- **Issues Found**: Any integration issues discovered
- **Recommendations**: Additional integration tests needed
