# SupaBird MCP Server

<img src="assets/supabird-icon-512.png" width="96" alt="SupaBird logo" />

The official remote MCP server for [SupaBird](https://supabird.io), your social media growth agent. Bring your SupaBird account into Claude, Cursor, VS Code, Gemini CLI or any MCP client: find viral content, write in your voice, and schedule posts across all major social media platforms.

- **Endpoint:** `https://api.supabird.io/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 — your client opens a SupaBird sign-in page the first time it connects. No API key to copy.
- **Requires:** a SupaBird account ([start a free trial](https://x.supabird.io/auth)). MCP usage is paid from your SupaBird credit wallet.

## What it can do

64 tools:

### Writing

| Tool | What it does |
| --- | --- |
| `write_in_my_style` | Rewrite your text into post drafts in your own writing style |
| `write_in_supabird_style` | Drafts that blend your voice with proven engagement patterns |
| `write_like_my_creators` | Drafts in the combined style of the creators you picked in SupaBird |
| `write_like_creator` | Drafts in the voice of any specific creator on X |
| `learn_creator_style` | Analyze a creator's posts and save a writing-style rulebook |

### Ideas

| Tool | What it does |
| --- | --- |
| `generate_ideas` | Generate post ideas from your posts or a creator's, in your style or theirs |
| `generate_ideas_from_posts` | Generate ideas from specific posts you pass in |
| `check_ideas_status` | Get the results of an idea-generation job |
| `get_saved_ideas` | Ideas you saved in SupaBird |

### Scheduling and publishing

| Tool | What it does |
| --- | --- |
| `schedule_post` | Schedule a post (with images or video), optionally cross-posting to other platforms |
| `schedule_saved_post` | Schedule one of your drafts or saved ideas |
| `get_scheduled_posts` | Upcoming scheduled posts and reposts |
| `unschedule_post` | Cancel a queued post (it moves back to Drafts) |
| `get_drafts` | Your saved drafts |
| `cross_post` | Send an existing post to LinkedIn, Threads, Bluesky, Instagram or TikTok |
| `get_published_urls` | Public links to a published post on every platform |
| `get_connected_socials` | Which social accounts are connected, plus character limits |
| `list_social_sets` | Your social sets (one brand = its own set of accounts) |
| `create_image_upload` | Get an upload link for images to attach to a post |
| `create_video_upload` | Get an upload link for a video to attach to a post |
| `get_image_upload` | Check whether attached media finished uploading |

### Posting calendar

| Tool | What it does |
| --- | --- |
| `get_posting_slots` | Free, filled and past posting slots for any day |
| `add_posting_slot` | Add a repeating weekly posting time |
| `update_posting_slot` | Move or retag a slot (every week or one date only) |
| `remove_posting_slot` | Remove a repeating posting time |

### Reports and daily tasks

| Tool | What it does |
| --- | --- |
| `get_daily_performance_report` | How your account did on any tracked day |
| `get_overview_analytics` | What tends to work or flop, with examples and next steps |
| `get_daily_tasks` | Today's personalized growth tasks (or a past day's) |
| `complete_daily_task` | Mark a daily task as done |

### Search and research

| Tool | What it does |
| --- | --- |
| `search_tweets` | Find posts with SupaBird Magic Search, in plain language |
| `filter_posts` | Filter posts loaded from a list or community by what you describe |
| `search_users` | Search accounts by keyword |
| `get_trends` | Trending topics for a location |
| `get_article` | Read an X Article |
| `get_space_detail` | Details of an X Space |

### Posts and threads

| Tool | What it does |
| --- | --- |
| `get_tweets_by_ids` | Fetch posts by ID |
| `get_tweet_replies` | Replies to a post |
| `get_tweet_replies_v2` | Replies to a post, sorted by relevance, latest or likes |
| `get_tweet_quotes` | Quote posts of a post |
| `get_tweet_retweeters` | Accounts that reposted a post |
| `get_tweet_thread_context` | The thread around a post |

### Accounts

| Tool | What it does |
| --- | --- |
| `get_user_info` | Profile by username |
| `get_user_about` | Extended profile details |
| `get_user_last_tweets` | An account's recent posts |
| `get_user_timeline` | An account's profile timeline |
| `get_user_mentions` | Posts mentioning an account |
| `get_user_followers` | An account's followers |
| `get_user_followers_ids` | An account's follower IDs |
| `get_user_verified_followers` | An account's verified followers |
| `get_user_followings` | Accounts someone follows |
| `check_follow_relationship` | Whether two accounts follow each other |
| `batch_get_users_by_ids` | Look up up to 20 profiles by ID |

### Lists and communities

| Tool | What it does |
| --- | --- |
| `get_list_tweets` | Posts from a list |
| `get_list_timeline` | A list's timeline |
| `get_list_members` | Members of a list |
| `get_list_followers` | Followers of a list |
| `get_community_tweets` | Posts from a community |
| `search_community_tweets` | Search posts across communities |
| `get_community_info` | Community details |
| `get_community_members` | Community members |
| `get_community_moderators` | Community moderators |

### Utility

| Tool | What it does |
| --- | --- |
| `ping_supabird` | Check that the server is responding |
| `check_job_status` | Get the result of a long-running tool call |
| `dismiss_update_notice` | Stop update notifications |

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

### Claude Code plugin
```bash
/plugin install supabird --marketplace Farid18baku/supabird-mcp
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
