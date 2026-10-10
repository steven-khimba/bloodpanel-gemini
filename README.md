# Gemini CLI

BloodPanel is available to Gemini CLI through its public, catalogue-only
Streamable HTTP MCP endpoint. It needs no BloodPanel account, API key or local
server.

## Install the extension

The public BloodPanel Gemini extension connects Gemini CLI directly to the
hosted endpoint:

```sh
gemini extensions install https://github.com/steven-khimba/bloodpanel-gemini
```

Restart Gemini CLI after installation, then verify the server:

```sh
gemini mcp list
```

## Connect the endpoint directly

To add only the remote server to the current project, without installing the
extension, run:

```sh
gemini mcp add --transport http bloodpanel https://bloodpanel.ie/mcp/catalogue
```

Gemini CLI writes project-scoped MCP configuration by default. Add
`--scope user` if you want the connection available across your projects.

Start a new Gemini CLI session and try:

> Use BloodPanel to find an FBC test near Naas.

Run `/mcp list` in an interactive session if the tools do not appear. BloodPanel
uses a public example catalogue. Prices and availability need provider
confirmation. The Gemini extension does not expose appointment or purchase
tools.

The commands and the `httpUrl` manifest field follow the official
[Gemini CLI MCP](https://geminicli.com/docs/tools/mcp-server/) and
[extension](https://geminicli.com/docs/extensions/reference/) documentation.

For gallery discovery, the public GitHub repository must have the
`gemini-cli-extension` topic and a tagged release whose tag matches the manifest
version. Gemini CLI's gallery crawler then checks the root manifest. These
repository settings are applied during release, not by the extension itself.
