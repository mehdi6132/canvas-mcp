# Canvas MCP

MCP server for Claude Desktop that connects to the Canvas LMS API. Ask Claude about your courses, deadlines, grades, and feedback directly from your chat interface.

## How it works

Canvas MCP exposes 29 tools across six categories: courses, deadlines, grades, content, communication, and planning. Once connected, you can ask Claude things like "what assignments are due this week" or "how am I doing in my algorithms course" and get answers pulled directly from Canvas.

Deadlines are classified into four urgency levels: critical, urgent, attention, and okay. You can export your schedule as an `.ics` file compatible with Google Calendar, Apple Calendar, and Outlook. Twelve pre-built prompts cover the most common study workflows, including a morning briefing and a catch-up plan.

Currently configured for Fontys. Other institutions can be added via the `CANVAS_BASE_URL` environment variable.

## Setup

**Option 1: one-click install**

Download `canvas-mcp-1.1.0.dxt` from [releases](https://github.com/mehdi6132/canvas-mcp/releases) and open it in Claude Desktop.

**Option 2: manual**

```bash
git clone https://github.com/mehdi6132/canvas-mcp
cd canvas-mcp
npm install
```

Add to your Claude Desktop config:

```json
{
  "mcpServers": {
    "canvas": {
      "command": "node",
      "args": ["path/to/canvas-mcp/index.js"],
      "env": {
        "CANVAS_API_TOKEN": "your-token-here",
        "CANVAS_BASE_URL": "https://canvas.fontys.nl"
      }
    }
  }
}
```

Get your Canvas API token at Account > Settings > New Access Token.
