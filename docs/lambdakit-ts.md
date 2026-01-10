# LambdaKit TS

A TypeScript toolkit for bootstrapping AWS Lambda functions with production-ready best practices.

## What it does

- Scaffolds a complete TypeScript AWS Lambda project structure
- Configures production-ready tooling (TypeScript, ESBuild, Prettier, ESLint)
- Sets up AWS Lambda Powertools for structured logging
- Configures Middy middleware for cross-cutting concerns
- Enforces clean code architecture with SRP (Single Responsibility Principle)
- Includes local invocation setup for testing

## Key Features

- API Gateway event source support (default)
- Aliased imports configured via tsconfig
- Production-grade error handling and logging
- Build and deployment scripts included
- Comprehensive linting and formatting rules
- Type-safe development with TypeScript strict mode

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
/plugin install lambdakit-ts@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/carlo-marketplace.git

# Add to your Claude Code plugins directory
cp -r carlo-marketplace/plugins/lambdakit-ts ~/.config/claude/plugins/
```

## Uninstalling

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, uninstall the plugin:

```bash
/plugin uninstall lambdakit-ts
```

## Usage

In your Claude Code session, in a new directory where you want to create a new lambda, ask Claude to use it:

### Prompt 1 (auto detect skill)

```
create a new typescript lambda
```

### Prompt 2

```
/lambdakit-ts
```

### Prompt 3

```
/lambdakit-ts bootstrap a new lambda
```

### Prompt 4

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

## What Gets Created

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
