# indox for Claude

Convert files and pull data out of PDFs from Claude, using your [indox.org](https://indox.org) account. Ask Claude to turn a PDF into Word, compress or merge PDFs, convert images, video, 3D models or fonts, or extract the tables in a statement or invoice into Excel, CSV or JSON. Every job runs on your indox account and spends its credits, with the price checked before anything runs.

## What is inside

- **Connector** `indox` — the hosted MCP server at `https://mcp.indox.org/mcp`. You sign in with your indox account the first time Claude uses it.
- **Skill** `convert-document` — when and how to convert a file, including how to hand a local file to indox.
- **Skill** `extract-tables` — when and how to pull tables and text out of a PDF.

The plugin ships no code: only these instructions and the connector address.

## Tools the connector provides

| Tool | What it does |
|------|--------------|
| `list_formats` | Input and output formats for a kind of file |
| `convert_file` | Start a conversion (spends credits) |
| `extract_data` | PDF tables and text to xlsx, csv or json (spends credits) |
| `pdf_tools_list`, `pdf_tool_describe`, `pdf_run_tool` | PDF operations such as compress, merge, split, rotate, redact and sign |
| `get_conversion`, `wait_conversion` | Job status |
| `download_result` | A short-lived download link for the result |
| `create_upload_url`, `list_files` | Upload a local file to your indox storage, list stored files |
| `credits_balance`, `usage_summary` | Your credit balance and recent usage |
| `pdf_ai_job`, `health` | AI job status, service check |

## Data handling

- **Where data goes:** only to indox. Claude talks to `mcp.indox.org`, which calls the indox API at `indox.org` as you. The plugin sends nothing anywhere else.
- **What is sent:** the files or links you ask Claude to convert, and the options for each job. Results come back as download links.
- **Sign-in:** OAuth on indox.org. You choose what Claude may do (convert files, use your storage, read your credits), and you can remove the connection at any time.
- **Storage and retention:** as described in the [indox Privacy Policy](https://indox.org/privacy). Use is subject to the [indox Terms of Service](https://indox.org/terms).

## Use it

- **claude.ai, Claude Desktop and Cowork:** install the plugin from the Claude directory, then connect indox on the plugin's Connectors tab.
- **Claude Code:** install from the directory, or try a local copy with `claude --plugin-dir ./indox-claude-plugin`. Run `/mcp` to sign in to indox.

Files attached in a chat cannot be forwarded to the connector. Give Claude a public link, or work from Claude Code or Cowork, where Claude can upload a local file.

## Support

[indox.org/support](https://indox.org/support) · [Connector documentation](https://indox.org/en-US/developers/sdk/mcp)
