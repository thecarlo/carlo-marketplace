# LambdaKit TS

Bootstrap production-ready AWS Lambda functions with TypeScript using industry best practices. Includes serverless framework integration, proper error handling, logging, and local invocation setup out of the box.

## What it does

- Scaffolds complete TypeScript Lambda project with production-ready tooling (ESBuild, Prettier, ESLint)
- Sets up AWS Lambda Powertools for logging and Middy middleware for cross-cutting concerns
- Enforces clean code architecture with SRP, aliased imports, and strict TypeScript
- Includes local invocation setup and build scripts for testing and deployment

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

# Option A: Add to your Claude Code plugins directory
cp -r carlo-marketplace/plugins/lambdakit-ts ~/.config/claude/plugins/

# Option B: Add skill directly to your Claude Code skills directory
cp -r carlo-marketplace/plugins/lambdakit-ts/skills/lambdakit-ts ~/.config/claude/skills/
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

To remove the marketplace entirely:

```bash
/plugin marketplace remove carlo-marketplace
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
