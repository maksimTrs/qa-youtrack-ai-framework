# Claude Code Essentials - Most Useful Commands & Hotkeys



## Basic usage

**⚠️ Note:** `ccusage` is a separate third-party npm package (`npm install -g ccusage`) for analyzing Claude Code token usage from JSONL files - NOT a built-in Claude Code command.

| Third-Party Tool | Description |
|---------|-------------|
| `ccusage` | Show daily usage report (requires separate installation) |
| `ccusage daily` | Daily token usage and costs |
| `ccusage monthly` | Monthly aggregated report |
| `ccusage session` | Usage by conversation session |
| `ccusage blocks` | 5-hour billing windows |


## 🚨 Quick Reference Card

**Essential Flow:**
1. `npm install -g @anthropic-ai/claude-code` (one-time setup)
2. `claude` (start session)
3. `/init` (initialize project context)
4. `/terminal-setup` (better UX)
5. Start coding with Claude!


## 🎯 Pro Tips for Maximum Efficiency

1. **Always start with `/init`** - This single command makes Claude 10x more helpful
2. **Use `claude -c`** - Resume sessions instead of starting fresh each time  
3. **Learn the project understanding commands** - `> summarize` and `> explain folder structure` save massive time
4. **Monitor costs with `/cost`** - Stay aware of your token usage
5. **Set up your terminal with `/terminal-setup`** - Much better user experience
6. **Master the special prefixes** - `!`, `@`, `#` for rapid workflow
7. **Use Plan Mode for complex tasks (shift+tab)** - Let Claude break down big projects

## 🚀 Getting Started (Must-Know)

| Command | Description | Why It's Essential |
|---------|-------------|-------------------|
| `npm install -g @anthropic-ai/claude-code` | Install Claude Code globally | Required for initial setup |
| `claude` | Start new interactive session | Basic command to begin coding assistance |
| `claude --continue` or `claude -c` | Resume most recent session | Saves time, maintains context between sessions |
| `/init` | Create CLAUDE.md for project context | Dramatically improves Claude's understanding of your project |
| `/ide` | Connect Claude to your IDE from external terminals | Enables diff viewing, selection context, diagnostics in IDE |
| `/help` | List all available commands | Your in-session reference guide |
| `/release-notes` | View release notes | Stay updated with latest features and changes |
| `/approved-tools` | Manage tool permissions | Control which tools Claude can use without prompting |
| `/vim` | Enable vim bindings for text input | Familiar editing experience for vim users |
| `/bug` | Report bugs to Anthropic | Send conversation data to help improve Claude Code |
| `/model sonnet[1m]` | Add model with 1 million tokens | Access extended context for large codebases and complex tasks |
| `/statusline` | Modify status line of Claude chat | Customize chat interface (e.g., "/statusline show the model name in orange") |
| `/security-review` | Analyze codebase for security concerns | Identify potential security vulnerabilities and risks |

## 🔄 Update Management

| Command | Description | Use Case |
|---------|-------------|----------|
| `claude update` | Update Claude Code manually | Force update to latest version when needed |
| `claude --version` | Check current Claude Code version | Verify you're running the latest version |
| `claude doctor` | Check installation and version info | Diagnose installation issues and verify setup |
| `claude config set autoUpdates false --global` | Disable automatic updates | Control when updates happen |
| `export DISABLE_AUTOUPDATER=1` | Disable auto-updates via environment variable | System-wide auto-update control |
| `claude --mcp-debug` | Enable MCP debug mode | Get detailed information about MCP server errors |
| `claude --mcp-config <path>` | Run one-off MCP servers | Specify configuration file path for MCP servers |
| `claude --continue` or `claude --resume` | Resume previous conversations | Continue from where you left off |
| `claude -p --output-format=stream-json` | Stream JSON output in print mode | For programmatic consumption of Claude's output |


## 💪 Most Valuable Daily Commands

