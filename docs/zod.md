# Zod

Specialist for implementing and upgrading to Zod v4 validation schemas in TypeScript applications. Helps you create type-safe runtime validation with proper error handling and TypeScript inference, including migration from Zod v3.

## What it does

- Provides comprehensive Zod v4 implementation guidance with automatic version detection and v3 to v4 upgrade support
- Generates properly structured schema, interface, and validation files following SRP clean code principles
- Includes detailed error handling utilities and type-safe validation with z.infer
- Supports async validation, custom refinements, and common use cases (API, forms, environment variables)

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
/plugin install zod@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/carlo-marketplace.git

# Option A: Add to your Claude Code plugins directory
cp -r carlo-marketplace/plugins/zod ~/.config/claude/plugins/

# Option B: Add skill directly to your Claude Code skills directory
cp -r carlo-marketplace/plugins/zod/skills/zod ~/.config/claude/skills/
```

## Uninstalling

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, uninstall the plugin:

```bash
/plugin uninstall zod
```

To remove the marketplace entirely:

```bash
/plugin marketplace remove carlo-marketplace
```

## Usage

In your Claude Code session, ask Claude to use the Zod skill for validation tasks:

### Prompt 1 (auto detect skill)

```
implement zod validation
```

### Prompt 2

```
/zod
```

### Prompt 3

```
/zod create validation schema for user registration
```

### Prompt 4

```
create a validation schema for user registration using the zod skill
```
