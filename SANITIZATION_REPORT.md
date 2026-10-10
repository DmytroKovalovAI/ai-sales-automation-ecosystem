# Sanitization and Static Review Report

## Scope

This report covers eight n8n workflow JSON exports prepared for publication as public portfolio templates. It documents static review and sanitization changes only. It does not certify successful execution or production readiness.

## Changes Applied

- Removed workflow `pinData` and instance-specific top-level metadata where applicable.
- Reviewed node IDs and corrected malformed UUIDs where identified.
- Replaced corrupted BANT budget placeholders with illustrative numeric thresholds:
  - Over UAH 2,000,000
  - UAH 1,000,000–2,000,000
  - UAH 500,000–999,999
  - Under UAH 500,000

  These values are demonstration examples, not verified business rules. Adjust them to the intended qualification policy before use.

- Updated the Dialogue Quality Analyst session assignment to `={{ $json.Skype_ID }}` to align it with the workflow's lead/session identification logic. Confirm that this field is populated and uniquely identifies the intended conversation before production use.
- Replaced a machine-specific Knowledge Base file path with `/path/to/GM_GROUP_Corporate_Knowledge_Base_v1.0.md`.
- Replaced the exported website webhook path with a demo placeholder to avoid publishing a potentially active endpoint path.
- Replaced redacted endpoint values with explicit example placeholders and removed unnecessary trailing whitespace.
- Left external credentials unconfigured. No credentials were created or embedded in the exported workflows.

## Required Configuration Before Use

- Reconnect the required n8n credentials, including OpenAI, Qdrant, PostgreSQL, Zoho CRM, Google Sheets, Telegram, and the Voice AI service, where applicable.
- Replace `.example`, `YOUR_*`, `REPLACE_WITH_*`, and `/path/to/...` placeholders with environment-specific values.
- Configure Google Sheets spreadsheet IDs, sheet names, columns, Telegram destinations, Zoho CRM endpoints and fields, and webhook URLs.
- Place the Markdown Knowledge Base on the n8n host and update the file path in the import workflow. The Knowledge Base file itself is not included in this package.
- Verify that the Qdrant collection's vector dimension matches the selected embedding model.
- Revoke or rotate the previously exposed Happ.tools token if this has not already been done. Do not reuse the exposed token. Configure any newly issued token privately in n8n.

## Static Validation

The following checks should be confirmed against the final files included in this repository:

- All eight workflow files parse as valid JSON.
- No `REDACTED_PHONE` marker remains in the packaged JSON.
- Node IDs are valid UUIDs.
- `pinData` and instance-specific top-level metadata have been removed where applicable.
- No API tokens, phone numbers, or email addresses are present in the exported workflow files, based on the checks performed.

## Limitations

The workflows have not been imported, connected to external services, or executed as part of this static review. External API contracts, node-version compatibility, credentials, CRM schema, Google Sheets layout, webhook payloads, and runtime expressions remain unverified.

Import and test each workflow with synthetic data in a dedicated n8n test environment before activating it in a live environment.
