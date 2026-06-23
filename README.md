# Gemsift MCP Server

Query your recruiting pipeline from Claude or ChatGPT. **Gemsift** is an AI resume-triage tool for recruiters; this MCP server connects your AI assistant directly to your own candidate pool.

> Drop in a pile of applicants, get back a shortlist of who is worth a call, including the strong people a keyword filter would bury, with the reasons why. The recruiter always makes the final call.

## Type

Hosted / remote MCP server (Streamable HTTP + SSE), **authenticated**. No install. You connect with a per-workspace key from your Gemsift account: **gemsift.com → Settings → Connect AI**.

## Connect

- Streamable HTTP: `https://gemsift.com/api/mcp/mcp`
- SSE (legacy): `https://gemsift.com/api/mcp/sse`
- Auth header: `Authorization: Bearer <your-workspace-key>`

```json
{
  "mcpServers": {
    "gemsift": {
      "url": "https://gemsift.com/api/mcp/mcp",
      "headers": { "Authorization": "Bearer <your-workspace-key>" }
    }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `list_positions` | Open roles with candidate counts |
| `get_shortlist` | Top candidates for a role, including hidden gems |
| `get_candidate_analysis` | Full parsed profile + per-role evaluations |
| `why_ranked` | Why a candidate scores: matched, missing, transferable |
| `list_trust_flags` | Duplicate / consistency / fraud signals |
| `get_email_forwarding_address` | Forward resumes straight into the pool |
| `create_position` | Create a role from a job description |
| `set_candidate_status` | Move a candidate (shortlist, pass, etc.) by chat |

## About

Gemsift unifies applicants from every source, surfaces candidates who look weak on paper but are strong, and flags duplicates and fraud. Built for individual and agency recruiters who do their own screening.

Learn more and get a key: **https://gemsift.com**
