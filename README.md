# AI Content Studio

An n8n content workflow that turns Telegram ideas and URLs into platform-specific drafts, tracks them in Google Sheets and supports scheduled delivery.

## What it does
- Captures ideas and URLs through Telegram.
- Uses Gemini to generate and adapt drafts for LinkedIn, Twitter and Telegram.
- Applies JSON parsing and text-length checks.
- Tracks content and scheduling in Google Sheets.
- Publishes to Telegram and sends ready-to-paste drafts for LinkedIn and Twitter.
- Produces an AI-assisted engagement digest from recorded metrics.

The committed export contains **74 nodes**. Earlier project notes described a 71-node version.

## Files
| File | Purpose |
| --- | --- |
| [ai-content-studio.json](ai-content-studio.json) | Complete n8n workflow export |
| [screenshots.md](screenshots.md) | Existing workflow screenshot link |

## Setup
1. Import `ai-content-studio.json` into n8n.
2. Create your own Telegram, Gemini and Google Sheets credentials, then select them in the imported nodes.
3. Update spreadsheet IDs, sheet names, column mappings and Telegram destinations for your environment.
4. Check the command-parsing and help nodes for the supported commands.
5. Test idea capture, draft generation and scheduling with a private bot and test spreadsheet.
6. Review outputs before enabling the schedule triggers.

The export is inactive by default. It includes a 15-minute scheduling trigger and a weekly digest trigger; review their timezone settings before activation.

## Design notes
Google Sheets stores content state, drafts, scheduling and analytics. AI steps run sequentially, with validation between generation and storage.

LinkedIn and Twitter delivery uses ready-to-paste messages rather than direct publishing. API availability, quotas and hosting costs depend on your own service accounts.

## Status
Portfolio workflow requiring per-instance credentials and configuration. End-to-end execution depends on external services.

**Author:** Rudra Joyti Maitra Soham
