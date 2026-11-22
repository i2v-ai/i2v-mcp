<p align="center">
  <a href="https://i2v.ai">
    <img src="https://i2v.ai/brand/folded-rabbit-light.png" alt="i2v.ai" width="96">
  </a>
</p>

<h1 align="center">i2v.ai remote MCP server</h1>

<p align="center">
  Official metadata for the i2v.ai remote MCP server: discover models, quote inputs, generate media and track tasks from an MCP client.<br>
  Streamable HTTP · OAuth <code>mcp:read</code> / <code>mcp:write</code> · USD ceiling on paid tasks.
</p>

<p align="center">
  <a href="https://registry.modelcontextprotocol.io/v0.1/servers/io.github.i2v-ai%2Fmcp/versions/latest"><img alt="Official MCP Registry" src="https://img.shields.io/badge/registry-io.github.i2v--ai%2Fmcp-6366f1?style=flat-square"></a>
  <a href="https://i2v.ai/mcp"><img alt="Docs" src="https://img.shields.io/badge/docs-i2v.ai%2Fmcp-0ea5e9?style=flat-square"></a>
  <a href="https://lobehub.com/mcp/i2v-ai-i2v-mcp"><img alt="LobeHub MCP Market" src="https://lobehub.com/badge/mcp/i2v-ai-i2v-mcp"></a>
  <a href="./LICENSE"><img alt="License" src="https://img.shields.io/badge/license-MIT-22c55e?style=flat-square"></a>
</p>

<br>

## Connect

```
https://i2v.ai/api/mcp
```

OAuth discovery: <https://i2v.ai/.well-known/oauth-protected-resource/api/mcp>

- `mcp:read` — discover models, read parameters, quote inputs, check balance and usage, track your own tasks.
- `mcp:write` — create tasks and upload reference images. Paid tasks reserve and consume your USD balance.

Read is granted first; write needs an explicit second consent and can be revoked from the account settings.

Client guides for ChatGPT, Codex, [CC], Cursor, GitHub Copilot, VS Code, Kiro and Gemini CLI live at <https://i2v.ai/docs/mcp>.

## Install in Kiro

[![Add i2v.ai to Kiro](https://img.shields.io/badge/Add%20to-Kiro-6b4bd6?style=flat-square)](https://kiro.dev/launch/mcp/add?name=i2v.ai&config=%7B%22url%22%3A%22https%3A//i2v.ai/api/mcp%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D)

The badge opens Kiro with the remote endpoint pre-filled; Kiro then walks through the OAuth consent for `mcp:read`.

## Server metadata

`server.json` is the source of truth for the Official MCP Registry entry `io.github.i2v-ai/mcp`. The `registry.yml` workflow validates the file and publishes it through GitHub OIDC.

```bash
./mcp-publisher validate server.json   # after downloading the publisher binary
```

## For AI agents

- Agent index: <https://i2v.ai/llms.txt>
- Full documentation: <https://i2v.ai/llms-full.txt>
- Skill discovery index: <https://i2v.ai/.well-known/agent-skills/index.json>

## Related repositories

| Repository | Purpose |
| --- | --- |
| [i2v-skills](https://github.com/i2v-ai/i2v-skills) | Agent Skills and plugin manifests |
| [i2v-cli](https://github.com/i2v-ai/i2v-cli) | Command-line tools and local stdio MCP |
| [i2v-sdk-js](https://github.com/i2v-ai/i2v-sdk-js) | TypeScript SDK |
| [i2v-sdk-python](https://github.com/i2v-ai/i2v-sdk-python) | Python SDK |
| [generate-action](https://github.com/i2v-ai/generate-action) | GitHub Action |
| [i2v-api-examples](https://github.com/i2v-ai/i2v-api-examples) | Runnable examples |
| [i2v-agent-tools](https://github.com/i2v-ai/i2v-agent-tools) | Ecosystem hub |

## Privacy and support

- Privacy policy: <https://i2v.ai/privacy-policy>
- Terms of service: <https://i2v.ai/terms-of-service>
- Support: <support@i2v.ai>
- Security reports: <security@i2v.ai>

## License

MIT. See [LICENSE](./LICENSE).
