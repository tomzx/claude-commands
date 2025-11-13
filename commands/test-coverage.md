Analyze and improve test coverage for the codebase.

## Instructions

1. **Measure Current Coverage**
   - Identify coverage tool for the project:
     - Python: `pytest-cov` or `coverage.py`
     - JavaScript: `jest --coverage` or `nyc`
     - Go: built-in `go test -cover`
     - Rust: `cargo-tarpaulin` or `cargo-llvm-cov`

2. **Run Coverage Analysis**
   - Python: `pytest --cov=. --cov-report=html --cov-report=term`
   - JavaScript: `npm test -- --coverage`
   - Go: `go test -coverprofile=coverage.out ./... && go tool cover -html=coverage.out`
   - Rust: `cargo tarpaulin --out Html`

3. **Analyze Results**
   - Overall coverage percentage
   - Per-file coverage breakdown
   - Identify uncovered lines
   - Find critical paths without coverage
   - Look for untested edge cases

4. **Prioritize Coverage Gaps**
   - Critical business logic
   - Error handling paths
   - Edge cases and boundary conditions
   - Recently modified code
   - Complex algorithms

5. **Write Missing Tests**
   - Focus on high-value, uncovered code first
   - Write tests that increase coverage meaningfully
   - Don't just write tests to hit coverage targets
   - Ensure tests verify actual behavior, not just execute code

6. **Set Coverage Goals**
   - Establish minimum coverage thresholds
   - Configure coverage tools to enforce thresholds
   - Add coverage checks to CI/CD pipeline

## Coverage Best Practices

- Aim for 80%+ coverage, but focus on quality over quantity
- 100% coverage doesn't mean bug-free code
- Test behavior and contracts, not implementation details
- Ignore coverage for generated code, migrations, config files
- Use coverage to find untested code, not as a success metric

## Output

Provide a coverage report:
- **Current Coverage**: Overall percentage and breakdown by file/module
- **Coverage Gaps**: List of uncovered code areas
- **Priority Areas**: Critical code lacking coverage
- **Recommended Tests**: Specific tests to write to improve coverage
- **Coverage Trends**: How coverage has changed over time (if available)
- **Configuration**: Coverage tool settings and thresholds
