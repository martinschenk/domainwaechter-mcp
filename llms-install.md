# Installing the Domainwächter MCP server

1. Add a remote MCP server with this URL: `https://www.domainwaechter.de/api/v1/mcp` (Spanish market: `https://www.itvweb.es/api/v1/mcp`). Transport: Streamable HTTP.
2. Your client opens a sign-in page. Enter your e-mail address, then the six-digit code sent to it, and approve access (scope `analyses`).
3. Ask your assistant to check a website you operate. Before the first check you prove you operate the site, either by uploading a small file to it or by adding a DNS TXT record (for site builders and shops without file access); the assistant tells you both ways, with the exact content, if the domain is not yet verified. You confirm authorization in the browser.
4. Analyses take about two minutes. The assistant collects the result with `get_analysis`.

No API key is needed. The server never changes your website.
