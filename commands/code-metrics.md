Analyze code metrics to assess code quality and complexity.

## Instructions

1. **Select Metrics to Measure**

   **Code Size Metrics:**
   - Lines of code (LOC)
   - Lines of production code vs test code
   - Number of files
   - Code vs comments ratio

   **Complexity Metrics:**
   - Cyclomatic complexity
   - Cognitive complexity
   - Nesting depth
   - Function/method length

   **Quality Metrics:**
   - Test coverage
   - Code duplication
   - Maintainability index
   - Technical debt ratio

   **Structure Metrics:**
   - Module coupling
   - Class cohesion
   - Dependency depth
   - Inheritance depth

2. **Measure Code Size**

   ```bash
   # Total lines of code
   find . -name "*.py" -o -name "*.js" | xargs wc -l

   # Count by file type
   cloc .

   # Exclude tests and dependencies
   cloc --exclude-dir=tests,node_modules,.venv .
   ```

3. **Analyze Complexity**

   **Python:**
   ```bash
   # Cyclomatic complexity
   radon cc . -a -nb

   # Show functions with complexity > 10
   radon cc . -n C -nb

   # Maintainability index
   radon mi . -nb
   ```

   **JavaScript:**
   ```bash
   # Using complexity-report
   cr --format json src/

   # ESLint complexity rules
   eslint --rule 'complexity: ["error", 10]' src/
   ```

   **Go:**
   ```bash
   # Cyclomatic complexity
   gocyclo .

   # Show functions with complexity > 15
   gocyclo -over 15 .
   ```

4. **Measure Code Duplication**

   ```bash
   # Python
   pylint --disable=all --enable=duplicate-code .

   # JavaScript
   jscpd src/

   # General (CPD from PMD)
   cpd --minimum-tokens 50 --files src/
   ```

5. **Analyze Dependencies**

   **Python:**
   ```bash
   # Import dependencies
   pydeps mypackage --max-bacon=2

   # Circular dependencies
   pydeps mypackage --show-cycles
   ```

   **JavaScript:**
   ```bash
   # Dependency tree
   npm list --depth=2

   # Find circular dependencies
   madge --circular src/
   ```

6. **Calculate Code Metrics**

   **Function/Method Analysis:**
   - Count functions longer than 50 lines
   - Identify functions with >5 parameters
   - Find deeply nested code (>4 levels)

   **Class Analysis (OOP):**
   - Number of methods per class
   - Lines of code per class
   - Inheritance depth
   - Number of dependencies

7. **Identify Problem Areas**

   **High Complexity:**
   - Functions with cyclomatic complexity > 10
   - Classes with too many methods (>20)
   - Long functions (>50 lines)

   **Poor Structure:**
   - High coupling (many dependencies)
   - Low cohesion (unrelated functionality)
   - Circular dependencies

   **Maintenance Issues:**
   - High code duplication (>5%)
   - Low test coverage (<80%)
   - Many TODO/FIXME comments

8. **Generate Metrics Report**

   **Using SonarQube:**
   ```bash
   sonar-scanner \
     -Dsonar.projectKey=myproject \
     -Dsonar.sources=src \
     -Dsonar.host.url=http://localhost:9000
   ```

   **Using CodeClimate:**
   ```bash
   codeclimate analyze
   ```

9. **Track Metrics Over Time**
   - Set up metrics tracking in CI/CD
   - Monitor trends (improving or degrading)
   - Set thresholds for acceptable metrics
   - Create dashboards for visibility

## Code Quality Thresholds

**Recommended limits:**
- Cyclomatic complexity: ≤ 10 (warning), ≤ 20 (error)
- Function length: ≤ 50 lines (warning), ≤ 100 (error)
- Test coverage: ≥ 80%
- Code duplication: < 5%
- Maintainability index: ≥ 65 (Python)
- Parameters per function: ≤ 5
- Nesting depth: ≤ 4

## Complexity Categories

- **1-5**: Simple, easy to maintain
- **6-10**: Moderate complexity, acceptable
- **11-20**: Complex, consider refactoring
- **21+**: Very complex, should refactor

## Tools by Language

**Python:**
- `radon`: Complexity and maintainability
- `pylint`: General code quality
- `mccabe`: Cyclomatic complexity
- `coverage`: Test coverage

**JavaScript:**
- `complexity-report`: Complexity analysis
- `plato`: Complexity and maintainability
- `jscpd`: Duplication detection
- `eslint`: Code quality rules

**Go:**
- `gocyclo`: Cyclomatic complexity
- `gocognit`: Cognitive complexity
- `go vet`: Code quality

**Rust:**
- `cargo-geiger`: Unsafe code detection
- `cargo-clippy`: Code quality lints

## Output

Provide a code metrics report:
- **Project Overview**:
  - Total lines of code
  - Files analyzed
  - Languages breakdown
- **Complexity Metrics**:
  - Average cyclomatic complexity
  - Functions/classes with high complexity
  - Most complex functions (top 10)
- **Quality Metrics**:
  - Test coverage percentage
  - Code duplication percentage
  - Maintainability index
- **Structure Metrics**:
  - Module dependencies
  - Circular dependencies
  - Coupling/cohesion scores
- **Problem Areas**:
  - High-complexity functions to refactor
  - Duplicated code locations
  - Low coverage areas
  - Overly long functions/classes
- **Trends**: How metrics changed over time (if historical data available)
- **Recommendations**:
  - Top refactoring priorities
  - Areas needing tests
  - Code to simplify
- **Overall Grade**: A-F rating based on metrics
