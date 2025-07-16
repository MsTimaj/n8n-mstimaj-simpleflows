# 🧠 Telegram to Ollama AI Bot - Starter Version

A **starter template** for a self-hosted Telegram bot powered by **n8n** - this is a simplified version that shows the concept without AI integration.

> **⚠️ This is NOT the full AI workflow!** This starter version only sends a promotional message. For the complete AI-powered bot with Ollama integration, get the full version.

---

## 🎯 What This Starter Does

- ✅ **Telegram Integration** - Receives messages via webhook
- ✅ **Basic Response** - Sends a promotional message about the full version
- ✅ **100% Private** - Everything runs on your machine
- ✅ **n8n Powered** - Easy to customize and expand

**What it does NOT do:**
- ❌ No AI processing
- ❌ No Ollama integration
- ❌ No intelligent responses

---

## 🚀 Complete Setup Guide (Step-by-Step)

### Prerequisites
- Windows 10/11 computer
- Basic computer skills
- 30 minutes of your time

---

## Step 1: Install Required Software

### 1.1 Install Node.js
1. Go to [https://nodejs.org/](https://nodejs.org/)
2. Download the "LTS" version (recommended)
3. Run the installer and follow the prompts
4. Restart your computer

### 1.2 Install n8n
1. Open Command Prompt as Administrator
2. Run this command:
   ```
   npm install -g n8n
   ```
3. Wait for installation to complete

### 1.3 Install ngrok
1. Go to [https://ngrok.com/](https://ngrok.com/)
2. Sign up for a free account
3. Download ngrok for Windows
4. Extract the zip file to a folder (e.g., `C:\ngrok`)
5. Add ngrok to your PATH or use the full path

---

## Step 2: Create a Telegram Bot

### 2.1 Get Bot Token
1. Open Telegram and search for `@BotFather`
2. Send `/start`
3. Send `/newbot`
4. Choose a name for your bot (e.g., "My Test Bot")
5. Choose a username ending in 'bot' (e.g., "mytestbot123")
6. **Save the bot token** - you'll need it later!

---

## Step 3: Set Up the Workflow

### 3.1 Start n8n
1. Open Command Prompt
2. Navigate to your project folder
3. Run: `n8n start`
4. Wait for n8n to start (you'll see "n8n ready on port 5678")
5. Open your browser and go to: `http://localhost:5678`

### 3.2 Import the Workflow
1. In n8n, click "Import from file"
2. Select the `starter-workflow.json` file from this repository
3. Click "Import"

### 3.3 Configure the Bot Token
1. Click on the "📤 Send Telegram" node
2. Replace `YOUR_BOT_TOKEN_HERE` with your actual bot token
3. Click "Save"

### 3.4 Activate the Workflow
1. Click the "Active" toggle to turn on the workflow
2. The workflow is now ready!

---

## Step 4: Set Up ngrok (Public Access)

### 4.1 Start ngrok
1. Open a new Command Prompt
2. Run: `ngrok http 5678`
3. **Copy the HTTPS URL** (e.g., `https://abc123.ngrok-free.app`)

### 4.2 Set Up Telegram Webhook
1. Open your browser
2. Go to this URL (replace with your details):
   ```
   https://api.telegram.org/botYOUR_BOT_TOKEN_HERE/setWebhook?url=https://YOUR_NGROK_URL/webhook-test/telegram-webhook
   ```
3. You should see: `{"ok":true,"result":true,"description":"Webhook was set"}`

---

## Step 5: Test Your Bot

1. Open Telegram and find your bot
2. Send any message (e.g., "Hello")
3. You should receive the starter response message

---

## 🔧 Troubleshooting

### Bot doesn't respond?
- Check that the workflow is active in n8n
- Verify your bot token is correct
- Make sure ngrok is running
- Check n8n executions for errors

### 404 errors?
- Make sure n8n is running on port 5678
- Verify ngrok is forwarding to port 5678
- Check the webhook URL is correct

### Connection refused?
- Restart n8n: `n8n start`
- Restart ngrok: `ngrok http 5678`

---

## 📋 What You Get

This starter includes:
- ✅ Working Telegram bot setup
- ✅ Basic message handling
- ✅ Promotional response system
- ✅ Complete setup documentation

**What you DON'T get:**
- ❌ AI processing capabilities
- ❌ Ollama integration
- ❌ Intelligent responses
- ❌ Advanced features

---

## 🚀 Get the Full Version

For the complete AI-powered bot with:
- 🤖 **Real AI processing** with Ollama
- 🧠 **Intelligent responses** from local AI models
- 📚 **Complete setup guide** with troubleshooting
- 🎁 **Bonus extras** and advanced features

👉 **[Get the Full Version on Ko-fi ($10)](https://ko-fi.com/s/a3bb939baa)**

---

## 📬 Support & Community

- 🌐 **Website**: [mstimaj.com](https://mstimaj.com)
- 🐙 **GitHub**: [@mstimaj](https://github.com/mstimaj)
- 📺 **YouTube**: [@mstimaj](https://youtube.com/@mstimaj)
- 📱 **TikTok**: [@mstimaj](https://tiktok.com/@mstimaj)
- 📧 **Email**: [connect@mstimaj.com](mailto:connect@mstimaj.com)

---

## 📄 License

This starter version is licensed under the MIT License - feel free to use and modify!

---

## ⭐ Star This Repo

If this project helps you, please give it a star! It helps others discover the project and supports future development.

---

*Ready to build your own AI chatbot? Get the complete version and start chatting with your local AI today! 🚀* 