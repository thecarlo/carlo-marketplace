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

## Installation

### Option 1: Via Plugin Marketplace (Recommended)

Add this marketplace to Claude Code and install the skills:

```bash
/plugin marketplace add thecarlo/claude-skills
/plugin install lambdakit-ts@carlo-skills
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/claude-skills.git

# Add to your Claude Code skills directory
cp -r claude-skills/skills/* ~/.config/claude/skills/
```

## Usage

### Using LambdaKit TS

In your Claude Code session, in a new directory where you want to create a new lambda, ask Claude to use it:

### Prompt 1

```
/lambdakit-ts
```

### Prompt 2

```
/lambdakit-ts bootstrap a new lambda
```

### Prompt 2 (more granular)

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

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Carlo van Wyk
