# Claude Skills Collection

A collection of my custom Claude skills.

## Available Skills

### LambdaKit TS

A TypeScript toolkit for bootstrapping AWS Lambda functions with production-ready best practices.

**Location:** `skills/lambdakit-ts/`

**What it does:**

- Scaffolds a complete TypeScript AWS Lambda project structure
- Configures production-ready tooling (TypeScript, ESBuild, Prettier, ESLint)
- Sets up AWS Lambda Powertools for structured logging
- Configures Middy middleware for cross-cutting concerns
- Enforces clean code architecture with SRP (Single Responsibility Principle)
- Includes local invocation setup for testing

**Key Features:**

- API Gateway event source support (default)
- Aliased imports configured via tsconfig
- Production-grade error handling and logging
- Build and deployment scripts included
- Comprehensive linting and formatting rules
- Type-safe development with TypeScript strict mode

### Zod

A Zod v4 validation specialist for implementing type-safe validation in TypeScript applications.

**Location:** `skills/zod/`

**What it does:**

- Provides comprehensive guidance for Zod v4 validation implementation
- Checks project Zod version and offers upgrade path from v3 to v4
- Implements schema design patterns following clean code principles
- Generates properly structured schema, interface, and validation files
- Provides detailed error handling with Zod's issues array
- Includes complete migration guide from Zod 3 to Zod 4

**Key Features:**

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

Add this marketplace to Claude Code and install the skills:

```bash
# Add the marketplace
/plugin marketplace add thecarlo/claude-skills

# Install individual skills
/plugin install lambdakit-ts@carlo-skills
/plugin install zod@carlo-skills
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/claude-skills.git

# Add to your Claude Code skills directory
cp -r claude-skills/skills/* ~/.config/claude/skills/
```

## Usage

### Using the lambdakit-ts skill

In your Claude Code session, in a new directory where you want to create a new lambda, ask Claude to use it:

### Prompt 1

```
/lambdakit-ts
```

### Prompt 2

```
/lambdakit-ts bootstrap a new lambda
```

### Prompt 3

```
bootstrap a new lambda using the lambdakit-ts skill
```

The skill will:

1. Initialize a new npm project
2. Install all required dependencies
3. Create the proper directory structure
4. Configure TypeScript, ESLint, and Prettier
5. Generate starter code with best practices
6. Provide instructions for building and testing

### What Gets Created

After running LambdaKit TS, you'll have:

```
your-lambda/
├── src/
│   ├── functions/          # Individual function files (SRP)
│   │   └── greet.ts
│   ├── interfaces/         # TypeScript interfaces
│   ├── index.ts           # Main handler with middleware
│   └── local-invoke.ts    # Local testing script
├── dist/                  # Compiled output (after build)
├── build.sh              # Build script using esbuild
├── tsconfig.json         # TypeScript configuration
├── eslint.config.mjs     # ESLint rules
├── .prettierrc           # Prettier configuration
├── .gitignore
└── package.json
```

### Using the zod skill

In your Claude Code session, ask Claude to use the Zod skill for validation tasks:

#### Prompt 1

```
/zod
```

#### Prompt 2

```
/zod create validation schema for user registration
```

#### Prompt 3

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

### What Gets Created

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

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Carlo van Wyk
