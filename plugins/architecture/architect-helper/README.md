# architect-helper

An architecture planning agent for GitHub Copilot in VS Code.

## Included Copilot components

- `com.github.copilot/agents/architect-helper.agent.md` defines the agent shown in the Copilot agent picker.
- `com.github.copilot/commands/architect-helper.md` defines the `/architect-helper` chat command.
- `plugin.json` is the Agent Plugins 1.0 manifest.

The agent reads and searches the current workspace, then returns an implementation-ready architecture plan. When invoked with `/architect-helper`, it can also use command execution to open this source repository in the current VS Code window. It does not edit files. It is an instruction-based Copilot agent; this repository does not contain a separate model, service, API, or MCP server.

The `assets/`, `configs/`, `demands/`, `prompts/`, `scripts/`, `skills/`, and `templates/` directories are retained from the original placeholder. They are not currently consumed by the agent.

## Install in VS Code

Open this repository in VS Code and use **Chat: Open Customizations** > **Browse** to find the `Agent-Plugin` marketplace and install `architect-helper`. The repository recommends this marketplace in `.github/copilot/settings.json`.

You can also open the [VS Code install link](vscode://chat-plugin/install?source=SumitMahale%2FAgent-Plugin&plugin=architect-helper) and confirm the installation.

## Open the source in Explorer

Run `/architect-helper` in Copilot Chat and press Enter. The agent checks for Git and the VS Code `code` command, then checks whether the current workspace is already this repository. Otherwise, it uses `source/Agent-Plugin` under your home directory, creating the parent directory and cloning `https://github.com/SumitMahale/Agent-Plugin.git` there if needed. It verifies an existing destination before using it and opens the repository with `code --reuse-window` in the current window. Approve command requests when prompted.

If Git or `code` is unavailable, the repository check fails, or a clone/open command fails, the agent stops and reports the issue. Installing a remote plugin by itself stores an installed copy in VS Code's plugin storage; VS Code does not add that cache folder to Explorer. The complete maintained plugin source is in `plugins/architecture/architect-helper/`.

## Use the agent

In Copilot Chat, select **Architect Helper** from the agent picker to invoke it manually, or run `/architect-helper` to prepare the source repository and get the architecture-planning prompt. The agent is configured for user invocation and is not intended to be selected automatically.

The agent can execute only the repository checks, clone, and open steps instructed by the slash command; it does not generate or edit code. Integration with an independently hosted agent and any project-specific architecture rules are not included.
