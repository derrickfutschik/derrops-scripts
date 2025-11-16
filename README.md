# DerrOps Scripts

A collection of helper scripts to automate common development tasks, powered by Claude Code and AI.

## Scripts

### > ai-commit.sh

AI-powered git commit message generator that creates conventional commit messages with emojis.

**Features:**
- Generates conventional commit format messages (`type(scope): description`)
- Supports custom context via CLI argument or interactive editor
- Automatically handles staging prompts for unstaged/untracked files
- Opens your preferred editor for reviewing and editing the generated message before committing
- Uses emojis to make commit history more visual and scannable
- Follows best practices: imperative mood, 72-character limit, descriptive but concise

**Usage:**

```bash
# Generate commit message from staged changes
./ai-commit.sh

# Provide context as an argument
./ai-commit.sh "Fixed debug configuration so that now debug is working"

# Use interactive editor to provide context
./ai-commit.sh --context
```

**Requirements:**
- [Claude Code CLI](https://claude.com/claude-code) installed and available as `claude`
- Git repository
- Text editor (vim, or configured in `git config core.editor`, or `$EDITOR`)

**Workflow:**
1. Analyzes your staged changes (or prompts you to stage changes if needed)
2. Uses Claude to generate a conventional commit message based on the diff
3. Opens the generated message in your editor for review/modification
4. Commits with the finalized message

**Commit Message Format:**

The script generates messages following conventional commits with emoji prefixes:

- ( `feat`: New features
- = `fix`: Bug fixes
- =Ý `docs`: Documentation changes
- { `refactor`: Code refactoring
- <¨ `style`: Code style/formatting
- ¡ `perf`: Performance improvements
-  `test`: Tests
- =' `chore`: Configuration/tooling
- =€ `deploy`: Deployments
- =% `remove`: Removing code/files
- =¥ `breaking`: Breaking changes

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd derrops-scripts
   ```

2. Make scripts executable:
   ```bash
   chmod +x *.sh
   ```

3. (Optional) Add to your PATH:
   ```bash
   echo 'export PATH="$PATH:/path/to/derrops-scripts"' >> ~/.bashrc
   # or for zsh
   echo 'export PATH="$PATH:/path/to/derrops-scripts"' >> ~/.zshrc
   ```

## Contributing

Feel free to add more automation scripts to this collection! Each script should:
- Have clear documentation at the top explaining usage
- Follow shell scripting best practices
- Include helpful error messages
- Use colors for better UX (see ai-commit.sh for examples)

## License

MIT
