# Daily JSON Tip Automation

This project automates sending daily beginner-friendly JSON tips via email and logs them into a Google Sheet using n8n workflows integrated with OpenAI.

## Features

- Daily trigger to generate a unique JSON tip using OpenAI
- Sends the tip via email
- Logs each tip with a date to Google Sheets for tracking
- Avoids repeating previous tips by reading logged data from Google Sheets

## Prerequisites

- [n8n](https://n8n.io/) instance (cloud or self-hosted)
- OpenAI API key
- Google Sheets with shareable link (set to "Anyone with the link can view")
- Email SMTP or Gmail credentials for sending emails

## Setup Instructions

1. Clone this repository.

2. Import the provided workflow into your n8n instance.

3. Update credentials:
   - Replace OpenAI API key in n8n credentials.
   - Add your Gmail or SMTP email credentials.
   - Update the Google Sheet ID with your own.

4. Make your Google Sheet publicly viewable to allow n8n to fetch previous tips without OAuth.

5. Test the workflow by running the Cron trigger manually.

6. Enjoy daily JSON tips delivered to your inbox.

## Workflow Structure

- Cron trigger to start the workflow daily
- HTTP Request node to fetch past tips from Google Sheets CSV export
- Function node to parse CSV into an array
- OpenAI node to generate new JSON tips avoiding duplicates
- Set node to format the tip and date
- Email Send node to send the tip via email
- Google Sheets Append node to log the tip and date

## Security Notes

- Ensure your Google Sheet does not contain sensitive data, as it is publicly accessible.
- Keep your OpenAI API key and email credentials secure.
- Regularly monitor logs for any unexpected behavior.

## License

MIT License 