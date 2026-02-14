# Git Commit Message Generator

A powerful CLI tool that analyzes your staged git changes and suggests conventional commit messages. Supports both rule-based and AI-powered suggestions.

## Features

- **Smart Analysis**: Analyzes staged changes to determine commit type
- **Conventional Commits**: Follows the [Conventional Commits](https://www.conventionalcommits.org/) specification
- **AI Support**: Optional AI-powered suggestions using OpenAI or Anthropic
- **Multiple Suggestions**: Get up to 5 different commit message options
- **Confidence Scoring**: Shows confidence level for each suggestion
- **Statistics**: View detailed change statistics
- **Auto-Apply**: Automatically apply the best suggestion

## Installation

```bash
# Clone the repository
git clone https://github.com/yksanjo/coding-tutor-v2.git
cd coding-tutor-v2

# Make executable
chmod +x git-commit-gen.py

# Optional: Add to PATH for global use
ln -s "$(pwd)/git-commit-gen.py" /usr/local/bin/git-commit-gen
```

## Usage

### Basic Usage

```bash
# Stage your changes
git add .

# Run the tool
python git-commit-gen.py
# or
./git-commit-gen.py
```

### Command Line Options

```bash
# Show statistics only
python git-commit-gen.py --stats

# Include AI-powered suggestion
python git-commit-gen.py --ai

# Automatically apply the best suggestion
python git-commit-gen.py --apply

# Disable colored output
python git-commit-gen.py --no-color
```

## Examples

### Interactive Mode

```
📋 Suggested Commit Messages:

  1. feat(auth): add user authentication
     Confidence: 85%
     Reason: AI-generated based on diff analysis

  2. feat: add new files
     Confidence: 70%
     Reason: All new files suggest a new feature

  3. docs: update documentation
     Confidence: 60%
     Reason: Changes primarily in docs files

Select option (1-5/c/q): 
```

### Statistics Mode

```
Change Statistics:
  Files: 3 added, 1 modified, 0 deleted
  Lines: +150 / -23
  File types: .py(2), .md(1), .json(1)
```

## Environment Variables

For AI-powered suggestions, set one of:

```bash
# For OpenAI
export OPENAI_API_KEY="your-api-key"

# For Anthropic
export ANTHROPIC_API_KEY="your-api-key"
```

## How It Works

1. **Analyzes Staged Changes**: Reads git diff of staged files
2. **Extracts Metadata**: Counts lines added/deleted, identifies file types
3. **Keyword Analysis**: Scans diff content for relevant keywords
4. **Classification**: Determines commit type (feat, fix, docs, etc.)
5. **Suggestion Generation**: Creates conventional commit messages

## Supported Commit Types

| Type | Description |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Code style changes |
| `refactor` | Code refactoring |
| `perf` | Performance improvements |
| `test` | Adding or correcting tests |
| `chore` | Build process, dependencies |
| `ci` | CI/CD configuration changes |
| `build` | Build system changes |
| `revert` | Reverting a previous commit |

## Requirements

- Python 3.7+
- Git

## License

MIT License

## Author

[yksanjo](https://github.com/yksanjo)

---

**Note**: This tool is part of the coding-tutor-v2 project. For more tools and utilities, check out the main repository.
