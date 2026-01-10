# Commit Message

Create semantic git commit messages based on staged changes with optional emoji support.

## What it does

- Analyzes your staged git changes to understand what was modified
- Generates semantic commit messages following conventional commit format
- Supports optional git emoji prefixes for visual commit logs
- Reviews recent commit history to maintain consistent style
- Provides clear commit type classification (feat, fix, docs, etc.)
- Asks for user approval before creating the commit

## Key Features

- Automatic change analysis from `git diff --staged`
- Semantic commit format with type, scope, and description
- Optional emoji support with type-specific mappings
- Multi-line commit messages with body and footer sections
- Issue reference support (Closes #123, Fixes #456)
- Follows conventional commit guidelines
- Imperative mood and proper capitalization
- Co-authored by Claude attribution

## Installation

### Option 1: Via Plugin Marketplace (Recommended)

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, add the marketplace and install the skill:

```bash
# Add the marketplace
/plugin marketplace add thecarlo/carlo-marketplace

# Install the plugin
/plugin install commit-message@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/carlo-marketplace.git

# Add to your Claude Code plugins directory
cp -r carlo-marketplace/plugins/commit-message ~/.config/claude/plugins/
```

## Uninstalling

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, uninstall the plugin:

```bash
/plugin uninstall commit-message
```

## Usage

In your Claude Code session, after staging your changes with `git add`, ask Claude to create a commit message:

### Prompt 1 (auto detect skill)

```
create a git commit message
```

### Prompt 2

```
/commit-message
```

### Prompt 3

```
/commit-message create a commit message
```

### Prompt 4

```
use the commit-message skill to create a commit message
```

### With Emoji Support

To include git emojis in your commit message:

```
create a git commit message with a gitmoji
```

```
/commit-message with emojis
```

```
use the commit-message skill to create a commit with an emoji
```

The skill will:

1. Check for staged changes using `git diff --staged`
2. Analyze the changes to understand what was modified
3. Review recent commit history for style consistency
4. Generate a semantic commit message with appropriate type and scope
5. Include emoji prefix if requested
6. Display the commit message for your review
7. Ask for your approval before creating the commit
8. Execute the git commit with co-authorship attribution

## Commit Message Format

The skill generates commits in this format:

```
[emoji] type(scope): subject

body

footer
```

### Commit Types

| Type     | Description                      | Emoji |
| -------- | -------------------------------- | ----- |
| feat     | A new feature                    | ✨    |
| fix      | A bug fix                        | 🐛    |
| docs     | Documentation changes            | 📚    |
| style    | Code formatting changes          | 💄    |
| refactor | Code refactoring                 | ♻️    |
| perf     | Performance improvements         | ⚡    |
| test     | Adding or updating tests         | ✅    |
| chore    | Build process or tooling changes | 🔨    |
| ci       | CI/CD changes                    | 👷    |
| build    | Build system changes             | 📦    |
| revert   | Reverting previous changes       | ⏮️    |
| security | Security fixes                   | 🔒    |

### Example Commits

**Without emoji:**

```
feat(auth): add two-factor authentication

Implements TOTP-based 2FA for enhanced security. Users can enable
2FA in their account settings and use authenticator apps.

Closes #234
```

**With emoji:**

```
✨ feat(auth): add two-factor authentication

Implements TOTP-based 2FA for enhanced security. Users can enable
2FA in their account settings and use authenticator apps.

Closes #234
```

**Simple commit:**

```
fix(api): handle null responses correctly
```

**With emoji:**

```
🐛 fix(api): handle null responses correctly
```

## Guidelines

The skill follows these commit message best practices:

- **Type classification**: Accurately identifies the nature of changes (feat, fix, docs, etc.)
- **Scope definition**: Identifies the affected area of the codebase
- **Subject line**: Clear, imperative mood, under 50 characters, capitalized
- **Body text**: Optional detailed explanation wrapped at 72 characters
- **Issue references**: Includes footer with "Closes #123" or "Fixes #456" when relevant
- **Consistency**: Matches the style of recent commits in your repository
- **Co-authorship**: Adds Claude Sonnet 4.5 as co-author

## What Happens

When you use the commit-message skill:

1. The skill checks your staged changes
2. If no changes are staged, you'll be prompted to stage files first
3. The skill analyzes the diff to understand modifications
4. It reviews recent commits to match your repository's style
5. A commit message is generated and displayed for review
6. You're asked: "Would you like me to create this commit for you?"
7. Upon approval, the commit is created with co-authorship attribution
8. The commit hash is displayed for confirmation

## Requirements

- Git repository (the skill works within git repositories)
- Staged changes (use `git add` to stage files before using the skill)
- Claude Code CLI environment

## Tips

- Stage related changes together for better commit messages
- Use the skill consistently to maintain clean commit history
- Add emojis if your team prefers visual commit logs
- Review the generated message before approving
- Split unrelated changes into separate commits for clarity
