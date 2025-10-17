```
# Global Instructions
- **Read**:
Read and obey the instructions in the file at ./commands/format/check.toml
## Documentation Style Guide
Follow the below rules.
## General Rules
- When writing project documentation, avoid first-person and third-person perspectives.
- All new documentation must include a section for "References" at the end, linking to relevant resources.
- Use clear and descriptive headings, with `H1` for the main topic and `H2` for subsections.

## Markdown Formatting
- Use triple backticks (```) for all code blocks, specifying the language for syntax highlighting.
- Use Markdown admonitions for important callouts:
  - `!!! note` for general information.
  - `!!! tip` for helpful advice.
  - `!!! warning` for critical warnings.

- **About Gemini CLI**:The Gemini Command Line Interface (CLI) supports extensions that enhance its capabilities and allow for customization. These extensions can package custom slash commands, Model Context Protocol (MCP) servers, scripts, and even custom GEMINI.md files into self-contained units for easy installation and use.
Key aspects of Gemini CLI extensions:
- **Custom Commands**:
Extensions can provide new commands by placing .toml files in a commands/ subdirectory within the extension's directory. These commands can be invoked using standard naming conventions (e.g., /extension_name:command_name).
- **MCP Servers**:
Extensions can integrate and configure external MCP servers, which extend the Gemini CLI's tool capabilities by providing access to additional functionalities.
Context Files (GEMINI.md):
Extensions can include GEMINI.md files to provide specific instructions and context to the Gemini model, tailoring its behavior for particular projects or tasks.
- **Configuration**:
Extensions are configured through a gemini-extension.json file, which defines properties like the context file name, excluded tools, and security policies for tool execution.
- **Installation**:
Users or the AI itself sing the Shell Tool and workaround syntax in the same way the AI can use ```cat <EOF``` and other syntax, and in this way the AI can install extensions with a singl, or multiple line, or prescripted command, similar to how extensions are installed in environments like VS Code. The AI or the User can also choose if fitting to create and install to a virtual environment (venv) for projects whic may be more advisable to create in virtual environments to protect global system installs and avppid library conflicts.
-  **Hierarchical Loading**:
The Gemini CLI loads GEMINI.md files hierarchically, merging context from global, project, and sub-directory levels, with more specific files overriding general ones.
- **Integration with Gemini Code Assist**:
A subset of Gemini CLI functionality, including extensions, is available directly within the Gemini Code Assist chat in VS Code, enabling agent mode capabilities within the IDE.
Gemini can and should suggest and assist with iinstalling VS Code and integrating Gemini CLIhe AI should also be actively suggestive with code improvements or alternative approaches to successfully achieveing any goals within a project development trajectory until the project is successfully completed to the user's satisfaction.
# Extensions

- **Context Files**:
Context files in Gemini CLI are used to provide the AI model with relevant information about your project, instructions, and preferences, allowing for more accurate and tailored responses.
How context files are handled:
- **GEMINI.md files**:
These Markdown files are a primary way to define context. They can be placed at various levels (e.g., global in ~/.gemini/ or project-specific in .gemini/) and define high-level strategy, persona, and mission-specific context. More specific GEMINI.md files override or supplement more general ones.
- **File and directory inclusion**:
You can explicitly include files and even entire directories as context using the @ symbol in your prompts (e.g., @filename.js or @src/). Gemini CLI is git-aware and will automatically exclude files listed in .gitignore.
--include-all-files flag:
When starting a session, this flag recursively includes the content of all text-based files in the current directory (respecting .gitignore) as initial context for the model.
- **Tool outputs**:
Outputs from shell commands executed using ! are also appended to the context.
**Model Context Protocol (MCP) servers**:
These servers can be configured to provide custom tools and data sources that Gemini CLI can leverage for context, allowing for integration with external systems or specific data sets.
- **Purpose of context files**:
Provide instructions and preferences:
Define how you want the AI to behave, its persona, and specific guidelines for generating responses.
Share project information:
Give the AI an understanding of your project structure, key files, and relevant code snippets.-
- **Improve response quality**:
By providing relevant context, you help the AI generate more accurate, consistent, and project-aligned output.
Manage token usage:
While context adds to token usage, well-managed context can lead to more efficient interactions by reducing the need for repeated information in prompts.
# Key Features
- **Among other things, the  AI can Perform**:
Code Understanding & Generation
Query and edit large codebases
Generate new apps from PDFs, images, or sketches using multimodal capabilities
Debug issues and troubleshoot with natural language
Automation & Integration
Automate operational tasks like querying pull requests or handling complex rebases
Use MCP servers to connect new capabilities, including media generation with Imagen, Veo or Lyria
Run non-interactively in scripts for workflow automation
Advanced Capabilities
Ground queries with built-in Google Search for real-time information
Perform conversation checkpointing to save and resume complex sessions
Create, read and write custom context files (GEMINI.md) to tailor behavior for your projects
- **Perform GitHub Integration**:
Integrate Gemini CLI directly into your GitHub workflows with Gemini CLI GitHub Action:

- **Pull Request Reviews*: Automated code review with contextual feedback and suggestions
**Issue Triage**: Perform automated labeling and prioritization of GitHub issues based on content analysis
On-demand Assistance: Mention @gemini-cli in issues and pull requests for help with debugging, explanations, or task delegation

```
