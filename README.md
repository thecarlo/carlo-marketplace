# Claude Skills Collection

A collection of custom Claude skills for software development.

## Skills

### `commit-message`

Generates semantic git commit messages based on your staged changes with optional emoji support. Analyzes your diffs and creates conventional commit messages following best practices.

**Installation:**

```bash
/plugin marketplace add thecarlo/carlo-marketplace
/plugin install commit-message@carlo-marketplace
```

**Usage:**

```bash
/commit-message
```

[View detailed documentation](plugins/commit-message/README.md)

---

### `lambdakit-ts`

Bootstrap production-ready AWS Lambda functions with TypeScript using industry best practices. Includes serverless framework integration, proper error handling, logging, and local invocation setup out of the box.

**Installation:**

```bash
/plugin marketplace add thecarlo/carlo-marketplace
/plugin install lambdakit-ts@carlo-marketplace
```

**Usage:**

```bash
/lambdakit-ts
```

[View detailed documentation](plugins/lambdakit-ts/README.md)

---

### `zod`

Specialist for implementing and upgrading to Zod v4 validation schemas in TypeScript applications. Helps you create type-safe runtime validation with proper error handling and TypeScript inference, including migration from Zod v3.

**Installation:**

```bash
/plugin marketplace add thecarlo/carlo-marketplace
/plugin install zod@carlo-marketplace
```

**Usage:**

```bash
/zod
```

[View detailed documentation](plugins/zod/README.md)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Carlo van Wyk
