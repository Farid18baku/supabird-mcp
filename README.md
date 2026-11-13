# SupaBird MCP Server

<img src="assets/supabird-icon-512.png" width="96" alt="SupaBird logo" />

The official remote MCP server for [SupaBird](https://supabird.io), your social media growth agent. Bring your SupaBird account into Claude, Cursor, VS Code, Gemini CLI or any MCP client: find viral content, write in your voice, and schedule posts across all major social media platforms.

- **Endpoint:** `https://api.supabird.io/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 — your client opens a SupaBird sign-in page the first time it connects. No API key to copy.
- **Requires:** a SupaBird account ([start a free trial](https://x.supabird.io/auth)). MCP usage is paid from your SupaBird credit wallet.

## What it can do

19 tools, grouped:

**Reports and coaching**
- Get your daily report — how your account did on any tracked date, with key results and insights
- Get overview analytics — what content tends to work or flop, with examples and next actions
- Get your daily tasks — today's personalized growth tasks, and mark them complete

**Writing**
- Write posts in your style
- Write in SupaBird (viral) style — your voice blended with proven engagement patterns
- Write like a specific creator on X
- Write like your saved creators
- Learn a creator's style — analyze an X account and save a writing style rulebook

**Ideas and research**
- Generate 5–20 post ideas from your own posts or a creator you choose
- Generate ideas from specific posts you feed in
- Search tweets with advanced filters (engagement minimums, date ranges, media type)

**Scheduling and cross-posting**
- Schedule posts (with optional images) and unschedule them back to Drafts
- View scheduled posts and retweets
- See available posting slots; add, move or remove slots
- See connected socials and each platform's character limit
- Cross-post to your other connected social accounts
- Get published post URLs on every platform

Example prompts:
- "Show my performance for yesterday."
- "Generate 10 ideas from my posts in my style."
- "Find tweets about AI agents with at least 500 likes from this week."
- "Schedule this post for tomorrow at 9am on X and LinkedIn."

Chain it with Notion, Gmail, Drive, Slack and other MCP servers, e.g. "turn this week's changelog in Notion into three X posts and schedule them in my free slots".

## Install

### Claude (claude.ai / Claude Desktop)
Settings → Connectors → **Add custom connector** → URL `https://api.supabird.io/mcp` → Connect, then sign in to SupaBird.

### Claude Code
```bash
claude mcp add --transport http supabird https://api.supabird.io/mcp
```

### Cursor
Add to `~/.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "supabird": { "url": "https://api.supabird.io/mcp" }
  }
}
```

### VS Code
```bash
code --add-mcp '{"name":"supabird","type":"http","url":"https://api.supabird.io/mcp"}'
```

### Gemini CLI
```bash
gemini extensions install https://github.com/Farid18baku/supabird-mcp
```

### Clients without remote/OAuth support
Use [`mcp-remote`](https://www.npmjs.com/package/mcp-remote) as a local bridge:
```json
{
  "mcpServers": {
    "supabird": { "command": "npx", "args": ["-y", "mcp-remote", "https://api.supabird.io/mcp"] }
  }
}
```

## Links
- Website: https://supabird.io
- App: https://x.supabird.io
- MCP feature page: https://supabird.io/features/x-twitter-mcp
- Privacy: https://supabird.io/privacy · Terms: https://supabird.io/terms
- Made by [@hustle_fred](https://x.com/hustle_fred) and [@kjuriousBeing](https://x.com/kjuriousBeing)

## License
The contents of this repository (docs and manifests) are MIT licensed. The SupaBird service is subject to the [SupaBird Terms](https://supabird.io/terms).