| Command | Description | Impact |
|---------|-------------|---------|
| `/review` | Review code for bugs and improvements | Speeds up code reviews, catches issues early |
| `> summarize this project` | Get high-level project overview | Saves hours when joining new projects |
| `> find the files that handle [feature]` | Locate specific functionality | Fast, accurate codebase navigation |
| `/cost` | Check token usage and costs | Helps manage AI budget effectively |
| `/terminal-setup` | Configure terminal for enhanced UX | Enables Shift+Enter for multiline + auto-accept |
| `/ide` | Connect Claude to your IDE from external terminals | Enables diff viewing, selection context, diagnostics in IDE |
| `/login` | Switch Anthropic accounts | Change between different Anthropic accounts |
| `/logout` | Sign out from your Anthropic account | Disconnect from current account |
| `/memory` | Edit CLAUDE.md memory files | Manage project memory and context files |
| `/permissions` | View or update permissions | Manage tool permissions and access controls |
| `/pr_comments` | View pull request comments | Access and review PR feedback |
| `/status` | View account and system statuses | Check account status and system health |
| `claude mcp list` | List all configured MCP servers | View connected databases, APIs, and tools |
| `claude mcp add` | Add new MCP server connections | Connect databases, GitHub, file systems, etc. |
| `claude mcp add-from-claude-desktop` | Import MCP servers from Claude Desktop | Quick setup for existing configurations |

### 🚀 Quick MCP Installation (Smithery)
For Claude Desktop users, there's an even easier way:
```bash
# Auto-install Context7 with one command
npx -y @smithery/cli install @upstash/context7-mcp --client claude

# Auto-install other servers 
npx -y @smithery/cli install @anaisbetts/mcp-installer --client claude
```

### 🔗 Popular MCP Server Examples

| Server | Installation Command | Use Case |
|--------|---------------------|----------|
| **Context7** | `claude mcp add context7 -- npx -y @upstash/context7-mcp@latest` | Up-to-date documentation for any library |
| **Playwright** | `claude mcp add playwright -- npx @playwright/mcp@latest` | Browser automation and testing |
| **PostgreSQL** | `claude mcp add postgres -- npx @modelcontextprotocol/server-postgres` | Database queries and schema analysis |
| **GitHub** | `claude mcp add github -- npx @modelcontextprotocol/server-github` | Repository management and PR reviews |
| **File System** | `claude mcp add filesystem -- npx @modelcontextprotocol/server-filesystem` | Advanced file operations |
| **Fetch** | `claude mcp add fetch -- uvx mcp-server-fetch` | Web content fetching and HTML-to-markdown conversion |

**📋 More Popular MCP Servers:**
- https://github.com/modelcontextprotocol/servers
- https://glama.ai/mcp/servers

**Example Context7 Usage:**
```bash
> Create a Next.js 14 project with app router. use context7
> Write a FastAPI CRUD API with authentication. use context7
> Show how to use TanStack Router in React. use context7
```

**Example Playwright Usage:**
```bash
> Take a screenshot of example.com
> Fill out this web form and submit it
> Test the login flow on our staging site
```

**Example Fetch Usage:**
```bash
> Fetch https://docs.python.org/3/library/requests.html and summarize the key concepts
> Get the content from https://example.com/api-docs and extract API endpoints
> Fetch this webpage and convert to markdown: https://github.com/anthropics/claude-code
```

## 🔧 **Claude Code MCP Management Commands**

| **Command** | **Description** | **Use Case** |
|-------------|----------------|--------------|
| **`claude mcp list` OR `/mcp` command in claude code** | List all configured MCP servers | See what servers are currently available |
| **`claude mcp get <server-name>`** | Get detailed info about specific server | Troubleshoot server configuration |
| **`claude mcp add <name> <command> [args...]`** | Add new MCP server with command | Install new server functionality |
| **`claude mcp add-json <name> '<json>'`** | Add server from JSON configuration | Advanced server setup with full config |
| **`claude mcp remove <server-name>`** | Remove MCP server | Uninstall unwanted server |
| **`claude mcp add-from-claude-desktop`** | Import servers from Claude Desktop | Quick setup from existing configuration |
| **`claude mcp serve`** | Start Claude Code as MCP server | Make Claude Code available to other MCP clients |

