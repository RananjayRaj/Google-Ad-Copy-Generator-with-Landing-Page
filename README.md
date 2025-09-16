This repository contains a sanitized n8n workflow export: **Google Ads Ad Copy Generator from Landing Page**.

> ⚠️ **Important:** This repository is sanitized. All credential IDs, webhook IDs, and direct document URLs have been replaced with placeholders. Before using the workflow you must attach your own credentials and replace placeholders.

## Files

- `workflows/google-ads-adcopy-from-landingpage.sanitized.json` — sanitized n8n workflow (importable).
- `.env.example` — example environment variables for local reference.
- `README.md` — this file.

## Quick start

1. **Clone the repo**
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```

2. **Import the workflow**
   - Open your n8n instance.
   - Import `workflows/google-ads-adcopy-from-landingpage.sanitized.json` (Import → From File).

3. **Create credentials in n8n**
   Create the credentials and attach them to the matching nodes via the n8n UI (recommended):
   - **OpenAI (or LLM provider)** — used in `OpenAI` and `OpenAI2` nodes.
   - **Google Sheets OAuth2** — used in the `Google Sheets` node.
   - **Firecrawl / Scraper provider** — used in the Firecrawl/`Scrape a url and get its content` node (if you use the same service).

   After creating credentials, open the imported workflow, select each node with a credential slot, and choose the credential you created.

4. **Replace placeholders**
   - `REPLACE_GOOGLE_SHEET_ID` — edit the Google Sheets node and paste your spreadsheet ID.
   - Any `REPLACE_*_CREDENTIAL_ID` / `REPLACE_*_CREDENTIAL_NAME` — not required if you attach credentials via the UI; placeholders are included for reference.
   - If you use a custom scraping service or HTTP proxy, update those nodes accordingly.

5. **(Optional) Environment variables**
   - If you prefer environment-driven config, use `.env` or your host environment with the variables from `.env.example`.

6. **Test**
   - Submit the form trigger (or simulate inputs) and watch the execution. Enable the trigger node to generate a new webhook URL (the sanitized export has `webhookId` set to null; n8n will create a new webhook when you activate the trigger).

## Security & best-practices

- **Never commit real credentials** (API keys, client secrets) into the repo.
- Use n8n’s credential store and attach credentials through the UI — do not hard-code them into code nodes.
- If a secret was accidentally committed, **rotate/revoke** it immediately.
- Keep code nodes free of long-lived tokens. Use environment variables or the n8n credential mechanism.
- Consider adding `CONTRIBUTING.md` to explain how contributors should name credentials.
