<p align="center"><img src="assets/icon.png" width="96" alt="Docket Room"></p>

# Docket Room MCP server

**Legislative intelligence for all 50 US states, DC and Congress, inside your AI assistant.**

Docket Room gives Claude, ChatGPT, Cursor and other MCP clients live legislative data:
- bill status, full text, sponsors and actions
- roll-call votes
- hearings
- legislators
- federal regulations

Data is read nightly from official legislature sources, so answers come from the record, not a guess. Docket Room also remembers what you track: `whats_new` tells your assistant what changed on your bills and keyword alerts since you last asked. Every result links back to [docketroom.ai](https://docketroom.ai) so you can share it.

This is a hosted (remote) server. There's nothing to install or run locally.

## Connect

| | |
|---|---|
| **Endpoint** | `https://docketroom.ai/api/mcp` (Streamable HTTP) |
| **Auth** | OAuth 2.1 with PKCE and dynamic client registration. You sign in to a free Docket Room account during setup |

**Claude** (web or desktop): Settings → Connectors → *Add custom connector* → paste the endpoint → sign in.

**ChatGPT**: add a custom connector (in developer mode) with the endpoint above, then sign in.

**Cursor**: add to `~/.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "docket-room": { "url": "https://docketroom.ai/api/mcp" }
  }
}
```

**Any MCP client** that supports remote servers with OAuth: use the endpoint above.

## Try asking

- What artificial-intelligence bills had action in any state legislature this week?
- Give me a brief on Wisconsin SB 1027: status, sponsors and what it does.
- Which upcoming hearings in California involve data privacy?
- Compare how states are regulating deepfakes in elections.
- What changed in the latest version of CA SB 53?
- Who sponsored HR 10768, and what else have they introduced on AI?
- What's new on my tracked bills since I last asked?
- Show me the full history of TX SB 1188 and flag the votes that mattered.
- Is this sentence actually in the enrolled text of TX SB 1188? "…"
- Only email me weekly about my tracked bills, and alert me 48 hours before their hearings.

## Plans

| | Free | Pro | Team |
|---|---|---|---|
| Search and read bills, hearings, votes, legislators, regulations | ✅ | ✅ | ✅ |
| Requests per hour | 60 | 1,000 | 5,000+ |
| AI analysis, amendment diffs, multistate comparisons, hearing briefs | 3 a day | ✅ | ✅ |
| Tracked bills | 5 | 100 | more |
| Keyword alerts | 3 | unlimited | unlimited |
| Bill history (`bill_timeline`) | latest 3 events | full | full |
| Quote checks (`verify_quote`) | 5 a day | ✅ | ✅ |
| Shared team records, notes, org-profile impact scoring, webhooks | — | — | ✅ |

See [docketroom.ai/pricing](https://docketroom.ai/pricing).

## Tools

51 tools and 3 prompts, grouped:

| Group | Tools |
|---|---|
| Find bills | `search_bills`, `semantic_search_bills`, `list_bills`, `fast_movers`, `bill_momentum`, `related_bills` |
| Read and verify a bill | `get_bill`, `get_bill_text`, `bill_timeline`, `verify_quote`, `get_bill_votes`, `get_bill_cosponsors`, `list_bill_versions`, `get_bill_changes` |
| AI analysis | `analyze_bill`, `compare_bill_versions`, `compare_bills`, `hearing_brief`, `generate_report` |
| People | `list_legislators`, `get_legislator`, `legislators_on_topic`, `bill_stakeholders` |
| Hearings | `upcoming_hearings`, `get_hearing` |
| Federal regulations | `search_regulations`, `get_regulation` |
| Monitoring | `whats_new`, `set_alerts`, `recent_changes`, `activity_summary`, `tracked_changes`, `track_bill`, `untrack_bill`, `update_tracked_bill`, `list_tracked_bills`, `list_keyword_alerts`, `create_keyword_alert`, `delete_keyword_alert`, `list_webhooks`, `create_webhook`, `delete_webhook` |
| Team workspace | `get_organization_profile`, `set_organization_profile`, `assess_bill_impact`, `scan_relevant_bills`, `set_team_bill_record`, `add_team_bill_note`, `get_team_bill_record`, `list_team_bill_records`, `set_bill_relevance` |
| Prompts | `bill`, `bill_brief`, `topic_scan` |

## Data coverage

- **States:** all 50 states and DC. Official legislature sources are read nightly, and statuses are verified against them.
- **Congress:** bills, votes and hearings.
- **Federal regulations:** Federal Register documents.

## Links

- Website: https://docketroom.ai
- REST API and webhooks: https://docketroom.ai/docs/api
- Privacy: https://docketroom.ai/privacy · Terms: https://docketroom.ai/terms
- Support: support@docketroom.ai

This repository contains the server's public documentation and registry metadata (`server.json`). The service itself is hosted by Docket Room.
