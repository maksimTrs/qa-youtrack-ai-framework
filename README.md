# AI Automation Testing Project

An intelligent testing and workflow automation project integrating Claude Code with YouTrack, Figma, and Playwright for comprehensive QA automation.

## 🚀 Quick Setup

### Prerequisites

**Install Required Tools:**

```bash
# Install uv (for uvx command)
# Follow official installation guide: https://docs.astral.sh/uv/getting-started/installation/

# Install Node.js (for npx command)
# Download from: https://nodejs.org/

# Install Docker Desktop
# Download from: https://www.docker.com/products/docker-desktop/
```

**Install Claude Code:**

```bash
npm install -g @anthropic-ai/claude-code
```

### Project Setup

1. **Clone and configure:**

   ```bash
   git clone <repository-url>
   cd <project-name>

   # Copy MCP configuration template
   cp .mcp_example.json .mcp.json
   ```

2. **Configure authentication tokens:**

   **YouTrack API Token:**

   - Visit: https://www.jetbrains.com/help/youtrack/server/manage-authentication-tokens.html
   - Generate a permanent token with required permissions
   - Update `.mcp.json`: Replace `YOUTRACK_API_TOKEN=perm-XXX` with your token

   **Figma Dev Mode MCP:**

   - Follow setup guide: https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Dev-Mode-MCP-Server#h_01JZ8NN55YWF0HT5VBVYXF8WK9
   - Start the Figma MCP server on `http://127.0.0.1:3845/mcp`

3. **Start Claude Code:**

   ```bash
   claude

   # Activate extended context model (1 million tokens) for complex QA workflows
   /model sonnet[1m]
   ```

## 🔧 MCP Server Configuration

The project uses these MCP servers for enhanced functionality:

| Server             | Purpose              | Dependencies      |
| ------------------ | -------------------- | ----------------- |
| **fetch**          | Web content fetching | `uvx`             |
| **playwright**     | Browser automation   | `npx`, Docker     |
| **context7**       | Documentation access | `npx`             |
| **YouTrack**       | Issue management     | Docker, API token |
| **Figma Dev Mode** | Design integration   | Local server      |

**Reference:** [YouTrack MCP Server](https://github.com/tonyzorin/youtrack-mcp)

## 📂 Project Structure

```
├── .claude/
│   └── settings.json          # Shared team settings
├── QA/XXX-123/             # Test scenarios and assets for the QA XXX-123 task
├── .mcp_example.json         # MCP config template
├── CLAUDE.md                 # Project context and instructions for Claude Code
├── CLAUDE_CODE_WORKFLOW.md   # Detailed Claude Code usage guide
├── MCP_YouTrack_AI_Prompt.md  # Master prompt for the task
├── MCP_YouTrack_AI_Prompt_Smoke.md # Master smoke prompt for the task
└── prompts/                  # Task-specific prompt templates
    ├── YouTrack_XXX-123_Init.md        # Init prompt to generate test artifacts using YouTrack MCP
    ├── Figma_XXX-123_Support.md        # Figma MCP frameworks/mockups (optional)
    └── Playwright_XXX-123_UI_Tests.md  # Playwright MCP UI flow via Chrome browser (optional)
```

## 🛠️ Usage

### 📋 Workflow: Using Project Prompts

**Step 1: Initialize Task Analysis**

1. Start Claude Code session: `claude`
2. Use `prompts/YouTrack_XXX-123_Init.md` prompt to initiate master prompt execution from `MCP_YouTrack_AI_Prompt.md`
   - **Note:** For smoke testing, reference `MCP_YouTrack_AI_Prompt_Smoke.md` instead inside `YouTrack_XXX-123_Init.md`
3. The prompt will execute YouTrack MCP task logic + code reading from patch files
4. **Output:** Creates QA test artifacts in `QA/{TASK-ID}/{TASK-ID}-test-scenarios.md`

**Step 2: Enhanced Analysis (Optional)**

- **Figma Integration:** Add `prompts/Figma_XXX-123_Support.md` prompt to read Figma frames via Figma MCP and update test scenarios with significant UI cases
- **Browser Testing:** Add `prompts/Playwright_XXX-123_UI_Tests.md` prompt to show Claude Code full context of working UI realization via browser and update test scenarios with significant findings

### ⚡ Claude Code Commands

**For detailed Claude Code commands and workflows:**

- See [CLAUDE_CODE_WORKFLOW.md](CLAUDE_CODE_WORKFLOW.md)

**Common commands:**

```bash
# Start Claude Code session
claude

# Resume previous session
claude --continue

# Activate extended context model (1 million tokens) - essential for complex QA workflows
/model sonnet[1m]

# Access MCP servers
/mcp
```

## 🔒 Security Notes

- **`.mcp.json`** - Contains API tokens, excluded from git
- **Authentication tokens** - Store securely, never commit to repository
- Use **`.mcp_example.json`** as template for team setup

## 🐳 Docker Integration

YouTrack MCP server runs in Docker container as configured in your `.mcp.json` file (copied from `.mcp_example.json`). Ensure Docker Desktop is running before starting Claude Code.

## 🤝 Team Collaboration

- **Shared settings:** `.claude/settings.json` (committed to git)
- **MCP template:** Use `.mcp_example.json` to setup your `.mcp.json`
- **Documentation:** All team workflows documented in existing .md files

---

**Quick Start:** `claude` → Start automating! 🚀
