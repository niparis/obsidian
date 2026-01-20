# @modelcontextprotocol/sdk - npm

> Source: https://www.npmjs.com/package/@modelcontextprotocol/sdk
> Cached: 2026-01-20T14:11:02.077Z

---

MCP TypeScript SDK [](https://www.npmjs.com/package/@modelcontextprotocol/sdk) [](https://github.com/modelcontextprotocol/typescript-sdk/blob/main/LICENSE)
[](#mcp-typescript-sdk--)

Table of Contents

- [Overview](#overview)

- [Installation](#installation)

- [Quick Start](#quick-start)

- [Core Concepts](#core-concepts)

- [Examples](#examples)

- [Documentation](#documentation)

- [Contributing](#contributing)

- [License](#license)

## Overview

[](#overview)
The Model Context Protocol allows applications to provide context for LLMs in a standardized way, separating the concerns of providing context from the actual LLM interaction. This TypeScript SDK implements
[the full MCP specification](https://modelcontextprotocol.io/specification/draft), making it easy to:

- Create MCP servers that expose resources, prompts and tools

- Build MCP clients that can connect to any MCP server

- Use standard transports like stdio and Streamable HTTP

## Installation

[](#installation)
npm install @modelcontextprotocol/sdk zod
This SDK has a **required peer dependency** on `zod` for schema validation. The SDK internally imports from `zod/v4`, but maintains backwards compatibility with projects using Zod v3.25 or later. You can use either API in your code by importing from `zod/v3` or `zod/v4`:

## Quick Start

[](#quick-start)
To see the SDK in action end-to-end, start from the runnable examples in `src/examples`:

**Install dependencies** (from the SDK repo root):

npm install

**Run the example Streamable HTTP server**:

npx tsx src/examples/server/simpleStreamableHttp.ts

**Run the interactive client in another terminal**:

npx tsx src/examples/client/simpleStreamableHttp.ts

This pair of examples demonstrates tools, resources, prompts, sampling, elicitation, tasks and logging. For a guided walkthrough and variations (stateless servers, JSON-only responses, SSE compatibility, OAuth, etc.), see [docs/server.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md) and
[docs/client.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md).
## Core Concepts

[](#core-concepts)
### Servers and transports

[](#servers-and-transports)
An MCP server is typically created with `McpServer` and connected to a transport such as Streamable HTTP or stdio. The SDK supports:

**Streamable HTTP** for remote servers (recommended).

**HTTP + SSE** for backwards compatibility only.

**stdio** for local, process-spawned integrations.

Runnable server examples live under `src/examples/server` and are documented in [docs/server.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md).

### Tools, resources, prompts

[](#tools-resources-prompts)

**Tools** let LLMs ask your server to take actions (computation, side effects, network calls).

**Resources** expose read-only data that clients can surface to users or models.

**Prompts** are reusable templates that help users talk to models in a consistent way.

The detailed APIs, including `ResourceTemplate`, completions, and display-name metadata, are covered in [docs/server.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md#tools-resources-and-prompts), with runnable implementations in [`simpleStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/simpleStreamableHttp.ts).

### Capabilities: sampling, elicitation, and tasks

[](#capabilities-sampling-elicitation-and-tasks)
The SDK includes higher-level capabilities for richer workflows:

**Sampling**: server-side tools can ask connected clients to run LLM completions.

**Form elicitation**: tools can request non-sensitive input via structured forms.

**URL elicitation**: servers can ask users to complete secure flows in a browser (e.g., API key entry, payments, OAuth).

**Tasks (experimental)**: long-running tool calls can be turned into tasks that you poll or resume later.

Conceptual overviews and links to runnable examples are in:

- [docs/capabilities.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md)

Key example servers include:

- [`toolWithSampleServer.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/toolWithSampleServer.ts)

- [`elicitationFormExample.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/elicitationFormExample.ts)

- [`elicitationUrlExample.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/elicitationUrlExample.ts)

### Clients

[](#clients)
The high-level `Client` class connects to MCP servers over different transports and exposes helpers like `listTools`, `callTool`, `listResources`, `readResource`, `listPrompts`, and `getPrompt`.

Runnable clients live under `src/examples/client` and are described in [docs/client.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md), including:

- Interactive Streamable HTTP client ([`simpleStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/simpleStreamableHttp.ts))

- Streamable HTTP client with SSE fallback ([`streamableHttpWithSseFallbackClient.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/streamableHttpWithSseFallbackClient.ts))

- OAuth-enabled clients and polling/parallel examples

### Node.js Web Crypto (globalThis.crypto) compatibility

[](#nodejs-web-crypto-globalthiscrypto-compatibility)
Some parts of the SDK (for example, JWT-based client authentication in `auth-extensions.ts` via `jose`) rely on the Web Crypto API exposed as `globalThis.crypto`.

See [docs/faq.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/faq.md) for details on supported Node.js versions and how to polyfill `globalThis.crypto` when running on older Node.js runtimes.

## Examples

[](#examples)
The SDK ships runnable examples under `src/examples`. Use these tables to find the scenario you care about and jump straight to the corresponding code and docs.

### Server examples

[](#server-examples)

Scenario
Description
Example file(s)
Related docs

Streamable HTTP server (stateful)
Feature-rich server with tools, resources, prompts, logging, tasks, sampling, and optional OAuth.
[`simpleStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/simpleStreamableHttp.ts)

[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md), [`capabilities.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md)

Streamable HTTP server (stateless)
No session tracking; good for simple API-style servers.
[`simpleStatelessStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/simpleStatelessStreamableHttp.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

JSON response mode (no SSE)
Streamable HTTP with JSON responses only and limited notifications.
[`jsonResponseStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/jsonResponseStreamableHttp.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

Server notifications over Streamable HTTP
Demonstrates server-initiated notifications using SSE with Streamable HTTP.
[`standaloneSseWithGetStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/standaloneSseWithGetStreamableHttp.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

Deprecated HTTP+SSE server
Legacy HTTP+SSE transport for backwards-compatibility testing.
[`simpleSseServer.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/simpleSseServer.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

Backwards-compatible server (Streamable HTTP + SSE)
Single server that supports both Streamable HTTP and legacy SSE clients.
[`sseAndStreamableHttpCompatibleServer.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/sseAndStreamableHttpCompatibleServer.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

Form elicitation server
Uses form elicitation to collect non-sensitive user input.
[`elicitationFormExample.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/elicitationFormExample.ts)
[`capabilities.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md#elicitation)

URL elicitation server
Demonstrates URL-mode elicitation in an OAuth-protected server.
[`elicitationUrlExample.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/elicitationUrlExample.ts)
[`capabilities.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md#elicitation)

Sampling and tasks server
Combines tools, logging, sampling, and experimental task-based execution.
[`toolWithSampleServer.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/toolWithSampleServer.ts)
[`capabilities.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md)

OAuth demo authorization server
In-memory OAuth provider used with the example servers.
[`demoInMemoryOAuthProvider.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/server/demoInMemoryOAuthProvider.ts)
[`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

### Client examples

[](#client-examples)

Scenario
Description
Example file(s)
Related docs

Interactive Streamable HTTP client
CLI client that exercises tools, resources, prompts, elicitation, and tasks.
[`simpleStreamableHttp.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/simpleStreamableHttp.ts)
[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md)

Backwards-compatible client (Streamable HTTP → SSE)
Tries Streamable HTTP first, then falls back to SSE on 4xx responses.
[`streamableHttpWithSseFallbackClient.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/streamableHttpWithSseFallbackClient.ts)

[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md), [`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)

SSE polling client
Polls a legacy SSE server and demonstrates notification handling.
[`ssePollingClient.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/ssePollingClient.ts)
[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md)

Parallel tool calls client
Shows how to run multiple tool calls in parallel.
[`parallelToolCallsClient.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/parallelToolCallsClient.ts)
[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md)

Multiple clients in parallel
Demonstrates connecting multiple clients concurrently to the same server.
[`multipleClientsParallel.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/multipleClientsParallel.ts)
[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md)

OAuth clients
Examples of client_credentials (basic and private_key_jwt) and reusable providers.

[`simpleOAuthClient.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/simpleOAuthClient.ts), [`simpleOAuthClientProvider.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/simpleOAuthClientProvider.ts), [`simpleClientCredentials.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/simpleClientCredentials.ts)

[`client.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md)

URL elicitation client
Works with the URL elicitation server to drive secure browser flows.
[`elicitationUrlExample.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/client/elicitationUrlExample.ts)
[`capabilities.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md#elicitation)

Shared utilities:

- In-memory event store for resumability: [`inMemoryEventStore.ts`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/src/examples/shared/inMemoryEventStore.ts) (see [`server.md`](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md)).

For more details on how to run these examples (including recommended commands and deployment diagrams), see `src/examples/README.md`.

## Documentation

[](#documentation)

Local SDK docs:

[docs/server.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/server.md) – building and running MCP servers, transports, tools/resources/prompts, CORS, DNS rebinding, and multi-node deployment.

[docs/client.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/client.md) – using the high-level client, transports, backwards compatibility, and OAuth helpers.

[docs/capabilities.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/capabilities.md) – sampling, elicitation (form and URL), and experimental task-based execution.

[docs/faq.md](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/docs/faq.md) – environment and troubleshooting FAQs (including Node.js Web Crypto support).

External references:

- [Model Context Protocol documentation](https://modelcontextprotocol.io)

- [MCP Specification](https://spec.modelcontextprotocol.io)

- [Example Servers](https://github.com/modelcontextprotocol/servers)

## Contributing

[](#contributing)
Issues and pull requests are welcome on GitHub at [https://github.com/modelcontextprotocol/typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk).

## License

[](#license)
This project is licensed under the MIT License—see the [LICENSE](https://github.com/modelcontextprotocol/typescript-sdk/blob/HEAD/LICENSE) file for details.