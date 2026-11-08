# Crosspublish MCP

Create, schedule, and manage social media posts with AI assistants.

[Crosspublish](https://crosspublish.com) is a social media scheduler. This MCP server lets Claude, Cursor, and other MCP clients draft posts, queue them, check analytics, and answer your inbox across your connected accounts.

This repository is the public listing for the hosted server. The server itself is remote, so there is nothing to install or run locally.

- **Endpoint:** `https://crosspublish.com/api/mcp`
- **Transport:** streamable HTTP
- **Auth:** OAuth (browser sign-in) or an API key (`Authorization: Bearer cp_live_...`) created in Crosspublish settings
- **Website:** https://crosspublish.com

## Setup

### Claude (claude.ai / Claude Desktop)

Settings → Connectors → Add custom connector → `https://crosspublish.com/api/mcp`, then sign in.

### Claude Code

```bash
claude mcp add --transport http crosspublish https://crosspublish.com/api/mcp
```

### Cursor / other clients (API key)

```json
{
  "mcpServers": {
    "crosspublish": {
      "url": "https://crosspublish.com/api/mcp",
      "headers": { "Authorization": "Bearer cp_live_YOUR_KEY" }
    }
  }
}
```

## Tools

| Area | Tools |
| --- | --- |
| Accounts | `list_social_sets`, `set_active_social_set`, `list_social_accounts` |
| Posts | `list_posts`, `get_post`, `create_draft`, `update_post`, `delete_post`, `set_post_options` |
| Scheduling | `schedule_post`, `unschedule_post`, `publish_now`, `move_to_drafts` |
| Per-account copies | `add_accounts`, `remove_accounts`, `detach_copy`, `merge_copy` |
| Media | `upload_media`, `request_upload_link`, `attach_media`, `remove_media`, `list_media` |
| Analytics | `get_analytics`, `list_post_analytics` |
| Inbox | `list_inbox`, `get_conversation`, `reply_to_comment`, `reply_to_conversation` |
| Platform helpers | `get_tiktok_creator_info`, `list_pinterest_boards`, `search_x_communities` |

## License

MIT. Covers the contents of this repository only; the Crosspublish service is governed by its own terms.
