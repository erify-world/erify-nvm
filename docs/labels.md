# ERIFY™ Repository Labels

This document describes the standardized labeling system used in ERIFY™ repositories for consistent project management and organization.

## Label Categories

### Category Labels (Required)
Every issue and pull request must have exactly one category label:

- **`category:feature`** - New feature or functionality
- **`category:bug`** - Bug fix or error correction  
- **`category:docs`** - Documentation updates
- **`category:maintenance`** - Maintenance, refactoring, or chores
- **`category:security`** - Security-related changes
- **`category:performance`** - Performance improvements

### Priority Labels (Required)
Every issue and pull request must have exactly one priority label:

- **`priority:P0`** - Critical - Immediate attention required
- **`priority:P1`** - High - Important, should be addressed soon
- **`priority:P2`** - Medium - Normal priority
- **`priority:P3`** - Low - Can be addressed when convenient

### Status Labels (Optional)
Used to track workflow states:

- **`status:blocked`** - Blocked by external dependency
- **`status:in-progress`** - Currently being worked on
- **`status:needs-review`** - Ready for review

### ERIFY™ Specific Labels
Labels specific to ERIFY™ operations:

- **`erify:enhancement`** - ERIFY™ brand enhancement
- **`upstream:sync`** - Related to upstream synchronization
- **`breaking-change`** - Contains breaking changes

## Usage Guidelines

### For Issues
1. **Always apply both a category and priority label** when creating issues
2. Add status labels as work progresses
3. Use ERIFY™ specific labels for brand-related work

### For Pull Requests
1. **Category and priority labels are enforced** - PRs without both will be blocked
2. Add appropriate status labels during review process
3. Mark breaking changes with the `breaking-change` label

### Label Automation
- Labels are automatically synchronized from `labels.json`
- PR label guards enforce required labeling
- Branch protection rules may require specific labels

## Color Coding
- **Red tones**: Critical items (P0, security, bugs)
- **Yellow tones**: Important items (P1, maintenance)
- **Green tones**: Normal/low priority items
- **Blue tones**: Documentation and features
- **Purple tones**: ERIFY™ brand and special workflow items

## Maintenance
Labels are managed through:
- `labels.json` - Source of truth for all labels
- `.github/workflows/labels.yml` - Automated label synchronization
- Manual GitHub settings for any emergency changes

For questions about labeling standards, contact the ERIFY™ DevOps team.