## 🤖 **Claude Code Sub-Agents (New)**

| **Command** | **Description** | **Use Case** |
|-------------|----------------|--------------|
| **`/agents`** | List and manage available sub-agents | View configured specialized agents |
| **`/agents create <name>`** | Create a new sub-agent with specific role | Set up domain-specific AI assistants |
| **Use sub-agents via prompts** | `> Use the code-reviewer agent to analyze this PR` | Delegate specialized tasks to focused agents |

### 🔧 **Sub-Agent Concepts**
- **Lightweight Claude instances** with specialized system prompts
- **Separate context** - won't pollute main Claude session  
- **Parallel execution** - multiple agents can work simultaneously
- **Domain expertise** - each agent optimized for specific tasks

### 💡 **Common Sub-Agent Use Cases**

| **Agent Type** | **Example Use** | **Command Pattern** |
|---------------|----------------|-------------------|
| **Code Reviewer** | `> Use code-analyzer sub-agent to find performance issues` | Specialized code analysis |
| **TDD Agent** | `> Use tdd-agent to verify implementation doesn't overfit tests` | Test-driven development |
| **Security Agent** | `> Use security-agent to audit authentication flow` | Security-focused reviews |
| **Documentation Agent** | `> Use docs-agent to update README with new features` | Documentation maintenance |

### ⚡ **Agents promt examples**
1. https://docs.anthropic.com/en/docs/claude-code/sub-agents
2. https://github.com/SuperClaude-Org/SuperClaude_Framework/blob/5436b1a76218e7cf94d13017d51db0c57a52491f/SuperClaude/Core/PERSONAS.md
3. https://github.com/bmadcode/BMAD-METHOD/blob/main/dist/agents/qa.txt
4. https://github.com/bmadcode/BMAD-METHOD/blob/a7038d43d18246f6aef175aa89ba059b7c94f61f/bmad-core/agents/qa.md
5. https://github.com/wshobson/agents/blob/main/test-automator.md
6. https://github.com/coleam00/context-engineering-intro/blob/main/claude-code-full-guide/CLAUDE.md

**Note**: Sub-agents preserve main context while providing specialized expertise through separate, focused instances.

## 🚨 **Security-Sensitive Commands & Flags**

| Command/Flag | Description | ⚠️ **Security Warning** | Use Case |
|-------------|-------------|------------------------|----------|
| **`claude --dangerously-skip-permissions`** | Skip all permission prompts | **🛑 EXTREME CAUTION** - Bypasses all safety checks and permission controls | Automated scripts, CI/CD pipelines where human approval isn't available |
| **Auto-Accept Mode** | `Shift + Tab` to enable | **⚠️ MONITORED USE** - Automatically accepts Claude's suggestions | Rapid development in controlled environments |

## 🔧 Productivity Boosters

| Command | Description | Benefit |
|---------|-------------|---------|
| `/compact` | Summarize conversation to reduce tokens | Enables longer sessions, saves costs |
| `/clear` | Reset session history | Fresh start while staying in same project |
| `claude --resume` or `claude -r` | Choose from past sessions | Switch between multiple projects easily |
| `/model` | Switch Claude models | Optimize for speed vs creativity as needed |
| `claude --dangerously-skip-permissions` | Skip all permission prompts | **⚠️ USE WITH CAUTION** - Bypasses safety checks |
| `claude --verbose` | Enable verbose logging | Show detailed output for debugging |
| `claude --max-turns <n>` | Limit agentic turns in non-interactive mode | Control task complexity in automation |

## ⚙️ Configuration Commands

