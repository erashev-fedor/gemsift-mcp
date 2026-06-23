# Gemsift MCP Server

**Query your recruiting pipeline from Claude or ChatGPT.**

Gemsift is an AI resume-triage tool for recruiters. This MCP server connects your AI
assistant directly to your own candidate pool, so you can screen, shortlist, and move
candidates by chat. Drop in a pile of applicants and ask your AI who is actually worth a
call, including the strong people a keyword filter would normally bury, with the reasons
why. The recruiter always makes the final call.

## Who it's for

Individual and agency recruiters, and small in-house hiring teams who do their own
first-pass screening, drown in inbound applications, and do not want to lose a good
candidate just because they look weak on paper.

## What you can do (ask your AI things like)

- "Show me the shortlist for my Backend Engineer role, and flag any hidden gems."
- "Why is Maria ranked above the other candidates for this position?"
- "Any duplicate or suspicious applications in my pool right now?"
- "Create a role from this job description and tell me who already fits."
- "Move James to shortlist and pass on the rest for the Designer role."

## Connect

Hosted, remote server. No install. You authenticate with a per-workspace key from your
Gemsift account: **gemsift.com → Settings → Connect AI**.

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
| `list_positions` | Your open roles with candidate counts |
| `get_shortlist` | Top candidates for a role, including hidden gems |
| `get_candidate_analysis` | Full parsed profile and per-role evaluations for one person |
| `why_ranked` | Why a candidate scores the way they do: matched, missing, transferable |
| `list_trust_flags` | Duplicate, consistency, and fraud signals in your pool |
| `get_email_forwarding_address` | A forwarding address to send resumes straight into the pool |
| `create_position` | Create a role from a job description |
| `set_candidate_status` | Move a candidate (shortlist, pass, and so on) by chat |

## How it is different

Most screeners rank against keywords and quietly drop everyone below a threshold. Gemsift
does the opposite: it surfaces the strong people who read weak on paper, unifies applicants
from every source into one pool, removes duplicates, and flags likely fraud, all with the
reasoning visible so you can trust or overrule it.

Learn more and get a key: **https://gemsift.com**
