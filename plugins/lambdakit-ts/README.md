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

## Available Scripts

Your `package.json` includes the following scripts:

| Script | Command | Description |
|--------|---------|-------------|
| `typecheck` | `tsc --noEmit` | Runs TypeScript type checking without emitting files |
| `build` | `bash build.sh` | Builds the project using esbuild (creates optimized bundle) |
| `invoke:local` | `npx tsx src/local-invoke.ts` | Runs the Lambda locally for testing |
| `prettier` | `prettier --check` | Checks code formatting against Prettier rules |
| `prettier:fix` | `prettier --write` | Auto-formats all TypeScript and JSON files |
| `lint` | `eslint .` | Checks code against ESLint rules |
| `lint:fix` | `eslint . --fix` | Auto-fixes ESLint issues where possible |

## Building Your Lambda

### Build the project

```bash
npm run build
```

This runs `build.sh`, which uses esbuild to:
- Compile TypeScript to JavaScript
- Bundle all dependencies into a single file
- Optimize and minify the code
- Output to `dist/index.js`

The build output is ready for deployment to AWS Lambda.

### Type checking

```bash
npm run typecheck
```

Validates TypeScript types without creating output files. Useful for catching type errors during development.

## Local Testing

Test your Lambda locally before deploying:

```bash
npm run invoke:local
```

This executes `src/local-invoke.ts`, which simulates an API Gateway event and invokes your Lambda handler locally. Modify this file to test different scenarios.

## Code Quality

### Format code with Prettier

```bash
# Check formatting
npm run prettier

# Auto-fix formatting
npm run prettier:fix
```

### Lint with ESLint

```bash
# Check for lint issues
npm run lint

# Auto-fix lint issues
npm run lint:fix
```

## Development Workflow

1. Write your Lambda code following SRP principles
2. Run `npm run typecheck` to verify types
3. Run `npm run invoke:local` to test locally
4. Run `npm run prettier:fix` to format code
5. Run `npm run lint:fix` to fix linting issues
6. Run `npm run build` to create deployment bundle
7. Deploy `dist/index.js` to AWS Lambda
