# Claude Skills Collection

A collection of custom Claude skills for software development.

## Available Skills

| Skill               | Description                                                                                                  | Documentation                          |
| ------------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------- |
| **Commit Message**  | Create semantic git commit messages based on staged changes with optional emoji support                     | [View Docs](docs/commit-message.md)   |
| **LambdaKit TS**    | TypeScript toolkit for bootstrapping AWS Lambda functions with production-ready best practices              | [View Docs](docs/lambdakit-ts.md)     |
| **Zod**             | Zod v4 validation specialist for implementing type-safe validation in TypeScript applications               | [View Docs](docs/zod.md)              |

## Installation

### Option 1: Via Plugin Marketplace (Recommended)

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, add this marketplace:

```bash
/plugin marketplace add thecarlo/carlo-marketplace
```

Install the skill(s) you want:

**For Commit Message:**

```bash
/plugin install git@carlo-marketplace
```

**For LambdaKit TS:**

```bash
/plugin install aws@carlo-marketplace
```

**For Zod:**

```bash
/plugin install zod@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/carlo-marketplace.git

# Add to your Claude Code plugins directory
cp -r carlo-marketplace/plugins/* ~/.config/claude/plugins/
```

## Uninstalling

Launch Claude Code first:

```bash
claude
```

Then from within Claude Code, uninstall individual skills:

**For Commit Message:**

```bash
/plugin uninstall git
```

**For LambdaKit TS:**

```bash
/plugin uninstall aws
```

**For Zod:**

```bash
/plugin uninstall zod
```

To remove the marketplace entirely:

```bash
/plugin marketplace remove carlo-marketplace
```

## Usage

See individual skill documentation for detailed usage instructions and examples:

- [Commit Message Documentation](docs/commit-message.md)
- [LambdaKit TS Documentation](docs/lambdakit-ts.md)
- [Zod Documentation](docs/zod.md)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Carlo van Wyk
