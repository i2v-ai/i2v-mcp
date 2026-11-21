# Installing the i2v.ai remote MCP server

i2v.ai is a remote Streamable HTTP MCP server. There is nothing to build, clone
or run locally — the client only needs the endpoint and an OAuth authorization.

## Endpoint

```
https://i2v.ai/api/mcp
```

OAuth protected-resource metadata:
<https://i2v.ai/.well-known/oauth-protected-resource/api/mcp>

Scope `mcp:read` covers model discovery, parameter lookup, quoting, balance and
usage, and reading your own tasks. Scope `mcp:write` is a separate consent and
is required to create tasks or upload reference images.

## Cline

Add the server to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "i2v": {
      "type": "streamableHttp",
      "url": "https://i2v.ai/api/mcp"
    }
  }
}
```

Cline opens the browser for OAuth on the first tool call. Choose your i2v.ai
account, grant `mcp:read`, and approve `mcp:write` only when you want to submit
paid generations.

## Verify

Ask the agent to call `list_models` with `{"type":"image"}`. A successful
response returns 12 image models; `{"type":"video"}` returns 16 video models.

Do not send an API key to the local stdio variant. The endpoint above is the
hosted server and uses OAuth only.

## Credit safety

Every paid call is quoted in USD first. `create_task` requires `maxCostUsd` and
an `idempotencyKey`, and the account wallet is the only funding source. Use
`estimate_cost` before `create_task` and keep the ceiling explicit.

## Links

- Documentation: <https://i2v.ai/docs/mcp>
- Product page: <https://i2v.ai/mcp>
- CLI and local stdio MCP: <https://github.com/i2v-ai/i2v-cli>

