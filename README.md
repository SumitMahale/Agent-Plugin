# Agent-Plugin

This repository contains the `architect-helper` GitHub Copilot plugin at [`plugins/architecture/architect-helper`](plugins/architecture/architect-helper/README.md).

## Install in VS Code

1. Open this repository as a VS Code workspace. Its source will be visible in the Explorer, and the repository marketplace is configured for Copilot.
2. Open **Chat: Open Customizations** and browse the `Agent-Plugin` marketplace, or use the [VS Code install link](vscode://chat-plugin/install?source=SumitMahale%2FAgent-Plugin&plugin=architect-helper).
3. Install `architect-helper` and confirm the prompt.
4. In Copilot Chat, select **Architect Helper** from the agent picker and invoke it when needed. It is not intended to run automatically.

Installing a plugin from a remote source alone keeps its installed copy in VS Code plugin storage rather than the Explorer. Open this repository as the workspace to browse the maintained source without separately downloading or copying the plugin files.

The current agent is a prompt-defined architecture planner. It inspects workspace code and returns a plan; it does not edit files, run commands, or connect to a separate hosted agent service.
