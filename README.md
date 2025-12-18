# Claude Commit

**Already using Claude Code? Get the commit message button you deserve – at no extra cost.**

A VS Code extension that brings the ✨ sparkle button to your Git panel, powered by the Claude CLI you already have. Generate intelligent commit messages without paying for additional AI services.

![Sparkle button in Git panel](screenshots/sparkle-button-demo.png)

## Why Claude Commit?

You're already investing in Claude Code – whether it's Pro, Max ×5, or Max ×10. Why pay for Copilot or Cursor just for commit message generation? This extension leverages your existing Claude subscription to bring the same AI-powered commit message functionality directly to VS Code.

**Zero additional cost. Zero complexity. Just works.**

## Features

- **One-click commit message generation**: The sparkle button ✨ you know and love, right in VS Code's Git panel
- **Powered by your Claude CLI**: Uses your existing Claude installation – no extra API keys or subscriptions
- **Context-aware analysis**: Understands your git diff to generate meaningful, conventional commit messages
- **Dead simple**: No configuration needed – install and go
- **Seamless VS Code integration**: Works directly with the built-in Git interface

## Requirements

- VS Code 1.103.0 or higher
- Claude CLI installed and authenticated (comes with your Claude Code subscription)
- Git repository initialized in your workspace
- Internet connection for AI generation

## Installation

1. Install the extension from the VS Code Marketplace
2. Ensure Claude CLI is installed and available in your system PATH
3. Open a project with a Git repository
4. Look for the sparkle ✨ button in your Git panel

## How to Use

1. Make your code changes
2. Stage your changes (optional – works with unstaged changes too)
3. Click the sparkle ✨ button next to the commit message input
4. Review the AI-generated commit message
5. Commit

That's it. No configuration, no setup wizards, no complexity.

## Extension Settings

This extension provides several optional settings to customize your experience:

- `claude-commit.claudePath`: Custom path to Claude CLI executable (auto-detects by default)
- `claude-commit.debugMode`: Enable debug output for troubleshooting
- `claude-commit.customInstructions`: Custom instructions for commit message generation
- `claude-commit.instructionsFilePath`: Path to a file containing custom commit message instructions

## Configuration Examples

### Using a custom Claude path

```json
{
    "claude-commit.claudePath": "/usr/local/bin/claude"
}
```

### Debug mode for troubleshooting

```json
{
    "claude-commit.debugMode": true
}
```

### Custom instructions (inline)

Provide custom rules directly in your settings:

```json
{
    "claude-commit.customInstructions": "Summarize changes into a single sentence suitable for release notes. Focus on user-facing impact rather than technical details."
}
```

### Custom instructions (from file)

Use a file to share commit message conventions across your team:

```json
{
    "claude-commit.instructionsFilePath": ".vscode/copilot/commit-message-instructions.md"
}
```

Then create `.vscode/copilot/commit-message-instructions.md`:

```markdown
# Commit Message Instructions

- Summarize changes into a sentence for release notes
- Focus on the "why" rather than the "what"
- Use imperative mood (e.g., "Add feature" not "Added feature")
- Maximum 50 characters for the subject line
- Include ticket number if applicable: [TICKET-123] Subject
```

The file path can be relative (from workspace root) or absolute. If both file and inline instructions are provided, the file takes precedence.

## Troubleshooting

### Claude CLI not found

If the extension can't find Claude CLI:

1. **Check Claude is installed**: Run in terminal:
   ```bash
   which claude
   ```
   This should show the path to Claude (e.g., `/Users/you/.nvm/versions/node/v22.13.0/bin/claude`)

2. **Set custom path in VS Code**:
   - Open VS Code Settings (Cmd+,)
   - Search for "claude-commit"
   - In "Claude Path", enter the full path from step 1

3. **Enable Debug Mode**:
   - Enable "Debug Mode" in settings
   - Open Output panel (View → Output)
   - Select "Claude Commit" from dropdown
   - Try generating a commit message and check logs

4. **Common issues**:
   - **NVM users**: VS Code might not see NVM paths – use the custom path setting
   - **macOS**: If using zsh, paths might differ between terminal and VS Code
   - **Authentication**: Ensure Claude CLI is authenticated by running `claude setup-token` in terminal

### No commit message generated

1. Ensure you have changes in your repository
2. Check that Claude CLI is properly authenticated
3. Enable debug mode to see the actual commands being executed

## Privacy & Security

- Your code changes are processed locally through Claude CLI
- No API keys are stored or transmitted by this extension
- Authentication is handled by your existing Claude CLI setup
- Code is only sent to Claude's servers through your authenticated CLI session

## Release Notes

### 1.0.1
- Streamlined configuration – removed unnecessary options for dead-simple operation
- Enhanced README to clarify value proposition for Claude Code users

### 1.0.0
- Complete refactor to use Claude CLI instead of Anthropic API
- Simplified configuration
- Hardcoded to use Sonnet model and conventional commit format
- Improved debug logging that only runs when debug mode is enabled
- New name: Claude Commit (formerly Claude Code AI Commit Message Button)

## Contributing

Found a bug or have a feature request? Please open an issue on our [GitHub repository](https://github.com/juanlb/claude-commit).

## License

MIT License - see LICENSE file for details.

---

**Stop paying twice for AI commit messages. You've got Claude Code – now get the commit button. ✨**
