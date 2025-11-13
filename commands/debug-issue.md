Debug a specific issue or error in the codebase.

## Instructions

1. **Gather Information**
   - Error message and stack trace
   - Steps to reproduce
   - Expected vs actual behavior
   - Environment details (OS, version, dependencies)
   - Recent changes that might be related

2. **Locate the Problem**
   - Use stack trace to identify the failing file and line
   - Read the relevant code section
   - Trace backwards through the call stack
   - Identify the data flow leading to the error

3. **Form Hypotheses**
   - What could cause this error?
   - List potential root causes
   - Prioritize hypotheses by likelihood

4. **Test Hypotheses**
   - Add logging/print statements at key points
   - Check variable values at critical junctures
   - Verify assumptions about data types and values
   - Test edge cases

5. **Isolate the Root Cause**
   - Narrow down the exact line or function causing the issue
   - Identify why it's failing (bad input, logic error, state issue, etc.)
   - Verify the root cause with a minimal reproduction

6. **Propose Fix**
   - Describe the fix needed
   - Consider edge cases
   - Ensure fix doesn't break other functionality
   - Write a test to prevent regression

## Debugging Techniques

- **Binary Search**: Comment out half the code to isolate the problem
- **Rubber Duck**: Explain the code line by line
- **Compare Working State**: What changed between working and broken?
- **Check Assumptions**: Verify all assumptions with assertions
- **Simplify**: Create minimal reproduction case

## Output

Provide a debugging report:
- **Issue Summary**: Brief description of the problem
- **Investigation Steps**: What you checked and found
- **Root Cause**: The underlying reason for the failure
- **Proposed Fix**: How to resolve the issue
- **Verification Plan**: How to test the fix
- **Prevention**: How to avoid this in the future (tests, validation, etc.)