| Command | Description | Use Case |
|---------|-------------|----------|
| `claude config list` | List all current settings | View current configuration |
| `claude config get <key>` | Retrieve value of specific setting | Check individual setting values |
| `claude config set <key> <value>` | Change value of a setting | Modify configuration options |
| `claude config add <key> <value>` | Add value to list setting | Add items to configuration lists |
| `claude config remove <key> <value>` | Remove value from list setting | Remove items from configuration lists |
| `claude config set --global <key> <value>` | Set global configuration | Apply settings across all projects |

## ⚡ Essential Hotkeys

| Hotkey | Action | Usage |
|--------|--------|-------|
| **Up/Down Arrows** | Navigate command history | Quick access to previous prompts |
| **Option + Enter** | New line (multiline input) | Default multiline on macOS |
| **Shift + Enter** | New line (after `/terminal-setup`) | Better multiline input after terminal setup |
| **\ + Enter** | Force newline | Universal multiline method that works in all terminals |
| **Escape** | Stop Claude's current action | Interrupt long-running tasks |
| **Esc + Esc** | Edit previous message | Double-escape to modify last input |
| **/ (start of line)** | Initiate slash command | Access all Claude commands |
| **# (start of line)** | Quick memory addition | Add context to CLAUDE.md file |
| **Ctrl + C** | Cancel input/generation | Standard interrupt |
| **Ctrl + D** | Exit Claude session | Clean exit |
| **Ctrl + L** | Clear terminal screen | Clean view while keeping history |

### 🚀 Special Command Prefixes

| Prefix | Purpose | Example | Usage |
|--------|---------|---------|-------|
| **! (bash mode)** | Execute bash commands directly | `!ls -la` | Run terminal commands without leaving Claude |
| **/ (slash commands)** | Built-in Claude commands | `/review`, `/cost`, `/help` | Access Claude's internal functions |
| **@ (file paths)** | Quick file references | `@src/main.py` | Reference files in conversation |
| **# (memorize)** | Add to project memory | `# Use TypeScript strict mode` | Store important project notes |

### ⌨️ Advanced Input Controls

| Shortcut | Action | When to Use |
|----------|--------|-------------|
| **Double ESC** | Clear current input | Cancel long prompts |
| **Shift + Tab** | Auto-accept edits | Quick approval of Claude's suggestions |
| **Ctrl + _** | Undo last action | Revert mistakes |
| **Ctrl + R** | Verbose output | Get detailed explanations |
| **Ctrl + Z** | Suspend Claude | Pause for system tasks |
| **\ + Enter** | Force newline | Multiline input (universal method) |

### 🎮 Advanced Modes & Automation

| Mode | Command | Description | When to Use |
|------|---------|-------------|-------------|
| **Auto-Accept** | `Shift + Tab` during edits | Automatically accept suggested changes OR use PLAN mode | Rapid development cycles |
| **Batch Mode** | `claude -p "prompt"` | Headless execution for scripts | CI/CD and automation |



---

## 🔥 Advanced Techniques (Power Users)

### 🧠 "Think Mode" for Complex Problems

| Technique | Example | Benefit |
|-----------|---------|---------|
| **Prepend with "I need to think through..."** | `> I need to think through building a secure authentication system with JWT vs sessions, rate limiting...` | Triggers extended reasoning mode, gets strategies not just code |
| **"think about" for follow-up analysis** | `> think about potential security vulnerabilities in this approach` | Prompts deeper analysis on specific aspects |
| **"think harder" for deeper edge cases** | `> think harder about edge cases we should handle` | Forces more thorough consideration of complex scenarios |
| **"ultrathink" for architectural planning** | `> ultrathink how to architect a scalable chat application` | Deep, structured, multi-step architectural thinking |


### 🔧 Advanced Configuration & Integration

