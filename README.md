# RulesWatch MCP server

Polymarket and Kalshi market rules, with each recorded edit shown before and after.

RulesWatch records edits to the rules of Polymarket and Kalshi prediction markets. This MCP server lets an assistant search markets, read one market's current rules and edit history, and list the newest rule edits.

- Endpoint: `https://ruleswatch.com/api/mcp`
- Transport: streamable HTTP
- Authentication: none for light use. Heavier automated use needs a Pro key; see https://ruleswatch.com/pricing.
- Website: https://ruleswatch.com
- API docs: https://ruleswatch.com/docs/api

All tools are read-only.

## Tools

- `search_markets`: Find Polymarket and Kalshi markets by words in the title.
- `get_market`: One market: its current rules, resolution source and the history of edits. venue is pm (Polymarket) or kalshi.
- `recent_rule_changes`: The newest recorded edits to market rules, with the before and after text.

## Connect

Add it as a remote MCP server in any client that supports streamable HTTP:

```json
{
  "mcpServers": {
    "ruleswatch": {
      "type": "http",
      "url": "https://ruleswatch.com/api/mcp"
    }
  }
}
```

Claude Code: `claude mcp add --transport http ruleswatch https://ruleswatch.com/api/mcp`

This repository holds only this description and the registry entry (`server.json`). The server runs at the endpoint above.
