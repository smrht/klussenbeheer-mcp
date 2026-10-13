<img src="logo-400.png" alt="Klussenbeheer logo" width="96" height="96">

# Klussenbeheer MCP server

**Job management for Dutch service companies: jobs, customers, planning, quotes and invoices.**

Remote MCP server: `https://samdesk.nl/mcp` (Streamable HTTP) · Website: [samdesk.nl/klussenbeheer](https://samdesk.nl/klussenbeheer/)

## What it does

Klussenbeheer is job-management software for Dutch tradespeople and service companies. It brings leads, planning, quotes, work orders and invoices together. Through this MCP server an AI assistant works in your existing account: it finds customers and jobs, reads today's work and the planning, opens job details, adds notes, creates and schedules jobs, drafts and sends quotes, and lists open invoices.

Every write asks for explicit confirmation and follows the permissions of your account. The server does not sell subscriptions or take payments.

## Connect

- **Server URL:** `https://samdesk.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Sign in with your Klussenbeheer account when your client asks.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http klussenbeheer https://samdesk.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "klussenbeheer": {
      "type": "http",
      "url": "https://samdesk.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `zoek_klanten / zoek_klussen` | Search customers and jobs. |
| `vandaag / planning / overzicht` | Today's work, the planning and a status overview. |
| `klus_detail / klus_aanmaken / klus_bijwerken` | Read, create and update a job. |
| `klus_inplannen / klus_toewijzen / fase_wijzigen` | Schedule, assign and move a job to another stage. |
| `notitie_toevoegen / werkregel_toevoegen / rit_registreren` | Add notes, work lines and mileage. |
| `klant_toevoegen / klant_bijwerken / klantlink_maken` | Create or update customers and share a customer link. |
| `offerte_maken / offerte_versturen / offertes` | Draft, send and list quotes. |
| `openstaande_facturen / factuurstatus_zetten` | Open invoices and invoice status. |
| `berichten / mail_naar_klant / teamleden / account` | Messages, customer mail, team and account info. |

## Example prompts

- What is on the planning for tomorrow?
- Create a job for Jansen in Hoorn: replace the kitchen tap, next Tuesday morning.
- Which invoices are still open, and for how long?

## Links

- Website: https://samdesk.nl/klussenbeheer/
- Documentation: https://samdesk.nl/plugin/
- Privacy policy: https://samdesk.nl/plugin/privacy/
- Terms: https://samdesk.nl/nl/terms-of-service/
- n8n node: https://www.npmjs.com/package/n8n-nodes-klussenbeheer
- Support: mailto:support@samdesk.nl

## Keywords

field service management, job management, work order software, scheduling, dispatch, quotes, invoices, CRM for trades, contractor software, Netherlands.

Nederlands: klussen beheren, werkbonnen, planning software, offerte maken, facturen, klantenbeheer, software voor vakmensen, installateur software, zzp planning, klusbedrijf.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/beheerjewp/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/ulazai/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/backlinkswinkel/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
