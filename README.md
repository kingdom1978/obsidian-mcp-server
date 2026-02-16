# Obsidian MCP Server

This plugin exposes your Obsidian vault as a Model Context Protocol (MCP) server, allowing AI assistants (like Claude, Gemini, etc.) to interact directly with your notes.

## Features

-   **Read Vault**: Access all files and their content.
-   **Search**: Find files by name.
-   **Full File Management**: Create, Read, Update, Delete files in your vault.
-   **Active Context**: Get the content of the currently active file in Obsidian.
-   **Append**: Append text to existing notes.
-   **Structure**: List folders and file hierarchy.

## Installation

1.  **Build the Plugin**:
    ```bash
    npm install
    npm run build
    ```
2.  **Copy to Obsidian**:
    -   Create a folder `obsidian-mcp-server` in your vault's `.obsidian/plugins/` directory.
    -   Copy `main.js`, `manifest.json`, and `styles.css` (if exists) into that folder.
3.  **Enable**:
    -   Open Obsidian Settings > Community Plugins.
    -   Reload plugins and toggle **Local MCP** on.

## Usage

The server runs on port `3123` by default.

### Connect from MCP Client

Configure your MCP client (e.g., Claude Desktop config) to connect via SSE:

```json
{
  "mcpServers": {
    "obsidian": {
      "url": "http://127.0.0.1:3123/sse"
    }
  }
}
```

### Available Tools

-   `search-files`: Search for files by name.
-   `create-file`: Create a new note.
-   `write-file`: Overwrite a note.
-   `append-content`: Add text to a note.
-   `delete-file`: Remove a note.
-   `list-folders`: List directories.

### Available Resources

-   `vault://files`: List all files.
-   `vault://active`: Get the current active file content.
-   `vault://{path}`: Read a specific file.

## Development

-   `npm run dev`: Build in watch mode.
