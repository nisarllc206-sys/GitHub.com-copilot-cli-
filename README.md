# GitHub Copilot CLI

> AI-powered coding assistant for your terminal — integrates GitHub Copilot directly into your CLI workflow.

GitHub Copilot CLI brings AI-powered code suggestions, completions, and automation directly to your terminal. Boost your productivity by generating code snippets, getting context-aware suggestions, and automating repetitive tasks without leaving the command line.

---

## Features

- **AI Code Generation** — Generate code snippets and full functions from natural-language descriptions.
- **Context-Aware Suggestions** — Get intelligent completions based on your project's code and context.
- **Multi-Language Support** — Works across popular languages including JavaScript, TypeScript, Python, Go, Rust, and more.
- **Shell Command Assistance** — Translate plain-English requests into shell commands.
- **Explain & Document Code** — Ask Copilot to explain or add documentation to existing code.
- **Automate Repetitive Tasks** — Script and automate common development workflows from the terminal.

---

## Prerequisites

- [Node.js](https://nodejs.org/) v16 or higher
- A [GitHub account](https://github.com) with an active [GitHub Copilot](https://github.com/features/copilot) subscription
- GitHub CLI (`gh`) installed and authenticated — [install guide](https://cli.github.com/)

---

## Installation

Install the GitHub Copilot CLI extension via the GitHub CLI:

```bash
gh extension install github/gh-copilot
```

Verify the installation:

```bash
gh copilot --version
```

---

## Authentication

Make sure you are authenticated with the GitHub CLI:

```bash
gh auth login
```

Follow the prompts to authenticate with your GitHub account. Once authenticated, the Copilot CLI extension will use your credentials automatically.

---

## Usage

### Suggest a Shell Command

Ask Copilot to suggest a shell command based on a plain-English description:

```bash
gh copilot suggest "list all running docker containers"
```

### Explain a Shell Command

Get an explanation of what a shell command does:

```bash
gh copilot explain "git rebase -i HEAD~3"
```

### Generate Code

Use the `--target` flag to specify the type of output:

```bash
# Suggest a shell command
gh copilot suggest -t shell "compress a folder into a tar.gz archive"

# Suggest a GitHub CLI command
gh copilot suggest -t gh "create a new pull request from current branch"

# Suggest a Git command
gh copilot suggest -t git "undo the last commit but keep the changes staged"
```

### Interactive Mode

Run without arguments to enter interactive mode:

```bash
gh copilot suggest
```

You will be prompted to enter your request and select the target type (shell, git, or gh command).

---

## Configuration

You can configure the extension's default behavior using the `gh` configuration file or environment variables.

### Set Default Target Type

```bash
gh config set copilot.target shell
```

### Available Configuration Keys

| Key | Description | Default |
|-----|-------------|---------|
| `copilot.target` | Default command type (`shell`, `git`, `gh`) | `shell` |

---

## Examples

```bash
# Find all files larger than 100MB
gh copilot suggest "find all files larger than 100MB in the current directory"

# Create and push a new Git branch
gh copilot suggest -t git "create a new branch called feature/login and push it to origin"

# Open a pull request with GitHub CLI
gh copilot suggest -t gh "open a pull request targeting the main branch"

# Explain a complex command
gh copilot explain "awk '{print $1}' access.log | sort | uniq -c | sort -rn | head -10"
```

---

## Updating

To update the Copilot CLI extension to the latest version:

```bash
gh extension upgrade gh-copilot
```

---

## Uninstalling

To remove the extension:

```bash
gh extension remove gh-copilot
```

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m "Add my feature"`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

---

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file included in this repository.

---

## Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [GitHub Copilot for CLI — Blog Post](https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/)

