Update project dependencies to latest versions.

## Instructions

1. **Identify Package Manager**
   - Python: `pip`, `poetry`, `uv`
   - JavaScript: `npm`, `yarn`, `pnpm`
   - Go: `go modules`
   - Rust: `cargo`
   - Ruby: `bundler`

2. **Check Current Dependencies**

   **List outdated packages:**
   ```bash
   # Python
   pip list --outdated
   # or with uv
   uv pip list --outdated

   # Node.js
   npm outdated
   yarn outdated

   # Go
   go list -u -m all

   # Rust
   cargo outdated
   ```

3. **Review Dependency Updates**

   For each outdated dependency:
   - Check changelog/release notes
   - Identify breaking changes
   - Review security advisories
   - Assess update priority:
     - **Critical**: Security vulnerabilities
     - **High**: Bug fixes affecting functionality
     - **Medium**: New features, improvements
     - **Low**: Minor updates, docs

4. **Update Dependencies**

   **Approach 1: Update all at once (risky)**
   ```bash
   # Python
   pip install --upgrade -r requirements.txt

   # Node.js
   npm update
   yarn upgrade

   # Go
   go get -u ./...

   # Rust
   cargo update
   ```

   **Approach 2: Update one at a time (safer)**
   ```bash
   # Python
   pip install --upgrade package-name

   # Node.js
   npm install package-name@latest

   # Go
   go get package@latest

   # Rust
   cargo update -p package-name
   ```

   **Approach 3: Update lock file only**
   ```bash
   # Node.js (respect semver in package.json)
   npm update
   yarn upgrade

   # Python with poetry
   poetry update
   ```

5. **Handle Major Version Updates**

   For major version bumps:
   - Read migration guide
   - Update code for breaking changes
   - Update configuration if needed
   - Update documentation
   - Test thoroughly

6. **Update Lock Files**
   - `package-lock.json` or `yarn.lock` (Node.js)
   - `poetry.lock` (Python with Poetry)
   - `Cargo.lock` (Rust)
   - `go.sum` (Go)

7. **Test After Updates**
   - Run full test suite
   - Run linting/formatting
   - Test critical functionality manually
   - Check for deprecation warnings
   - Run integration tests
   - Test in staging environment

8. **Handle Update Failures**

   If tests fail after update:
   - Identify which dependency caused the issue
   - Check breaking changes in that dependency
   - Update code to fix compatibility
   - Or pin to previous version temporarily
   - Document why pinned

9. **Security Updates**

   Prioritize security updates:
   ```bash
   # Check for security vulnerabilities
   # Python
   pip-audit

   # Node.js
   npm audit
   npm audit fix

   # Go
   go list -json -m all | nancy sleuth

   # Rust
   cargo audit
   ```

10. **Update Development Dependencies**
    - Update testing frameworks
    - Update linters/formatters
    - Update build tools
    - Update documentation tools

## Update Strategies

**Conservative (Recommended):**
- Only update patch versions automatically
- Review minor versions carefully
- Major versions require manual review and testing

**Aggressive:**
- Update to latest versions regularly
- Useful for staying current but riskier

**Security-First:**
- Always update security patches immediately
- Other updates can wait

## Dependency Update Checklist

- [ ] List all outdated dependencies
- [ ] Review changelogs for breaking changes
- [ ] Check for security vulnerabilities
- [ ] Create a backup/branch for updates
- [ ] Update dependencies incrementally or all at once
- [ ] Update lock files
- [ ] Run full test suite
- [ ] Run linting and formatting checks
- [ ] Test critical functionality
- [ ] Review deprecation warnings
- [ ] Update documentation if needed
- [ ] Commit changes with descriptive message
- [ ] Deploy to staging and test
- [ ] Monitor for issues after deployment

## Best Practices

- Update dependencies regularly (weekly or monthly)
- Read changelogs before updating
- Update in small batches
- Test thoroughly after updates
- Use automated tools (Dependabot, Renovate)
- Pin specific versions in production
- Document why dependencies are pinned
- Keep development and production deps separate
- Review security advisories

## Output

Provide a dependency update report:
- **Dependencies Reviewed**: Total count of dependencies checked
- **Updates Available**: Count by severity (major/minor/patch)
- **Security Updates**: Critical security updates identified
- **Updated Dependencies**: List of packages updated
  - Package name
  - Old version → New version
  - Update type (patch/minor/major)
  - Breaking changes (if any)
- **Failed Updates**: Dependencies that couldn't be updated and why
- **Test Results**: Test suite status after updates
- **Breaking Changes**: Code changes needed for compatibility
- **Recommendations**: Further actions needed
