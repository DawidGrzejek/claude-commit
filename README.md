# Claude Commit

A VS Code extension that adds an AI-powered sparkle button ✨ to your Git panel for generating intelligent commit messages using Claude CLI.

![Sparkle button in Git panel](screenshots/sparkle-button-demo.png)

## Features

- **One-click commit message generation**: Add a sparkle button directly in VS Code's Git panel
- **Powered by Claude CLI**: Uses your local Claude installation to analyze changes and generate meaningful commit messages
- **Claude Code Max Compatible**: Works seamlessly with your Claude Code Max account
- **Context-aware**: Analyzes your git diff to understand what changes were made
- **Smart formatting**: Generates properly formatted conventional commit messages
- **Seamless integration**: Works directly with VS Code's built-in Git interface
- **No API keys required**: Uses your existing Claude CLI authentication

## Requirements

- VS Code 1.103.0 or higher
- Claude CLI installed and authenticated (via Claude Code Max or other methods)
- Git repository initialized in your workspace
- Internet connection for AI generation

## Installation

1. Install the extension from the VS Code Marketplace
2. Ensure Claude CLI is installed and available in your system PATH
3. Open a project with a Git repository
4. Look for the sparkle ✨ button in your Git panel

## How to Use

1. Make some changes to your code
2. Stage your changes in VS Code's Git panel (optional - works with unstaged changes too)
3. Click the sparkle ✨ button next to the commit message input
4. The extension will analyze your changes using Claude CLI and generate a commit message
5. Review and edit the generated message if needed
6. Commit your changes

## Extension Settings

This extension contributes the following settings:

* `claude-commit.claudePath`: Custom path to Claude CLI executable (optional - auto-detects by default)
* `claude-commit.debugMode`: Enable debug mode to show CLI commands being executed
* `claude-commit.customRules`: Custom rules for commit message generation (e.g., 'Always include ticket number', 'Use present tense')
* `claude-commit.additionalCliArgs`: Additional command-line arguments to pass to Claude CLI

## Configuration Examples

### Using a custom Claude path
```json
{
    "claude-commit.claudePath": "/usr/local/bin/claude"
}
```

### Custom commit rules
```json
{
    "claude-commit.customRules": [
        "Always include JIRA ticket number",
        "Use present tense",
        "Keep under 50 characters"
    ]
}
```

### Debug mode for troubleshooting
```json
{
    "claude-commit.debugMode": true
}
```

## Troubleshooting

### Claude CLI not found
If you see an error about Claude CLI not being found:

1. **Check Claude is installed**: Run this in your terminal:
   ```bash
   which claude
   ```
   This should show the path to Claude (e.g., `/Users/you/.nvm/versions/node/v22.13.0/bin/claude`)

2. **Set custom path in VS Code**:
   - Open VS Code Settings (Cmd+,)
   - Search for "claude-commit"
   - In "Claude Path", enter the full path from step 1
   - Example: `/Users/you/.nvm/versions/node/v22.13.0/bin/claude`

3. **Enable Debug Mode**:
   - In the same settings, enable "Debug Mode"
   - Open the Output panel (View → Output)
   - Select "Claude Commit" from the dropdown
   - Try generating a commit message and check the logs

4. **Common issues**:
   - **NVM users**: VS Code might not see your NVM paths. Use the custom path setting
   - **macOS**: If using zsh, paths might differ between terminal and VS Code
   - **Authentication**: Ensure Claude CLI is authenticated by running `claude setup-token` in terminal

### No commit message generated
1. Ensure you have changes in your repository (staged or unstaged)
2. Check that Claude CLI is properly authenticated
3. Enable debug mode to see the actual commands being executed

## Privacy & Security

- Your code changes are processed locally through Claude CLI
- No API keys are stored or transmitted by this extension
- Authentication is handled by your existing Claude CLI setup
- Code is only sent to Claude's servers through your authenticated CLI session

## Release Notes

### 1.0.0
- Complete refactor to use Claude CLI instead of Anthropic API
- Simplified configuration (removed model, maxTokens, commitFormat, customTemplate)
- Hardcoded to use Sonnet model and conventional commit format
- Improved debug logging that only runs when debug mode is enabled
- Removed all console.log statements for cleaner operation
- New name: Claude Commit (formerly Claude Code AI Commit Message Button)

## Contributing

Found a bug or have a feature request? Please open an issue on our [GitHub repository](https://github.com/juanlb/claude-commit).

## License

MIT License - see LICENSE file for details.

**Enjoy smarter commits with Claude Code Max! ✨**