# TikTok/Tech Trending Topic Generator – Powered by n8n

This workflow fetches trending tech articles from TechCrunch, uses OpenAI to generate TikTok-ready summaries, and logs them into Google Sheets. Once complete, it emails a summary to you.

## 🚀 How It Works

1. **Daily Trigger** - Runs automatically at your scheduled time (e.g., 9:00 AM)
2. **Fetch Articles** - Pulls the latest tech articles from TechCrunch RSS feed
3. **AI Processing** - Uses OpenAI to create TikTok-ready content for each article:
   - Short attention-grabbing title (max 7 words)
   - Clear 1-2 sentence summary
   - 15-second TikTok hook script
   - Relevant hashtags
4. **Save to Sheets** - Logs all generated content to your Google Sheet
5. **Email Notification** - Sends you a completion email when done

## ⚙️ Setup Instructions

### 1. Import the JSON workflow into your n8n instance
- Download the `trendingtech_topics_inspo.json` file
- In n8n, go to **Workflows** → **Import from File**
- Select the downloaded JSON file

### 2. Set up your OpenAI credentials and Gmail credentials in n8n
- **OpenAI**: Go to **Settings** → **Credentials** → **Create New** → **OpenAI**
  - Add your OpenAI API key
  - Replace `YOUR_OPENAI_CREDENTIAL_ID_HERE` and `YOUR_OPENAI_CREDENTIAL_NAME_HERE` in the workflow
- **Gmail**: Create **Gmail OAuth2** credentials
  - Follow n8n's Gmail setup guide
  - Replace `YOUR_GMAIL_CREDENTIAL_ID_HERE` and `YOUR_GMAIL_CREDENTIAL_NAME_HERE` in the workflow

### 3. Link your Google Sheet (use your own sheet ID and tab name)
- Create a Google Sheet with columns: **Date**, **Title**, **Summary**, **Hook**, **hashtags**
- Set up **Google Sheets OAuth2** credentials in n8n
- Replace `YOUR_GOOGLE_SHEETS_CREDENTIAL_ID_HERE` and `YOUR_GOOGLE_SHEETS_CREDENTIAL_NAME_HERE`
- Replace `YOUR_GOOGLE_SHEET_ID_HERE` with your actual Google Sheet ID
- Replace `YOUR_SHEET_TAB_NAME_HERE` with your sheet tab name

### 4. Enable the Cron trigger (e.g. 9AM daily)
- Open the **Daily 9AM Trigger1** node
- Set your preferred schedule (default: `0 9 * * *` for 9:00 AM daily)

### 5. Customize the email recipient in the Gmail node
- Open the **Gmail1** node
- Replace `YOUR_EMAIL_HERE` with your actual email address

## 📋 Required Credentials

- **OpenAI API** - For generating TikTok content
- **Google Sheets OAuth2** - For saving generated ideas
- **Gmail OAuth2** - For email notifications

## 🎯 Output Format

Each generated idea includes:
- **Title**: Catchy 7-word headline
- **Summary**: Clear 1-2 sentence explanation
- **Hook**: 15-second TikTok script
- **Hashtags**: Relevant social media tags
- **Date**: When the idea was generated

## 🔧 Customization

You can modify:
- **RSS Source**: Change the TechCrunch URL to any RSS feed
- **AI Prompt**: Adjust the OpenAI prompt for different content styles
- **Schedule**: Modify the cron trigger timing
- **Email Template**: Customize the notification message

---

**Author**: Mstimaj  
**Signature**: forward ▸ upward ▸ onward

---

*This workflow is part of the n8n SimpleFlows collection. Feel free to fork, modify, and share!* 