# Silla Global Frontier Systems Landing Page

This is the Vercel-ready Silla Global landing page with a production form flow.

## Files

- `index.html`: the public landing page.
- `SillaGlobalLogo.png`: the header logo asset.
- `api/submit-application.js`: Vercel serverless function that saves application submissions to Airtable and optionally sends Resend email notifications.
- `silla_airtable_applications_template.csv`: Airtable setup headers.

## Required Vercel environment variables

Add these in Vercel under Project Settings > Environment Variables.

| Variable | Required | Purpose |
|---|---:|---|
| `AIRTABLE_API_KEY` | Yes | Airtable personal access token with write access to the base. |
| `AIRTABLE_BASE_ID` | Yes | Airtable base ID for the Silla Global Applications base. |
| `AIRTABLE_TABLE_NAME` | Yes | Table name, recommended: `Applications`. |
| `RESEND_API_KEY` | Optional | Sends email alerts after the application is saved. |
| `NOTIFY_TO_EMAIL` | Optional | Notification recipient, recommended: `partners@silla.global`. |
| `NOTIFY_FROM_EMAIL` | Optional | Verified Resend sender, for example `Silla Global <applications@sillaglobal.com>`. |

## Airtable table fields

Create an Airtable table named `Applications` with the fields listed in `silla_airtable_applications_template.csv`. The form will create one row per application.

## Important

The form will only save applications on Vercel after the Airtable environment variables are added and the site is redeployed. Resend is optional because Airtable is the primary database.