| Command/File | Description | Power Use |
|--------------|-------------|-----------|
| **`.mcp.json`** | Configure Model Context Protocol servers | Connect databases, CI/CD, external APIs directly in prompts |
| **`npx ccusage@latest`** | Track token usage across ALL sessions | Monitor costs and optimize prompts across projects |
| **`claude --help`** | Show all available command options | Learn about advanced CLI flags and options |
| **`claude --version`** | Check Claude Code version | Verify you're running the latest version |

### 📁 Strategic CLAUDE.md Placement
Place `CLAUDE.md` files in multiple locations for maximum context:
- Repository root (project-specific)
- Parent directories (team standards)
- Home folder (`~/.claude/CLAUDE.md`) for personal preferences

### 🎯 Advanced Prompting Framework
Structure complex requests for architect-level responses:
```
Context: [Your system architecture]
Constraints: [Technical limitations]  
Goal: [Measurable outcome]
Format: [Response structure]
Examples: [Good/bad solutions]
Validation: [Verification methods]
Now solve: [Specific problem]
```

### 🔄 Multi-Claude Workflows
**Separation of Concerns:**
1. **Claude 1:** Write code
2. **Claude 2:** Review code (use `/clear` or new terminal)
3. **Claude 3:** Refactor based on feedback

**Parallel Development with Git Worktrees:**
```bash
git worktree add ../project-feature-a feature-a
cd ../project-feature-a && claude
```

### 🤖 Automation & CI Integration

| Command | Use Case | Example |
|---------|----------|---------|
| **`claude -p "prompt"`** | Headless mode for scripts/CI | Automated code reviews, issue triage |
| **`claude -p "prompt" > output.txt`** | Redirect output to file | CI/CD pipeline file organization |
| **GitHub CLI integration** | Natural language Git workflows | `> Create feature branch, implement OAuth, open PR tagging security team` |

### 🏗️ Professional Workflows

**1. Explore → Plan → Code → Commit Pattern:**
```
> Read these files and analyze the current auth system
> I need to think through adding 2FA support
> Implement the 2FA system with these requirements
> Commit this with proper commit message and create PR
```

**2. Defensive Coding with TDD:**
```
> Using TDD, write tests for payment processing handling network failures, invalid cards, rate limiting
> Now implement the resilient payment function with circuit breakers and logging
```

**3. Large-Scale Refactoring:**
```
> Extract all authentication logic into a service, update imports across codebase, add TypeScript interfaces
```

### 💡 Pro Power-User Tips

1. **Keep `/clear` handy** - Reset context frequently to stay focused
2. **Use checklists for complex tasks** - Have Claude maintain a Markdown checklist
3. **Be hyper-specific** - Detailed instructions dramatically improve first-attempt success
4. **Master data input methods:**
   - Direct copy/paste
   - File references: `@file.txt` or `> read this file and analyze...`
   - Natural language: `> analyze the code in src/main.py`
5. **Create custom workflows** - Design team-specific prompts and share across projects

### 🎨 Advanced Use Cases

| Scenario | Approach | Command Example |
|----------|----------|-----------------|
| **Cross-language migration** | Preserve logic, optimize for platform | `> Migrate this Node.js auth to Go with goroutines, preserve API contracts` |
| **Architecture planning** | Upfront system design | `> Architect a social platform for millions: auth, messaging, storage, CDN, monitoring` |
| **Living documentation** | Context-aware docs with diagrams | `> Document our auth system with architectural decisions, security considerations, sequence diagrams` |
| **Code archaeology** | Find scattered logic patterns | `> Analyze entire codebase for auth logic, map relationships, flag vulnerabilities` |

---

## ⚠️ **Important Disclaimer**

**Always verify commands with your installation:**
- Run `claude --help` for complete CLI options
- Use `/help` in interactive mode for current session commands  
- Features may vary between Claude Code versions
- Some examples may be version-specific or require additional setup
- Third-party tools (like `ccusage`) require separate installation

**This guide combines:**
- ✅ Official Anthropic documentation
- ⚠️ Context7 community documentation 
- ⚠️ User-contributed examples