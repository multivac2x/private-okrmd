# Contributing to OKRMD

Thank you for your interest in contributing to OKRMD! This document provides guidelines and information for contributors.

---

## 📋 Table of Contents

- [Contributing to OKRMD](#contributing-to-okrmd)
  - [📋 Table of Contents](#-table-of-contents)
  - [Code of Conduct](#code-of-conduct)
  - [How to Contribute](#how-to-contribute)
    - [🐛 Reporting Bugs](#-reporting-bugs)
    - [💡 Suggesting Enhancements](#-suggesting-enhancements)
    - [📝 Improving Documentation](#-improving-documentation)
    - [🔧 Submitting Code Changes](#-submitting-code-changes)
  - [Development Setup](#development-setup)
  - [Style Guidelines](#style-guidelines)
    - [Markdown](#markdown)
    - [Writing Style](#writing-style)
    - [Version Numbers](#version-numbers)
    - [File Naming](#file-naming)
  - [Commit Messages](#commit-messages)
    - [Types](#types)
    - [Examples](#examples)
  - [Pull Request Process](#pull-request-process)
    - [Before Submitting](#before-submitting)
    - [Submitting](#submitting)
    - [After Merging](#after-merging)
  - [Versioning](#versioning)
    - [When Version Bumps Occur](#when-version-bumps-occur)
  - [Release Process](#release-process)
  - [Questions?](#questions)
  - [Thank You!](#thank-you)

---

## Code of Conduct

This project adheres to a code of conduct based on the [Contributor Covenant](https://www.contributor-covenant.org/). By participating, you are expected to:

- Be respectful and inclusive
- Accept constructive feedback
- Focus on what's best for the community
- Show empathy towards others

Instances of abusive or unacceptable behavior may be reported to [the maintainer](https://github.com/pescatoreluca).

---

## How to Contribute

There are many ways to contribute to OKRMD:

### 🐛 Reporting Bugs

- Check if the bug has already been reported in [Issues](https://github.com/pescatoreluca/okrmd/issues)
- If not, create a new issue with:
  - A clear, descriptive title
  - Steps to reproduce the behavior
  - Expected vs. actual behavior
  - Screenshots or code snippets if applicable
  - Your environment (OS, editor, OKRMD version)

### 💡 Suggesting Enhancements

- Search existing issues to avoid duplicates
- Create a new issue with:
  - A clear description of the enhancement
  - Why this enhancement would be useful
  - Examples of how it would work
  - Any potential drawbacks or alternatives considered

### 📝 Improving Documentation

- All documentation lives in the `tmp/` directory and this README
- Fix typos, clarify confusing sections, add examples
- Documentation changes don't require an issue — just submit a PR

### 🔧 Submitting Code Changes

- Fork the repository
- Create a feature branch
- Make your changes
- Submit a Pull Request (see below)

---

## Development Setup

OKRMD is documentation-first. There's no code to run, but you should:

1. **Clone your fork**:
   ```bash
   git clone https://github.com/YOUR-USERNAME/okrmd.git
   cd okrmd
   ```

2. **Add upstream remote**:
   ```bash
   git remote add upstream https://github.com/pescatoreluca/okrmd.git
   ```

3. **Create a branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Make changes** to documentation or templates

5. **Test your changes**:
   - Render markdown files in your editor to check formatting
   - Verify links work
   - Check that tables align properly

6. **Sync with upstream**:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

---

## Style Guidelines

### Markdown

- Use ATX-style headings (`#`, `##`, `###`)
- Keep lines under 100 characters for readability
- Use fenced code blocks with language specifiers:
  ````markdown
  ```bash
  command here
  ```
  ````
- Tables should have aligned columns (use a markdown formatter if needed)
- Use emoji sparingly for visual cues (✅ ❌ ⚠️)

### Writing Style

- Use active voice: "Create the file" not "The file should be created"
- Be concise but complete
- Use second person: "You" or "We" not "The user"
- Include examples for every concept
- Assume reader is technical but new to OKRMD

### Version Numbers

- All documentation must reference **OKRMD Standard v0.1**
- Update the `Changelog` section when making changes
- Do not change the version number in existing files — that's done during releases

### File Naming

- Use kebab-case: `my-file-name.md`
- Descriptive names: `quick-start-guide.md` not `guide.md`
- Keep existing file names unless there's a strong reason to change

---

## Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) format:

```
type(scope): subject

body

footer
```

### Types

- `docs`: Documentation changes
- `feat`: New feature (new document or major section)
- `fix`: Bug fix in content or examples
- `refactor`: Restructuring without changing behavior
- `test`: Adding or updating tests
- `chore`: Build/process changes

### Examples

```
docs(README): add quick start section

Add comprehensive quick start guide with examples
of creating config.md and first story.

Closes #42
```

```
fix(workflows): correct cycle planning duration

The cycle planning workflow incorrectly stated
1-2 hours for large teams. Updated to 2-4 hours.

Fixes #56
```

```
feat(autonomy): add decision guide table

Add comprehensive table mapping task types to
recommended autonomy levels.

Implements #33
```

---

## Pull Request Process

### Before Submitting

- [ ] Your changes are in a feature branch off `main`
- [ ] You've run through the [Development Setup](#development-setup) checklist
- [ ] All markdown renders correctly
- [ ] All links (internal and external) work
- [ ] No spelling or grammar errors
- [ ] You've updated any relevant documentation
- [ ] You've added a changelog entry if needed

### Submitting

1. Push your branch to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

2. Open a Pull Request against `pescatoreluca:main`

3. Fill out the PR template completely:
   - What does this PR do?
   - Why is this change needed?
   - Screenshots or examples (if applicable)
   - Related issues

4. Wait for review. Maintainers will:
   - Review code/content
   - Request changes if needed
   - Approve or discuss

5. Address review comments by pushing to your branch

6. Once approved, a maintainer will merge your PR

### After Merging

- Delete your feature branch (both locally and on GitHub)
- Pull the latest `main` to your local repo:
  ```bash
   git checkout main
   git pull upstream main
   ```
- Celebrate! 🎉

---

## Versioning

OKRMD follows [Semantic Versioning](https://semver.org/):

```
MAJOR.MINOR.PATCH
```

- **MAJOR** (1.0.0): Incompatible API changes (breaking changes to the standard)
- **MINOR** (0.2.0): Add functionality in a backward-compatible manner
- **PATCH** (0.1.1): Backward-compatible bug fixes

**Current version: 0.1** — This is the initial public release. We consider the core standard stable but expect refinements based on community feedback.

### When Version Bumps Occur

- **0.1 → 0.2**: New document types, new fields in existing templates, expanded conventions
- **0.1 → 1.0**: After 6-12 months of production use, when the standard is proven stable
- **0.1.0 → 0.1.1**: Typo fixes, clarification, example updates

---

## Release Process

Releases are managed by the core maintainers:

1. **Feature freeze**: No new features after date set for release
2. **Stabilization**: Bug fixes and documentation improvements only
3. **Version bump**: Update version numbers in all affected files
4. **Changelog**: Update `CHANGELOG.md` with all changes since last release
5. **Git tag**: Create annotated tag: `git tag -a v0.2.0 -m "Release 0.2.0"`
6. **GitHub release**: Draft release with changelog and upload assets
7. **Publish**: Publish the release on GitHub
8. **Announce**: Post announcement in Discussions and social media

---

## Questions?

- **General questions**: [GitHub Discussions](https://github.com/pescatoreluca/okrmd/discussions)
- **Specific issues**: [GitHub Issues](https://github.com/pescatoreluca/okrmd/issues)
- **Documentation feedback**: Open an issue with "docs:" prefix in title

---

## Thank You!

Your contributions make OKRMD better for everyone. Whether you're fixing a typo or proposing a major feature, we appreciate your time and expertise.

**Happy contributing!** 🚀
