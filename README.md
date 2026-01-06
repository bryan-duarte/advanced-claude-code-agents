# Advance Dev Agents

A comprehensive Claude Code plugin for advanced agentic development, featuring specialized commands, subagents, and skills.

## Included Components

### Slash Commands
- `/advance-dev-agents:review`: Deep code and architectural review.
- `/advance-dev-agents:refactor`: Propose and execute code refactoring.
- `/advance-dev-agents:status`: Get an agentic health check of the project.

### Subagents
- **Architect**: System design and patterns.
- **Security**: Vulnerability and security audit.
- **Performance**: Optimization and profiling.
- **Testing**: Test generation and QA.
- **Docs**: Documentation and technical writing.
- **Compliance**: Standards and license auditing.

### Skills
- **Research Skill**: Powered by `context7` for real-time documentation retrieval.

## Installation

1. Add the marketplace:
   ```bash
   /plugin marketplace add https://github.com/YOUR_USERNAME/YOUR_REPO
   ```

2. Install the plugin:
   ```bash
   /plugin install advance-dev-agents@advance-dev-agents-marketplace
   ```

## Dependencies
- This plugin automatically configures the `context7` MCP server using `npx @context7/mcp-server`.
