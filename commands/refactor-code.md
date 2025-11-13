Refactor code to improve quality while maintaining functionality.

## Instructions

1. **Identify Refactoring Target**
   - Specify the file, function, class, or module to refactor
   - State the reason for refactoring (readability, maintainability, performance, etc.)

2. **Ensure Test Coverage**
   - Verify existing tests cover the code being refactored
   - If tests are missing, write them first
   - Run tests to establish baseline (all should pass)

3. **Plan Refactoring**
   - Identify code smells or issues:
     - Long methods/functions
     - Duplicated code
     - Complex conditionals
     - Poor naming
     - Tight coupling
     - Low cohesion
   - Choose refactoring techniques:
     - Extract method/function
     - Rename variables/functions/classes
     - Simplify conditionals
     - Remove duplication
     - Extract constants
     - Improve type hints/annotations

4. **Refactor Incrementally**
   - Make small, focused changes
   - Run tests after each change
   - Commit working state frequently
   - Don't mix refactoring with feature changes

5. **Common Refactoring Patterns**
   - **Extract Function**: Break long functions into smaller ones
   - **Rename**: Improve variable/function names for clarity
   - **Remove Dead Code**: Delete unused code
   - **Simplify Logic**: Reduce nesting, use early returns
   - **Extract Constants**: Replace magic numbers/strings
   - **Type Annotations**: Add type hints for better IDE support

6. **Verify**
   - Run full test suite
   - Verify no behavior changes
   - Check linting passes
   - Review for improved readability

## Output

Provide a refactoring summary:
- **Target**: What code was refactored
- **Motivation**: Why it needed refactoring
- **Changes Made**: List of refactoring techniques applied
- **Before/After Metrics**:
  - Lines of code
  - Cyclomatic complexity (if applicable)
  - Test coverage
- **Verification**: Confirm tests pass and no behavior changed
- **Improvements**: How the code is better now
