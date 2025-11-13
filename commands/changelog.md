Generate or update the CHANGELOG for the project.

## Instructions

1. **Check for Existing Changelog**
   - Look for `CHANGELOG.md` or `HISTORY.md` in the repository root
   - Review the format (Keep a Changelog, conventional, custom)

2. **Gather Changes Since Last Release**
   - Get the last release tag: `git describe --tags --abbrev=0`
   - List commits since last release: `git log <last-tag>..HEAD --oneline`
   - Review merged pull requests
   - Check closed issues
   - Review git commits for unreleased changes

3. **Categorize Changes**
   - **Added**: New features, enhancements
   - **Changed**: Changes to existing functionality
   - **Deprecated**: Features marked for removal
   - **Removed**: Removed features
   - **Fixed**: Bug fixes
   - **Security**: Security-related fixes

4. **Format Entries**
   - Use Keep a Changelog format (recommended)
   - Include dates in ISO 8601 format (YYYY-MM-DD)
   - Link to issues and PRs
   - Keep entries concise and user-focused
   - Highlight breaking changes

5. **Update CHANGELOG.md**
   - Add new `## [Unreleased]` section if not present
   - Or add new `## [X.Y.Z] - YYYY-MM-DD` section for a release
   - Organize entries by category
   - Ensure most recent changes are at the top

## Keep a Changelog Format

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- New feature X for improved performance (#123)

### Fixed
- Bug in feature Y that caused crashes (#456)

## [1.2.0] - 2025-01-15

### Added
- New API endpoint for user management (#100)
- Support for multiple databases (#110)

### Changed
- Improved error messages in validation module (#105)

### Deprecated
- `oldFunction()` will be removed in v2.0.0 (#115)

### Fixed
- Memory leak in background worker (#120)

## [1.1.0] - 2024-12-01

...
```

## Best Practices

- Write for users, not developers (avoid technical jargon)
- Focus on changes that affect users, not internal refactoring
- Link to issues/PRs for context
- Highlight breaking changes prominently
- Keep entries concise and scannable
- Use consistent formatting
- Update changelog with every significant change
- Don't include every commit, only notable changes

## Output

Provide:
- **Unreleased Changes**: List of changes since last release
- **Categorized Entries**: Changes organized by type
- **Formatted Changelog**: Ready-to-use changelog entries
- **Breaking Changes**: Any breaking changes highlighted
- **Migration Notes**: If breaking changes exist, provide migration guidance
