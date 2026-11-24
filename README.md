# Auto Inspect — South African vehicle checks (MCP server)

Remote [Model Context Protocol](https://modelcontextprotocol.io) server for **South African vehicle checks**, by [GetKonnektED](https://getkonnekted.com) (Konnektivity (Pty) Ltd t/a GetKonnektED, reg. 2026/363576/07).

**Server URL:** `https://autoinspect.co.za/api/mcp/vehicle` — Streamable HTTP, **no sign-in, no key**, free.

Listed on the [official MCP Registry](https://registry.modelcontextprotocol.io) as `za.co.autoinspect/sa-vehicle` and in the Claude connector directory.

## Tools (all read-only)

| Tool | What it does |
|---|---|
| `vehicle_vin_check` | VIN format and check digit, country and maker, possible model years |
| `sa_licence_disc_status` | Is a licence disc valid, in the 21-day grace period or expired — with an estimate of the late-renewal penalty |
| `sa_number_plate_check` | Which South African province a number plate format points to |
| `sa_find_test_stations` | Roadworthy / COF testing stations from the official provincial registers |
| `autoinspect_verify_report` | Whether an Auto Inspect inspection, intake or hand-over report is genuine and unchanged, from its verification code |

These are deterministic checks: Auto Inspect **never looks up a vehicle's owner or any personal information**. Results are information only — not a roadworthy certificate or a valuation.

## Connect

- **Claude:** Settings → Connectors → find *Auto Inspect* in the directory, or add a custom connector with the server URL.
- **ChatGPT:** Settings → Apps & Connectors → developer mode → create a connector with the server URL (no authentication).
- **Gemini CLI:** `gemini mcp add --transport http autoinspect https://autoinspect.co.za/api/mcp/vehicle`
- **Claude Code:** `claude mcp add --transport http autoinspect https://autoinspect.co.za/api/mcp/vehicle`

See [`examples/`](examples/) for client configuration files.

## Example questions

- "Which province does the number plate CA 123-456 point to, and is VIN 1HGCM82633A004352 valid?"
- "My licence disc expired on 31 August 2026 — is it still valid and what is the penalty?"
- "Where can I get a roadworthy test near Stellenbosch?"

## Terms and privacy

- AI tools terms: https://autoinspect.co.za/terms.html
- Privacy: https://getkonnekted.com/privacy.html
- Support: support@getkonnekted.com

This repository holds listing files only (server metadata and client examples); the server itself is hosted by GetKonnektED.
