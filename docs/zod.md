# Zod

A Zod v4 validation specialist for implementing type-safe validation in TypeScript applications.

## What it does

- Provides comprehensive guidance for Zod v4 validation implementation
- Checks project Zod version and offers upgrade path from v3 to v4
- Implements schema design patterns following clean code principles
- Generates properly structured schema, interface, and validation files
- Provides detailed error handling with Zod's issues array
- Includes complete migration guide from Zod 3 to Zod 4

## Key Features

- Zod v4 exclusive syntax and breaking changes reference
- Automatic version detection with upgrade prompts
- Schema organization with SRP (single export per file)
- Error formatting utilities (flattenError, treeifyError, prettifyError)
- Type inference with z.infer for compile-time type safety
- Comprehensive quick reference tables for v3 to v4 migration
- Async validation and custom refinement patterns
- API, form, and environment variable validation use cases

## Installation

### Option 1: Via Plugin Marketplace (Recommended)

Add this marketplace to Claude Code and install the skill:

```bash
# Add the marketplace
/plugin marketplace add thecarlo/carlo-marketplace

# Install the skill
/plugin install zod@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/claude-skills.git

# Add to your Claude Code skills directory
cp -r claude-skills/skills/zod ~/.config/claude/skills/
```

## Uninstalling

To uninstall this skill:

```bash
/plugin uninstall zod
```

## Usage

In your Claude Code session, ask Claude to use the Zod skill for validation tasks:

### Prompt 1

```
/zod
```

### Prompt 2

```
/zod create validation schema for user registration
```

### Prompt 3

```
create a validation schema for user registration using the zod skill
```

The skill will:

1. Check your project's Zod version (v3 or v4)
2. Offer to upgrade from v3 to v4 if needed
3. Create properly structured schema files in `src/schemas/`
4. Generate corresponding interface files in `src/interfaces/`
5. Implement validation functions in `src/functions/`
6. Use Zod v4 syntax exclusively (top-level validators, error parameter)
7. Provide comprehensive error handling with formatted errors

## What Gets Created

After using the Zod skill, you'll have:

```
your-project/
├── src/
│   ├── schemas/
│   │   └── user-registration.schema.ts    # Zod schema definition
│   ├── interfaces/
│   │   └── user-registration.interface.ts # Type-safe interface
│   └── functions/
│       └── validate-user-registration.ts  # Validation function with error handling
└── package.json                           # With zod@^4.0.0
```
