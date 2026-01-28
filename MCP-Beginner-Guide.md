# Claude Code & MCP Setup Guide

## What is Claude Code?

Claude Code is a command-line tool that lets you work with Claude directly in your terminal. It can read, write, and edit files in your projects.

### Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Then authenticate:
```bash
claude login
```

---

## What are MCPs?

**MCP (Model Context Protocol)** servers are plugins that give Claude extra capabilities—like accessing databases, scraping websites, or deploying apps.

**Why use them?**
- Connect Claude to external services (Supabase, Netlify, etc.)
- Give Claude specialized tools for your workflow
- Automate tasks that require API access

---

## MCP Scopes

| Scope | Location | Use Case |
|-------|----------|----------|
| `user` | `~/.claude.json` | Available in ALL projects |
| `project` | `.mcp.json` in repo root | Shared with team via git |
| `local` | `.claude/` folder | Only for you, in one project |

---

## Recommended MCPs

### Always Useful (Install at User Level)

**1. Sequential Thinking** — Complex reasoning tasks
```bash
claude mcp add sequential-thinking --scope user -- npx -y @modelcontextprotocol/server-sequential-thinking
```

**2. Context7** — Up-to-date library documentation
```bash
claude mcp add context7 --scope user -- npx -y @upstash/context7-mcp@latest
```

### Project-Specific (Install Per Project)

| MCP | Purpose | Tokens |
|-----|---------|--------|
| `supabase-mcp-server` | Database operations | 18k |
| `netlify` | Deploy sites | 8k |
| `mcp-playwright` | Browser automation | 20k |
| `mcp-server-firecrawl` | Web scraping | 10k |

---

## Setting Up Project MCPs

### Step 1: Create `.mcp.json`

Create a file named `.mcp.json` in your **project root** (same folder as `.git`):

```
my-project/
├── .git/
├── .mcp.json      ← Create this file
├── .env           ← Your API keys go here
├── src/
└── package.json
```

### Step 2: Add Your MCPs

**Basic template:**
```json
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp@latest"]
    }
  }
}
```

**With Supabase:**
```json
{
  "mcpServers": {
    "supabase-mcp-server": {
      "command": "npx",
      "args": ["-y", "supabase-mcp-server"],
      "env": {
        "SUPABASE_URL": "${SUPABASE_URL}",
        "SUPABASE_SERVICE_ROLE_KEY": "${SUPABASE_SERVICE_ROLE_KEY}"
      }
    }
  }
}
```

**With Netlify:**
```json
{
  "mcpServers": {
    "netlify": {
      "command": "npx",
      "args": ["-y", "@netlify/mcp-server"],
      "env": {
        "NETLIFY_AUTH_TOKEN": "${NETLIFY_AUTH_TOKEN}"
      }
    }
  }
}
```

### Step 3: Create `.env` File

Store your API keys in `.env` (same folder as `.mcp.json`):

```env
# Supabase
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_ROLE_KEY=eyJhbGci...

# Netlify
NETLIFY_AUTH_TOKEN=your_token

# Firecrawl
FIRECRAWL_API_KEY=your_key
```

> ⚠️ Add `.env` to your `.gitignore`!

### Step 4: Restart Claude Code

MCPs load when Claude Code starts. After creating `.mcp.json`, restart:
```bash
claude
```

---

## Quick Commands

```bash
# List all MCPs
claude mcp list

# Add an MCP
claude mcp add <name> --scope <user|project> -- <command>

# Remove an MCP
claude mcp remove <name> --scope <user|project>

# Check MCP details
claude mcp get <name>
```

**Inside Claude Code:**
```
/mcp        # Check MCP status
/context    # See token usage
```

---

## Full MCP Examples

### Web Scraping Project
```json
{
  "mcpServers": {
    "mcp-server-firecrawl": {
      "command": "npx",
      "args": ["-y", "firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "${FIRECRAWL_API_KEY}"
      }
    }
  }
}
```

### Browser Testing Project
```json
{
  "mcpServers": {
    "mcp-playwright": {
      "command": "npx",
      "args": ["-y", "@anthropic/mcp-playwright"]
    }
  }
}
```

### Full-Stack Project (Supabase + Netlify)
```json
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp@latest"]
    },
    "supabase-mcp-server": {
      "command": "npx",
      "args": ["-y", "supabase-mcp-server"],
      "env": {
        "SUPABASE_URL": "${SUPABASE_URL}",
        "SUPABASE_SERVICE_ROLE_KEY": "${SUPABASE_SERVICE_ROLE_KEY}"
      }
    },
    "netlify": {
      "command": "npx",
      "args": ["-y", "@netlify/mcp-server"],
      "env": {
        "NETLIFY_AUTH_TOKEN": "${NETLIFY_AUTH_TOKEN}"
      }
    }
  }
}
```

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| MCP not loading | Restart Claude Code after adding `.mcp.json` |
| Env vars not working | Check `.env` is in project root |
| `.mcp.json` not found | Must be in repo root (same level as `.git`) |
| Invalid JSON error | Check for trailing commas |

---

## Token Cost Reference

| MCP | Tokens | Install At |
|-----|--------|------------|
| sequential-thinking | 1.6k | user |
| context7 | 2.0k | user |
| supabase-mcp-server | 18k | project |
| netlify | 8k | project |
| mcp-playwright | 20k | project |
| mcp-server-firecrawl | 10k | project |

> 💡 Keep user-level MCPs minimal (~3.6k tokens). Add heavy MCPs only to projects that need them.
