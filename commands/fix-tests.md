Fix failing tests in the codebase.

## Instructions

1. Run the test suite to identify failing tests
2. For each failing test:
   - Read the test code to understand what it's testing
   - Read the failure message and stack trace
   - Identify the root cause of the failure:
     - Is the test incorrect?
     - Is the implementation incorrect?
     - Is it a test data issue?
     - Is it an environmental issue?
   - Determine the appropriate fix

3. Common failure patterns:
   - **Assertion failures**: Check if expectations match actual behavior
   - **Import errors**: Verify module paths and dependencies
   - **Setup/teardown issues**: Check test fixtures and cleanup
   - **Timing issues**: Look for race conditions or async problems
   - **Mock/stub issues**: Verify mocks are configured correctly

4. Fix the tests:
   - Update test code if the test is incorrect
   - Update implementation if the code is incorrect
   - Update test data if needed
   - Add missing setup/teardown steps

5. Verify the fix:
   - Re-run the specific test that was failing
   - Run the full test suite to ensure no regressions
   - Check that test coverage hasn't decreased

## Output

For each failing test, document:
- Test name and location
- Failure reason
- Root cause identified
- Fix applied
- Verification that fix works

Provide a final summary:
- Total tests fixed
- Any tests that still need attention
- Test coverage status
