# Autonomous Developer MCP Server

An advanced Model Context Protocol (MCP) server for Claude Desktop that enables AI-assisted software development with powerful code editing and project management capabilities.

## What is this?

This is an MCP server designed to be used with Claude Desktop, allowing Claude to autonomously edit and manage code in your projects. It provides a suite of tools for Claude to modify files, analyze code structure, run shell commands, and perform Git operations.

## Setup Guide for Claude Desktop

### Prerequisites

- Node.js ≥ 18.0.0
- Claude Desktop application
- Git (for version control features)

### Installation Steps

1. **Download the server files**
   - Download or clone this repository to your local machine
   - Note the full path where you saved the server.js file

2. **Configure your project directory**
   - Open the `package.json` file
   - Edit the `projectDirectory` field to point to the project you want Claude to work on:
     ```json
     "projectDirectory": "C:\\Users\\username\\path\\to\\your\\project"
     ```
   - Make sure to use double backslashes (`\\`) for Windows paths

3. **Install dependencies**
   - Open a terminal in the server directory
   - Run `npm install` to install all required dependencies

4. **Configure Claude Desktop's config.json**
   - Locate your Claude Desktop config file at:  
     `C:\Users\[username]\AppData\Roaming\Claude\claude_desktop_config.json`
   - Add the "autonomous-developer-mcp" to the "mcpServers" section:
     ```json
     "mcpServers": {
       "autonomous-developer-mcp": {
         "command": "C:\\Program Files\\nodejs\\node.exe",
         "args": [
           "C:\\Users\\[username]\\path\\to\\server.js"
         ],
         "env": {}
       }
     }
     ```
   - Replace `[username]` with your Windows username
   - Replace the path to server.js with the actual path where you saved the file
   - If you have other MCP servers already configured (like "graphx"), keep them and just add this new one

5. **Restart Claude Desktop**
   - Restart the application to apply the changes

## Using with Claude

Once configured, you can ask Claude to help with coding tasks in your project. For example:

- "Can you help me fix a bug in my project?"
- "Create a new React component for my user dashboard"
- "Refactor the authentication module to use JWT"

Claude will use the MCP server to:
- Browse your project files
- Make code changes with high reliability
- Execute commands to test changes
- Commit working changes to Git

## Available Tools

The server provides Claude with the following capabilities:
- Intelligent code editing with 99% success rate
- File creation and management
- Code search and structure analysis
- Git operations (commit, status, branch)
- Shell command execution
- Task planning

## Security Note

All operations are sandboxed to your specified project directory for safety. The server cannot access files outside this directory.
