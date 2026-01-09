---
name: LambdaKit TS
description: A TypeScript (TS) toolkit for bootstrapping AWS Lambda functions with production-ready best practices.
---

# LambdaKit TS

## Quickstart

Bootstrap a new TypeScript AWS Lambda using the instructions below.

If the desired event source is not specified, create a Lambda with API Gateway as the event source.

If a name is not specified, use the name of the current directory.

Start with:

1. create package.json with `npm init -y`
2. install dev dependencies `npm install -D @types/aws-lambda @types/node esbuild typescript prettier eslint eslint-plugin-prettier eslint-plugin-check-file eslint-config-prettier @typescript-eslint/parser @typescript-eslint/eslint-plugin`
3. install runtime dependencies `npm install @aws-lambda-powertools/logger @middy/core`
4. run `mkdir -p src/functions src/interfaces` to create the directories
5. copy the provided `assets/tsconfig.json` file
6. copy the provided `assets/eslint.config.mjs` file
7. copy the provided `assets/index.ts` file and change the `serviceName` value according to the provided name or directory name
8. copy the provided `assets/local-invoke.ts` file and change the `functionName` value according to the provided name or directory name
9. copy the provided `assets/greet.ts` file and copy it to the `src/functions/` directory
10. copy the provided `build.sh` file and run `chmod + x` to assign execute permissions
11. copy the provided `.prettierrc` file
12. copy the provided `.gitignore` file
13. add scripts to `package.json` from the section `add package.json scripts` below
14. when done, add instructions to the output as per the `Final Instructions` section below

## Code Organization Principles

### add package.json scripts

add the following scripts in `package.json`:

```json
{
  "scripts": {
    "typecheck": "tsc --noEmit",
    "build": "bash build.sh",
    "invoke:local": "npx tsx src/local-invoke.ts",
    "prettier": "prettier --check '**/*.{ts,json}'",
    "prettier:fix": "prettier --write '**/*.{ts,json}'",
    "lint": "eslint . --ext .ts",
    "lint:fix": "eslint . --ext .ts --fix"
  }
}
```

### Final Instructions

- To build the project, run `npm run build`
- To autoformat using prettier, run `npm run prettier:fix`
- To autofix lint issues, run `npm run lint:fix`

## Best Practices

1. Use async/await syntax instead of promises
2. Use import statements instead of require where possible
3. Use aliased imports as defined in `tsconfig.json`
4. Use Middy middleware for cross-cutting concerns
5. Use AWS Lambda Powertools for structured logging
6. Always include proper error handling with appropriate logging
7. When creating other functions, pass the instance of the logger to those functions so that the context and properties can be persisted across logs
8. Use the Single Responsibility Principle (SRP) to rnsure good separation of concerns.
9. SRP: Ensure a single export per file
10. SRP: Always create separate files for functions and store functions in `src/functions`
11. SRP: Prefer interfaces over types and store interfaces in `src/interfaces`
