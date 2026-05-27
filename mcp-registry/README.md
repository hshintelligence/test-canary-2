# Official MCP Registry artifact

This directory contains the canonical `server.json` published to the
[Official MCP Registry](https://registry.modelcontextprotocol.io) at
`io.github.hshintelligence/test-canary-2`.

## Re-publish on version bump

\`\`\`bash
brew install mcp-publisher
mcp-publisher login github
# bump "version" in server.json to match the new TestCanary2 release
mcp-publisher validate
mcp-publisher publish
\`\`\`
