Prepare a new release for the project.

## Instructions

1. **Pre-Release Checklist**
   - Verify all tests pass
   - Check that linting passes
   - Ensure documentation is up to date
   - Review open issues/PRs for blockers
   - Verify dependencies are up to date (security patches)
   - Check that CI/CD pipeline is green

2. **Version Bump**
   - Determine version number using semantic versioning:
     - MAJOR: Breaking changes
     - MINOR: New features (backward compatible)
     - PATCH: Bug fixes (backward compatible)
   - Update version in all relevant files:
     - `package.json` (JavaScript)
     - `pyproject.toml` or `setup.py` (Python)
     - `Cargo.toml` (Rust)
     - `go.mod` (Go)
   - Update version in documentation if applicable

3. **Update Changelog**
   - Follow Keep a Changelog format
   - Add a new version section with release date
   - Categorize changes:
     - **Added**: New features
     - **Changed**: Changes to existing functionality
     - **Deprecated**: Soon-to-be removed features
     - **Removed**: Removed features
     - **Fixed**: Bug fixes
     - **Security**: Security fixes
   - Link to relevant issues/PRs
   - Highlight breaking changes prominently

4. **Review Release Notes**
   - Write user-facing release notes
   - Highlight key features and improvements
   - Document breaking changes with migration guides
   - Include upgrade instructions
   - Thank contributors

5. **Create Release Commit**
   - Commit version bump and changelog
   - Use conventional commit format: `chore(release): prepare vX.Y.Z`
   - Tag the commit: `git tag -a vX.Y.Z -m "Release vX.Y.Z"`

6. **Pre-Release Testing**
   - Build the release artifacts
   - Test the build in a clean environment
   - Verify installation process works
   - Run smoke tests on the release build

7. **Create GitHub Release**
   - Push the tag: `git push origin vX.Y.Z`
   - Create release on GitHub using `gh release create`
   - Include release notes
   - Attach build artifacts if applicable

## Semantic Versioning

Given a version number MAJOR.MINOR.PATCH:
- **MAJOR**: Incompatible API changes
- **MINOR**: Add functionality (backward compatible)
- **PATCH**: Bug fixes (backward compatible)

Examples:
- `1.0.0` → `1.0.1` (bug fix)
- `1.0.1` → `1.1.0` (new feature)
- `1.1.0` → `2.0.0` (breaking change)

## Output

Provide a release preparation summary:
- **Version**: New version number and rationale
- **Changes**: Summary of changes in this release
- **Changelog**: Updated CHANGELOG.md content
- **Release Notes**: Draft release notes
- **Checklist**: Pre-release checklist completion status
- **Tag Created**: Git tag information
- **Next Steps**: Instructions for publishing the release
