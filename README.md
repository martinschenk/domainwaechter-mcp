# Domainwächter MCP

Remote MCP server for [Domainwächter](https://www.domainwaechter.de) (German) and [ITV web](https://www.itvweb.es) (Spanish): a passive security check of a website you operate, with a repair guide your AI assistant can walk you through.

- Endpoint (German market): `https://www.domainwaechter.de/api/v1/mcp`
- Endpoint (Spanish market): `https://www.itvweb.es/api/v1/mcp`
- Transport: Streamable HTTP, stateless, OAuth 2.1 (dynamic client registration, PKCE). Sign-in is a six-digit code sent by e-mail.

## Tools

| Tool | What it does | Read-only |
|---|---|---|
| `analyze_website` | Starts a check of a domain whose operator has verified it (verification file on the server). Returns a `job_id`. | no |
| `get_analysis` | Status and result: score, findings by severity, report and PDF links, repair guide in Markdown. | yes |
| `list_analyses` | The latest 20 analyses of the account. | yes |
| `get_quota` | Free analyses left this month and where to add credit. | yes |

The server only looks at publicly reachable information, from outside. It never changes anything on your website. Changes proposed in the repair guide are made only by you, or by your assistant with your explicit consent and access you granted on purpose. The check is software, not legal or professional advice.

## Connect in your assistant

- **Claude:** Settings, Connectors, add custom connector, paste the endpoint URL.
- **ChatGPT, Mistral Le Chat, Perplexity, Grok and other clients with remote MCP:** add the endpoint URL as a remote MCP server; the client handles registration and sign-in.
- **Claude Code:** `claude mcp add --transport http domainwaechter https://www.domainwaechter.de/api/v1/mcp`
- **Claude Code plugin:** `/plugin marketplace add martinschenk/domainwaechter-mcp`, then `/plugin install domainwaechter@domainwaechter`

See [llms-install.md](llms-install.md) for step-by-step setup.

## Limits

Three new analyses per account and month are free; repeated analyses of the same domain within 30 days are served from cache. After that each analysis is paid from prepaid credit that you add yourself in the browser. No tool moves money.

## Links

[Privacy](https://www.domainwaechter.de/datenschutz.html) · [Terms](https://www.domainwaechter.de/agb.html) · [Imprint](https://www.domainwaechter.de/impressum.html) · Support: martin@domainwaechter.de
