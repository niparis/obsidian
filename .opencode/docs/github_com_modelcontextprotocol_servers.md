# GitHub - modelcontextprotocol/servers: Model Context Protocol Servers

> Source: https://github.com/modelcontextprotocol/servers
> Cached: 2026-01-20T14:11:22.480Z

---

# Model Context Protocol servers

[](#model-context-protocol-servers)
This repository is a collection of *reference implementations* for the [Model Context Protocol](https://modelcontextprotocol.io/) (MCP), as well as references to community-built servers and additional resources.

Important

If you are looking for a list of MCP servers, you can browse published servers on [the MCP Registry](https://registry.modelcontextprotocol.io/). The repository served by this README is dedicated to housing just the small number of reference servers maintained by the MCP steering group.

The servers in this repository showcase the versatility and extensibility of MCP, demonstrating how it can be used to give Large Language Models (LLMs) secure, controlled access to tools and data sources.
Typically, each MCP server is implemented with an MCP SDK:

- [C# MCP SDK](https://github.com/modelcontextprotocol/csharp-sdk)

- [Go MCP SDK](https://github.com/modelcontextprotocol/go-sdk)

- [Java MCP SDK](https://github.com/modelcontextprotocol/java-sdk)

- [Kotlin MCP SDK](https://github.com/modelcontextprotocol/kotlin-sdk)

- [PHP MCP SDK](https://github.com/modelcontextprotocol/php-sdk)

- [Python MCP SDK](https://github.com/modelcontextprotocol/python-sdk)

- [Ruby MCP SDK](https://github.com/modelcontextprotocol/ruby-sdk)

- [Rust MCP SDK](https://github.com/modelcontextprotocol/rust-sdk)

- [Swift MCP SDK](https://github.com/modelcontextprotocol/swift-sdk)

- [TypeScript MCP SDK](https://github.com/modelcontextprotocol/typescript-sdk)

## 🌟 Reference Servers

[](#-reference-servers)
These servers aim to demonstrate MCP features and the official SDKs.

- **[Everything](/modelcontextprotocol/servers/blob/main/src/everything)** - Reference / test server with prompts, resources, and tools.

- **[Fetch](/modelcontextprotocol/servers/blob/main/src/fetch)** - Web content fetching and conversion for efficient LLM usage.

- **[Filesystem](/modelcontextprotocol/servers/blob/main/src/filesystem)** - Secure file operations with configurable access controls.

- **[Git](/modelcontextprotocol/servers/blob/main/src/git)** - Tools to read, search, and manipulate Git repositories.

- **[Memory](/modelcontextprotocol/servers/blob/main/src/memory)** - Knowledge graph-based persistent memory system.

- **[Sequential Thinking](/modelcontextprotocol/servers/blob/main/src/sequentialthinking)** - Dynamic and reflective problem-solving through thought sequences.

- **[Time](/modelcontextprotocol/servers/blob/main/src/time)** - Time and timezone conversion capabilities.

### Archived

[](#archived)
The following reference servers are now archived and can be found at [servers-archived](https://github.com/modelcontextprotocol/servers-archived).

- **[AWS KB Retrieval](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/aws-kb-retrieval-server)** - Retrieval from AWS Knowledge Base using Bedrock Agent Runtime.

- **[Brave Search](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/brave-search)** - Web and local search using Brave's Search API.  Has been replaced by the [official server](https://github.com/brave/brave-search-mcp-server).

- **[EverArt](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/everart)** - AI image generation using various models.

- **[GitHub](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/github)** - Repository management, file operations, and GitHub API integration.

- **[GitLab](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gitlab)** - GitLab API, enabling project management.

- **[Google Drive](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gdrive)** - File access and search capabilities for Google Drive.

- **[Google Maps](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/google-maps)** - Location services, directions, and place details.

- **[PostgreSQL](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres)** - Read-only database access with schema inspection.

- **[Puppeteer](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/puppeteer)** - Browser automation and web scraping.

- **[Redis](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/redis)** - Interact with Redis key-value stores.

- **[Sentry](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sentry)** - Retrieving and analyzing issues from Sentry.io.

- **[Slack](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/slack)** - Channel management and messaging capabilities. Now maintained by [Zencoder](https://github.com/zencoderai/slack-mcp-server)

- **[SQLite](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sqlite)** - Database interaction and business intelligence capabilities.

## 🤝 Third-Party Servers

[](#-third-party-servers)
Note

The server lists in this README are no longer maintained and will eventually be removed.

### 🎖️ Official Integrations

[](#️-official-integrations)
Official integrations are maintained by companies building production ready MCP servers for their platforms.

- [](https://camo.githubusercontent.com/2d37965ed7115e80d01d251f40d429304ac1e7df0170ea84189b072dd701fcb4/68747470733a2f2f7777772e323173742e6465762f66617669636f6e2e69636f) **[21st.dev Magic](https://github.com/21st-dev/magic-mcp)** - Create crafted UI components inspired by the best 21st.dev design engineers.

- [](https://camo.githubusercontent.com/d91bec931dd79b2a5be420a70f18202b62c09623e3d2f439d79858a136a759ec/68747470733a2f2f7777772e32736c696465732e636f6d2f696d616765732f32736c696465732d7265642e737667) **[2slides](https://github.com/2slides/2slides-mcp)** - An MCP server that provides tools to convert content into slides/PPT/presentation or generate slides/PPT/presentation with user intention.

- [](https://camo.githubusercontent.com/d2da5700493c416de9514bdc7dd60db60c22ab28497b23245007ab15f4b9e1b9/68747470733a2f2f6672616d657275736572636f6e74656e742e636f6d2f696d616765732f4c70534b3174535a77656f6d7241484f4d416a3947656139366c412e737667) **[ActionKit by Paragon](https://github.com/useparagon/paragon-mcp)** - Connect to 130+ SaaS integrations (e.g. Slack, Salesforce, Gmail) with Paragon’s [ActionKit](https://www.useparagon.com/actionkit) API.

- [](https://camo.githubusercontent.com/58b6accd1c3b838b8da08864bb7f7b2eedeb5f079b354e75babf342ec69b2f58/68747470733a2f2f696e766f78782d7075626c69632d6275636b65742e73332e65752d63656e7472616c2d312e616d617a6f6e6177732e636f6d2f66726f6e74656e642d7265736f75726365732f616466696e2d6c6f676f2d736d616c6c2e737667) **[Adfin](https://github.com/Adfin-Engineering/mcp-server-adfin)** - The only platform you need to get paid - all payments in one place, invoicing and accounting reconciliations with [Adfin](https://www.adfin.com/).

- [](https://github.com/AgentOps-AI/agentops/blob/main/docs/favicon.png) **[AgentOps](https://github.com/AgentOps-AI/agentops-mcp)** - Provide observability and tracing for debugging AI agents with [AgentOps](https://www.agentops.ai/) API.

- [](https://camo.githubusercontent.com/ebca6c81fe55b57111730baeeb8e13eb3ee70f3d166ce0176fc66adf33ade255/68747470733a2f2f7777772e6167656e74716c2e636f6d2f66617669636f6e2f66617669636f6e2e706e67) **[AgentQL](https://github.com/tinyfish-io/agentql-mcp)** - Enable AI agents to get structured data from unstructured web with [AgentQL](https://www.agentql.com/).

- [](https://camo.githubusercontent.com/511ca600a3d2c9c03d7a16d4525783fbd4fd0ebd1d79744df7f8ef7a9ca62cae/68747470733a2f2f6167656e747270632e636f6d2f66617669636f6e2e69636f) **[AgentRPC](https://github.com/agentrpc/agentrpc)** - Connect to any function, any language, across network boundaries using [AgentRPC](https://www.agentrpc.com/).

- **[Agentset](https://github.com/agentset-ai/mcp-server)** - RAG for your knowledge base connected to [Agentset](https://agentset.ai).

- [](https://camo.githubusercontent.com/2afe8be25b04ad83e812005d06605588634cabbde4ea3d3fadbb089a726b4872/68747470733a2f2f7777772e61697277616c6c65782e636f6d2f66617669636f6e2e69636f) **[Airwallex Developer](https://www.npmjs.com/package/@airwallex/developer-mcp)** - Empowers AI coding agents with the tools they need to assist developers integrating with [Airwallex APIs](https://www.airwallex.com/docs/api/)

- [](https://camo.githubusercontent.com/ba4623dc9d7da0aa5bd485ca7dd73f2deada3cd490f5ee7ca76819bb69f20890/68747470733a2f2f616976656e2e696f2f66617669636f6e2e69636f) **[Aiven](https://github.com/Aiven-Open/mcp-aiven)** - Navigate your [Aiven projects](https://go.aiven.io/mcp-server) and interact with the PostgreSQL®, Apache Kafka®, ClickHouse® and OpenSearch® services

- [](https://camo.githubusercontent.com/e57ec8cd09cae0b943b1c68381ba8d902671d52544e8b187236c3fd75224d6c2/68747470733a2f2f7777772e616c6174696f6e2e636f6d2f7265736f757263652d63656e7465722f646f776e6c6f61642f377033766e62627a6e6669772f3334464d7442546578357070767332684e59613946632f63383737633337653838653533333938373836353836393763343664326435382f416c6174696f6e2d4c6f676f2d4275672d5072696d6172792e737667) **[Alation](https://github.com/Alation/alation-ai-agent-sdk)** - Unlock the power of the enterprise Data Catalog by harnessing tools provided by the Alation MCP server.

- [](https://camo.githubusercontent.com/bce40fcf9259326c321ec2d70826ff89b8eca45ec2238595bbb89ca730697b9f/68747470733a2f2f692e706f7374696d672e63632f354e597739716a532f616c62792d69636f6e2d686561642d79656c6c6f772d353030783530302e706e67) **[Alby Bitcoin Payments](https://github.com/getAlby/mcp)** - Connect any bitcoin lightning wallet to your agent to send and receive instant payments globally with your agent.

- **[Algolia](https://github.com/algolia/mcp)** - Use AI agents to provision, configure, and query your [Algolia](https://algolia.com) search indices.

- [](https://camo.githubusercontent.com/16ec482b0d077fcb176683454b19f353c538e63d9e72b9bbf2daaf0ed8ca4e8f/68747470733a2f2f696d672e616c6963646e2e636f6d2f696d6765787472612f69342f4f31434e303165706b58774831574c41586b5a6656364e5f2121363030303030303030323737312d322d7470732d3230302d3230302e706e67) **[Alibaba Cloud AnalyticDB for MySQL](https://github.com/aliyun/alibabacloud-adb-mysql-mcp-server)** - Connect to an [AnalyticDB for MySQL](https://www.alibabacloud.com/en/product/analyticdb-for-mysql) cluster for getting database or table metadata, querying and analyzing data. It will be supported to add the OpenAPI for cluster operation in the future.

- [](https://github.com/aliyun/alibabacloud-adbpg-mcp-server/blob/master/images/AnalyticDB.png) **[Alibaba Cloud AnalyticDB for PostgreSQL](https://github.com/aliyun/alibabacloud-adbpg-mcp-server)** - An MCP server to connect to [AnalyticDB for PostgreSQL](https://github.com/aliyun/alibabacloud-adbpg-mcp-server) instances, query and analyze data.

- [](https://camo.githubusercontent.com/abfe4e4d98646b10de2f59e25ef0c35801d5102506f7192d89d9055a5b059bcf/68747470733a2f2f696d672e616c6963646e2e636f6d2f696d6765787472612f69332f4f31434e30313031555757463155596e337241653348555f2121363030303030303030323533302d322d7470732d33322d33322e706e67) **[Alibaba Cloud DataWorks](https://github.com/aliyun/alibabacloud-dataworks-mcp-server)** - A Model Context Protocol (MCP) server that provides tools for AI, allowing it to interact with the [DataWorks](https://www.alibabacloud.com/help/en/dataworks/) Open API through a standardized interface. This implementation is based on the Alibaba Cloud Open API and enables AI agents to perform cloud resources operations seamlessly.

- [](https://camo.githubusercontent.com/1d5174bb4bf1d8d1d532b08fdcc8a41ef73f05e29469043d7d72bc840d6e4b42/68747470733a2f2f6f70656e7365617263682d7368616e676861692e6f73732d636e2d7368616e676861692e616c6979756e63732e636f6d2f6f756875616e672f616c6979756e2d69636f6e2e706e67) **[Alibaba Cloud OpenSearch](https://github.com/aliyun/alibabacloud-opensearch-mcp-server)** - This MCP server equips AI Agents with tools to interact with [OpenSearch](https://help.aliyun.com/zh/open-search/?spm=5176.7946605.J_5253785160.6.28098651AaYZXC) through a standardized and extensible interface.

- [](https://github.com/aliyun/alibaba-cloud-ops-mcp-server/blob/master/image/alibaba-cloud.png) **[Alibaba Cloud OPS](https://github.com/aliyun/alibaba-cloud-ops-mcp-server)** - Manage the lifecycle of your Alibaba Cloud resources with [CloudOps Orchestration Service](https://www.alibabacloud.com/en/product/oos) and Alibaba Cloud OpenAPI.

- [](https://github.com/aliyun/alibabacloud-rds-openapi-mcp-server/blob/main/assets/alibabacloudrds.png) **[Alibaba Cloud RDS](https://github.com/aliyun/alibabacloud-rds-openapi-mcp-server)** - An MCP server designed to interact with the Alibaba Cloud RDS OpenAPI, enabling programmatic management of RDS resources via an LLM.

- [](https://camo.githubusercontent.com/65b6fbf0c516e9b845895150a33ab36d265c3e382e4edbf93f19478d9a70518a/68747470733a2f2f7777772e616c69706179706c75732e636f6d2f66617669636f6e2e69636f) **[AlipayPlus](https://github.com/alipay/global-alipayplus-mcp)** - Connect your AI Agents to AlipayPlus Checkout Payment.

- [](https://camo.githubusercontent.com/74430043795c1e770405bca8e788f8ef87c80da164c73ec3189f30024623499b/68747470733a2f2f646174616c61622e616c6b656d692e61692f66617669636f6e2e706e67) **[Alkemi](https://github.com/alkemi-ai/alkemi-mcp)** - Query Snowflake, Google BigQuery, DataBricks Data Products through Alkemi.ai.

- [](https://camo.githubusercontent.com/a1116f7371156e7a6661c1bec7671348c9b3b6a350aa3fce0327e0762c2b8bbc/68747470733a2f2f63646e2e616c6c766f6963656c61622e636f6d2f7265736f75726365732f776f726b62656e63682f646973742f69636f6e2d6461726b2e69636f) **[AllVoiceLab](https://www.allvoicelab.com/mcp)** - An AI voice toolkit with TTS, voice cloning, and video translation, now available as an MCP server for smarter agent integration.

- [](https://camo.githubusercontent.com/e94b94a3cb291f70fb0482205cea1b5c50f6b8abf228c272c7b826ca8aa9800e/68747470733a2f2f66696c65732e616c706163612e6d61726b6574732f7765626173736574732f66617669636f6e2d33327833322e706e67) **[Alpaca](https://github.com/alpacahq/alpaca-mcp-server)** – Alpaca's MCP server lets you trade stocks and options, analyze market data, and build strategies through [Alpaca's Trading API](https://alpaca.markets/)

- [](https://camo.githubusercontent.com/e6d3f305f920d2eacc3b2602e2ff776badf3c7f0509097cc390cd37726073265/68747470733a2f2f7777772e616c70686176616e746167652e636f2f6c6f676f2e706e672f) **[AlphaVantage](https://mcp.alphavantage.co/)** - Connect to 100+ APIs for financial market data, including stock prices, fundamentals, and more from [AlphaVantage](https://www.alphavantage.co)

- [](https://camo.githubusercontent.com/1ad3fa5ab99218d6b3418067c0c66abe74809df9ed4eeccb91de10937a00db40/68747470733a2f2f616c747465737465722e636f6d2f6170702f7468656d65732f616c747465737465722d736167652d7468656d652f7075626c69632f696d616765732f6c6f676f2d616c747465737465722e3033386563382e706e67) **[AltTester®](htt

... [Content truncated]