---
name: commit-message
description: Create git commit messages based on current staged changes. Has support for git emoji messages.
---

# Git Commit Message

## Instructions

When this skill is invoked, follow these steps:

1. **Check for staged changes**: Run `git diff --cached` to see what changes are currently staged for commit
2. **If the user hasn't staged any changes**:
   - Generate an interactive yes/no prompt artifact asking "No changes have been staged yet. Would you like me to stage your changes?"
   - Upon confirmation, proceed by adding the staged changes
3. **If there are no changes to stage**:
   - Display response to the user: "No changes found. Please make changes to your files before trying to commit."
   - Stop and exit the skill.
4. **Get repository status**: Run `git status` to understand which files are affected
5. **Analyze the changes**: Review the diff output to understand:
   - What files were modified
   - What functionality changed
   - The purpose and impact of the changes
6. **Determine emoji usage**:
   - Search the user's original request for keywords like "emoji", "gitmoji", "with emoji", or "use emoji"
   - **By default (if no emoji keywords found)**: Generate the commit message in standard format WITHOUT any emojis
   - **If the user explicitly asks for emojis**: Add emojis using the mapping table below, placing the emoji before the type
7. **Generate commit message**: Create a commit message following the semantic commit format below, ensuring:
   - Appropriate commit type (feat, fix, docs, etc.)
   - Only put a gitmoji in first line if user specified gitmoji or emoji
   - Relevant scope based on affected codebase area
   - Clear, imperative subject line under 50 characters
   - Body and footer if needed for complex changes
   - Add line breaks in the body if there are multiple sentences.
8. **Present to user for commit approval**:
   - Display the formatted commit message for review (without showing the git command)
   - Generate an interactive yes/no prompt artifact asking "Would you like me to create this commit?"
   - Upon confirmation, proceed to create the commit
9. **Present to user for push confirmation**:
   - Once the commit is created, generate an interactive yes/no prompt asking "Would you like me to push this to the remote?"
   - Upon confirmation, proceed with the push operation

## Commands to get details of staged changes

**Note**: `git diff --cached` and `git diff --staged` are equivalent commands - both show staged changes.

### Show which files are staged, modified, or untracked

git status

### Show detailed line-by-line changes in staged files

git diff --staged

### Show summary of staged changes with file names and line counts

git diff --staged --stat

### Show detailed changes for a specific staged file

git diff --staged path/to/file

## Commit Message Format

The basic semantic message format is:

```text
<type>(<scope>): <subject>

<body>

<footer>
```

Where:

- `<type>`: The type of change (see list below)
- `<scope>`: Optional, the area of codebase affected
- `<subject>`: Brief description in imperative mood
- `<body>`: Optional, detailed explanation
- `<footer>`: Optional, references to issues or breaking changes

### Commit Types

The most common types are:

- feat: A new feature
- fix: A bug fix
- docs: Documentation changes
- style: Changes that don't affect code meaning (formatting, semicolons, etc.)
- refactor: Code changes that neither fix bugs nor add features
- perf: Changes that improve performance
- test: Adding or updating tests
- chore: Changes to build process, dependencies, or tooling

Scope is optional and specifies which part of the codebase is affected, like feat(auth): add login validation or fix(api): handle null responses.

Subject is a short, imperative description—start with a verb and keep it under 50 characters. Use present tense: "add feature" not "added feature."

Body is optional but useful for longer commits. It explains the why and what in more detail, usually wrapped at 72 characters. Separate it from the subject with a blank line.

Footer is optional and often used for referencing issues: Closes #123 or Fixes #456.

A practical example:
feat(checkout): add PayPal payment option

Added integration with PayPal's API to support additional
payment methods. This allows users to complete purchases
without entering credit card information.

Closes #234

## Git Emoji Messages

**Only use emojis when explicitly requested by the user.**

When emojis are requested, place the emoji at the start of the commit message, before the type. Format:

```text
<emoji> <type>(<scope>): <subject>
```

### Emoji Mappings to Types

| Type     | Emoji |
| -------- | ----- |
| feat     | ✨    |
| fix      | 🐛    |
| docs     | 📚    |
| style    | 💄    |
| refactor | ♻️    |
| perf     | ⚡    |
| test     | ✅    |
| chore    | 🔨    |
| ci       | 👷    |
| build    | 📦    |
| revert   | ⏮️    |
| security | 🔒    |
| deps     | 📦    |

**Example commit messages with emojis:**

✨ feat(auth): add two-factor authentication
🐛 fix(api): handle null responses correctly
📚 docs: update installation guide
💄 style(ui): reformat button component
♻️ refactor(core): simplify data processing logic
⚡ perf(database): optimize query performance
✅ test(utils): add edge case tests
🔨 chore: upgrade dependencies
👷 ci: add GitHub Actions workflow
📦 build: update webpack config
🔒 security: patch XSS vulnerability

## Guidelines for Commit Messages

When generating commit messages, follow these rules:

- **Capitalize the first letter** of the subject line
- **Keep the first line under 50 characters** for better readability in git logs
- **Be descriptive rather than technical**: Explain what changed from a functional perspective, not implementation details
- **Use imperative mood**: "add feature" not "added feature" or "adds feature"
- **Include scope when relevant**: Helps identify which part of the codebase is affected
- **Add body for additional context**: Explain the why and what in more detail when the subject alone isn't sufficient
- **Reference issues in footer**: Use "Closes #123" or "Fixes #456" when applicable

## Output Format

When presenting the generated commit message to the user, use this format:

```markdown
Here's the suggested commit message based on your staged changes:

​`
<generated commit message>
​`

To commit these changes, run:
​`bash
git commit -m "<generated message>"
​`

Or for a multi-line commit with body:
​`bash
git commit -m "<subject line>" -m "<body text>"
​`
```

## Important Notes

- **DO NOT run `git commit` without user approval**: Only generate the message, then ask for user approval to run the commit command
- **DO NOT stage additional files**: Only analyze what's already staged
- **If multiple unrelated changes are staged**: Suggest the user split them into separate commits for better history
- **Use recent commit history for context**: Run `git log --oneline -10` to understand the existing commit style and follow the same patterns
- **Analyze all staged files**: If there are many staged files, review each one to ensure the commit message accurately reflects all changes
