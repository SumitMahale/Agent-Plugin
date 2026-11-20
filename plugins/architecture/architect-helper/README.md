# architect-helper

An architecture planning agent for GitHub Copilot in VS Code.

## Included Copilot components

- `com.github.copilot/agents/architect-helper.agent.md` defines the agent shown in the Copilot agent picker.
- `com.github.copilot/commands/architect-helper.md` defines the `/architect-helper` chat command.
- `plugin.json` is the Agent Plugins 1.0 manifest.

The agent reads and searches the current workspace, then returns an implementation-ready architecture plan. It does not edit files or run commands. It is an instruction-based Copilot agent; this repository does not contain a separate model, service, API, or MCP server.

The `assets/`, `configs/`, `demands/`, `prompts/`, `scripts/`, `skills/`, and `templates/` directories are retained from the original placeholder. They are not currently consumed by the agent.

## Install in VS Code

Open this repository in VS Code and use **Chat: Open Customizations** > **Browse** to find the `Agent-Plugin` marketplace and install `architect-helper`. The repository recommends this marketplace in `.github/copilot/settings.json`.

You can also open the [VS Code install link](vscode://chat-plugin/install?source=SumitMahale%2FAgent-Plugin&plugin=architect-helper) and confirm the installation.

## Make the source visible in Explorer

Open or clone this GitHub repository as the VS Code workspace. The complete plugin source is in `plugins/architecture/architect-helper/` and is visible in the Explorer. There is no separate source package to download or copy.

Installing a remote plugin by itself stores an installed copy in VS Code's plugin storage; VS Code does not add that cache folder to Explorer. Opening this repository as the workspace is what makes the maintained source visible.

## Use the agent

In Copilot Chat, select **Architect Helper** from the agent picker to invoke it manually. You can then run `/architect-helper` for the architecture-planning prompt. The agent is configured for user invocation and is not intended to be selected automatically.

The initial implementation provides architecture discovery and planning only. Code generation, edits, command execution, integration with an independently hosted agent, and any project-specific architecture rules still need to be implemented if desired.
