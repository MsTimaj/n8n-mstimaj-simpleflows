# Inspo Emailer

📨 Sends a daily inspirational quote to your inbox using a schedule trigger, a quote API, and email automation via N8N.

---

## 🔧 How It Works

1. **Schedule Trigger**: Runs every day at 9:00 AM.
2. **HTTP Request Node**: Pulls a random quote from [ZenQuotes API](https://zenquotes.io).
3. **(Optional) Set Node**: Extracts and flattens the quote and author from the API response.
4. **Send Email Node**: Sends the formatted quote to your email inbox.

---

## 🧪 Setup Instructions

1. **Import the Workflow**
   - Download the `workflow.json` file
   - In n8n, click "Import from File" and select the downloaded file

2. **Configure Email Settings**
   - 🔐 Add your own Gmail OAuth2 credentials:
     1. Click on the Gmail node
     2. Click "Add Credential"
     3. Select "Gmail OAuth2"
     4. Follow the authentication steps
   - ✉️ Replace `your-email@example.com` with your actual email address

3. **Customize the Schedule**
   - Click on the Schedule Trigger node
   - Adjust the time to your preferred schedule
   - You can also change the frequency (daily, weekly, etc.)

4. **Test the Workflow**
   - Click "Execute Workflow" to test
   - Check your email for the test message
   - The message should look like this:
     ```
     "Your quote will appear here"
     – Author Name
     ```

5. **Activate the Workflow**
   - Once everything is working, click "Activate" to enable the schedule

---

## 🔍 Troubleshooting

- **Email Not Sending**: Check your Gmail OAuth2 credentials
- **Wrong Quote Format**: Verify the HTTP Request node is returning the expected JSON structure
- **Schedule Not Working**: Ensure the workflow is activated and the schedule is set correctly

---

## 📝 Notes

- The ZenQuotes API is free and doesn't require authentication
- Gmail OAuth2 credentials are required for sending emails
- You can customize the email subject and message format in the Gmail node

---

## 🤝 Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements you'd like to suggest.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details. 