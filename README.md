# Claude Skills Collection

A collection of custom Claude skills for software development.

## Available Skills

| Skill | Description | Documentation |
|-------|-------------|---------------|
| **LambdaKit TS** | TypeScript toolkit for bootstrapping AWS Lambda functions with production-ready best practices | [View Docs](docs/lambdakit-ts.md) |
| **Zod** | Zod v4 validation specialist for implementing type-safe validation in TypeScript applications | [View Docs](docs/zod.md) |

## Installation

### Option 1: Via Plugin Marketplace (Recommended)

First, add this marketplace to Claude Code:

```bash
/plugin marketplace add thecarlo/claude-marketplace
```

Then install the skill(s) you want:

**For LambdaKit TS:**
```bash
/plugin install lambdakit-ts@carlo-marketplace
```

**For Zod:**
```bash
/plugin install zod@carlo-marketplace
```

### Option 2: Clone this repository

```bash
# Clone the repository
git clone https://github.com/thecarlo/claude-skills.git

# Add to your Claude Code skills directory
cp -r claude-skills/skills/* ~/.config/claude/skills/
```

## Uninstalling

To uninstall individual skills:

**For LambdaKit TS:**
```bash
/plugin uninstall lambdakit-ts
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
- [LambdaKit TS Documentation](docs/lambdakit-ts.md)
- [Zod Documentation](docs/zod.md)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Carlo van Wyk
