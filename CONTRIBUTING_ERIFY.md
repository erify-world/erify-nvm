# ERIFY™ Contribution Guidelines

Welcome to **ERIFY™ NVM**! We're building world-class Node.js version management with luxury enterprise features. Here's how to contribute effectively.

## 🎯 Before You Start

### Prerequisites
- ✅ Familiarity with shell scripting (bash, POSIX)
- ✅ Understanding of Node.js and npm
- ✅ Git workflow knowledge
- ✅ Commitment to ERIFY™ quality standards

### Repository Setup
```bash
# Fork and clone the repository
git clone https://github.com/YOUR_USERNAME/erify-nvm.git
cd erify-nvm

# Install dependencies
npm install

# Set up commit message template
git config commit.template .gitmessage.txt

# Add upstream remote
git remote add upstream https://github.com/nvm-sh/nvm.git
```

## 🏷️ Required Labels

**Every PR and issue MUST have:**
- **Category label** (exactly one): `category:feature`, `category:bug`, `category:docs`, `category:maintenance`, `category:security`, `category:performance`
- **Priority label** (exactly one): `priority:P0` (critical), `priority:P1` (high), `priority:P2` (medium), `priority:P3` (low)

See [docs/labels.md](docs/labels.md) for complete label documentation.

## 🔄 Contribution Workflow

### 1. Create a Feature Branch
```bash
# Use descriptive branch names
git checkout -b feature/enhanced-version-caching
git checkout -b fix/shell-compatibility-issue
git checkout -b docs/update-installation-guide
```

### 2. Make Changes
- ✅ Follow existing code patterns
- ✅ Preserve upstream compatibility
- ✅ Add/update tests for new functionality
- ✅ Update documentation as needed

### 3. Test Your Changes
```bash
# Run fast test suite
npm run test/fast

# Test in multiple shells
make test-bash
make test-zsh
make test-dash

# Verify ERIFY™ enhancements still work
python3 -m json.tool labels.json  # Validate labels
shellcheck nvm.sh install.sh      # Lint shell scripts
```

### 4. Commit with ERIFY™ Standards
```bash
# Use the commit template (automatically loaded)
git commit
# Follow the template format:
# feat: Add enhanced version caching system
#
# - Implement intelligent caching for version lookups
# - Reduce installation time by 40%
# - Add cache invalidation on version changes
#
# Closes #123
```

### 5. Submit Pull Request
- ✅ Use the PR template
- ✅ Add required labels (category + priority)
- ✅ Link related issues
- ✅ Request appropriate reviewers

## 🛡️ Code Quality Standards

### Shell Script Guidelines
```bash
# ✅ Good: Proper quoting
if [ -n "${NODE_VERSION}" ]; then

# ❌ Bad: Missing quotes
if [ -n $NODE_VERSION ]; then

# ✅ Good: Error handling
if ! command -v curl >/dev/null 2>&1; then
  nvm_err "curl is required but not installed"
  return 1
fi

# ✅ Good: Function naming
nvm_erify_enhanced_feature() {
  # ERIFY™ specific functions use nvm_erify_ prefix
}
```

### Security Requirements
- 🔒 Never commit secrets or credentials
- 🔒 Validate all user inputs
- 🔒 Use proper quoting to prevent injection
- 🔒 Avoid `eval` and unsafe shell operations
- 🔒 Follow principle of least privilege

### Testing Requirements
- ✅ All new features must have tests
- ✅ Preserve existing test compatibility
- ✅ Test across supported shells (bash, zsh, dash)
- ✅ Verify upstream compatibility

## 🌟 ERIFY™ Specific Guidelines

### Preserve Upstream Compatibility
```bash
# ✅ Good: Add new features without breaking existing ones
nvm_install() {
  # Existing upstream functionality
  nvm_install_original_logic "$@"
  
  # ERIFY™ enhancements
  if [ "${ERIFY_ENHANCED_MODE:-false}" = "true" ]; then
    nvm_erify_post_install_tasks
  fi
}

# ❌ Bad: Replacing core functionality
nvm_install() {
  # Completely different implementation
}
```

### File Preservation
These files should **never** be modified to match upstream:
- `.github/` directory (all ERIFY™ templates and workflows)
- `labels.json` and `docs/labels.md`
- `.gitmessage.txt`
- ERIFY™ sections in README.md

### Brand Consistency
- ✅ Use "ERIFY™" with trademark symbol
- ✅ Maintain professional tone
- ✅ Emphasize quality and luxury
- ✅ Reference "world-class" standards

## 🚦 Review Process

### Automated Checks
Your PR will be automatically validated for:
- ✅ Required labels (category + priority)
- ✅ Commit message format
- ✅ Code style and linting
- ✅ Security scanning
- ✅ Test coverage
- ✅ Multi-Node.js version compatibility

### Manual Review
Maintainers will review for:
- 🔍 Code quality and best practices
- 🔍 Upstream compatibility preservation
- 🔍 Security implications
- 🔍 Documentation completeness
- 🔍 ERIFY™ brand alignment

### Review Expectations
- 📝 **Constructive feedback**: We provide specific, actionable suggestions
- 🚀 **Rapid iteration**: Address feedback quickly for faster merging
- 🏆 **Excellence focus**: We maintain high standards for world-class software

## ❓ Getting Help

### Resources
- 📖 [Labels Documentation](docs/labels.md)
- 📋 [Code Review Guidelines](.github/CODE_REVIEW_GUIDELINES.md)
- 🔧 [Upstream NVM Documentation](https://github.com/nvm-sh/nvm)

### Support Channels
- 🎫 **Issues**: [Create an issue](https://github.com/erify-world/erify-nvm/issues/new/choose)
- 💬 **Discussions**: [Start a discussion](https://github.com/erify-world/erify-nvm/discussions)
- 📧 **Email**: [devops@erify.world](mailto:devops@erify.world)

### Maintainer Contact
For complex questions or architectural discussions:
- 👥 **Team**: `@erify-world/maintainers`
- 🛡️ **Security**: `@erify-world/security`
- 🏗️ **DevOps**: `@erify-world/devops`

---

## 🌟 Thank You!

By contributing to ERIFY™ NVM, you're helping build world-class Node.js version management tools. Every contribution matters, from small bug fixes to major features.

**Remember**: We're not just building software - we're crafting luxury developer experiences that set new standards for excellence.

*Welcome to the ERIFY™ family! 🚀*