# TestCanary2

> Validation test for hsh-deploy after today's 9-layer expansion

Throwaway test service. Will be deleted within 10 min.

[![Powered by AgentScrape](https://raw.githubusercontent.com/hshintelligence/agent-scrape/main/assets/badges/x402-powered.svg)](https://www.x402.org)

## Endpoints

- **MCP**: `https://test-canary-2.healingsunhaven.workers.dev/mcp`
- **A2A Agent Card**: `https://test-canary-2.healingsunhaven.workers.dev/.well-known/agent.json`
- **x402 manifest**: `https://test-canary-2.healingsunhaven.workers.dev/.well-known/x402.json`
- **OpenAPI**: `https://test-canary-2.healingsunhaven.workers.dev/openapi.json`
- **llms.txt**: `https://test-canary-2.healingsunhaven.workers.dev/llms.txt`

## Payment

Pay-per-call in USDC on Base mainnet via the x402 v2 protocol. No signup, no API keys.

## Part of HSH Intelligence

This service is broadcast 24/7 by the [HSH Broadcasting Tower](https://broadcasting.hshintelligence.com).
See all HSH services: `https://test-canary-2.healingsunhaven.workers.dev/services.json`

## Using TestCanary2 from ElizaOS

ElizaOS supports remote MCP servers via the [`@elizaos/plugin-mcp`](https://www.npmjs.com/package/@elizaos/plugin-mcp) package. TestCanary2 works out of the box — no custom integration needed.

```bash
bun add @elizaos/plugin-mcp
```

In your ElizaOS character JSON:

```json
{
  "name": "YourAgent",
  "plugins": ["@elizaos/plugin-mcp"],
  "settings": {
    "mcp": {
      "servers": {
        "test-canary-2": {
          "type": "streamable-http",
          "name": "TestCanary2",
          "url": "https://test-canary-2.healingsunhaven.workers.dev/mcp",
          "timeout": 60
        }
      }
    }
  }
}
```

ElizaOS auto-discovers TestCanary2's tools via standard MCP protocol negotiation.

## Using TestCanary2 from LangChain.js

```typescript
import { MultiServerMCPClient } from "@langchain/mcp-adapters";

const client = new MultiServerMCPClient({
  mcpServers: {
    test-canary-2: { url: "https://test-canary-2.healingsunhaven.workers.dev/mcp" }
  }
});
const tools = await client.getTools();
```

## Using TestCanary2 from LangChain Python

```python
from langchain_mcp_adapters.client import MultiServerMCPClient

client = MultiServerMCPClient({
    "test-canary-2": {
        "url": "https://test-canary-2.healingsunhaven.workers.dev/mcp",
        "transport": "streamable_http",
    }
})
tools = await client.get_tools()
```

## Using TestCanary2 from LlamaIndex

```python
from llama_index.tools.mcp import BasicMCPClient, McpToolSpec

mcp_client = BasicMCPClient("https://test-canary-2.healingsunhaven.workers.dev/mcp")
tools = McpToolSpec(client=mcp_client).to_tool_list()
```

## Discoverability

- **Official MCP Registry**: `io.github.hshintelligence/test-canary-2`
- **A2A Agent Card**: https://test-canary-2.healingsunhaven.workers.dev/.well-known/agent.json
- **x402 manifest**: https://test-canary-2.healingsunhaven.workers.dev/.well-known/x402.json
- **OpenAPI 3.1**: https://test-canary-2.healingsunhaven.workers.dev/openapi.json
- **llms.txt**: https://test-canary-2.healingsunhaven.workers.dev/llms.txt

## License

MIT
