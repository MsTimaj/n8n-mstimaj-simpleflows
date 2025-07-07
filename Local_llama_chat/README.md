# Local Llama Chat - N8N Workflow

🤖 A fast, local AI chat workflow using Ollama and Llama models in N8N. This workflow creates a webhook endpoint that allows you to chat with local AI models without sending data to external services.

## 🚀 What This Workflow Does

This workflow creates a **chat interface** that:
- **Receives messages** via webhook (perfect for integrations)
- **Processes conversations** using local Llama models via Ollama
- **Maintains conversation memory** so the AI remembers context
- **Returns AI responses** quickly and privately
- **Works completely offline** - no internet required after setup

## 🎯 Use Cases

- **Private AI Assistant** - Keep conversations local and secure
- **Integration Hub** - Connect to other apps via webhook
- **Content Creation** - Generate ideas, write drafts, brainstorm
- **Learning Tool** - Ask questions, get explanations
- **Development Helper** - Code assistance, debugging help

## ⚙️ Prerequisites

1. **N8N Instance** (cloud or self-hosted)
2. **Ollama** installed on your machine/server
3. **Llama Model** downloaded (recommended: `llama3.2:3b`)

## 📋 Setup Instructions

### Step 1: Install Ollama
```bash
# Download and install Ollama from https://ollama.ai
# Or use the installer for your OS
```

### Step 2: Download a Llama Model
```bash
# Pull the recommended fast model
ollama pull llama3.2:3b

# Alternative models (choose based on your hardware):
# ollama pull llama3.2:1b    # Fastest, lowest quality
# ollama pull llama3.2:7b    # Slower, higher quality
# ollama pull llama3.1:3b    # Stable version
```

### Step 3: Import the Workflow
1. **Download** the `Local_Llama_Chat.json` file from this repository
2. **Open your N8N instance**
3. **Go to Workflows** → **Import from File**
4. **Select** the downloaded JSON file
5. **Click Import**

### Step 4: Configure Ollama Credentials
1. **Click on the "Ollama Chat Model (Fast)" node**
2. **Click "Add Credential"**
3. **Select "Ollama API"**
4. **Configure:**
   - **Name**: `Ollama Local` (or any name you prefer)
   - **Base URL**: `http://localhost:11434` (default Ollama URL)
   - **API Key**: Leave empty (not required for local Ollama)
5. **Click "Save"**

### Step 5: Test the Workflow
1. **Click "Execute Workflow"** to test
2. **Check the webhook URL** in the "When chat message received" node
3. **Copy the webhook URL** for external access

## 🔧 How to Use

### Method 1: Direct Webhook Calls
```bash
curl -X POST "YOUR_WEBHOOK_URL" \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello, how are you today?"}'
```

### Method 2: N8N Chat Interface
1. **Activate the workflow**
2. **Use the built-in chat interface** in N8N
3. **Send messages** and get AI responses

### Method 3: Integrate with Other Apps
- **Slack** - Connect via webhook
- **Discord** - Bot integration
- **Website** - JavaScript fetch calls
- **Mobile App** - API integration

## ⚡ Performance Optimization

### Fast Model Settings (Already Configured)
- **Model**: `llama3.2:3b` (balanced speed/quality)
- **Temperature**: 0.7 (creative but focused)
- **Top-p**: 0.9 (faster sampling)
- **Num Predict**: 100 (shorter responses)
- **Top-k**: 40 (efficient token selection)

### Hardware Tips
- **GPU**: Use if available for faster processing
- **RAM**: 8GB+ recommended for 3B models
- **Cooling**: Ensure good ventilation for sustained use
- **Background Apps**: Close unnecessary applications

## 🔍 Troubleshooting

### Common Issues

**"Connection refused" error:**
- Ensure Ollama is running: `ollama serve`
- Check if port 11434 is accessible
- Verify firewall settings

**Slow responses:**
- Try a smaller model: `ollama pull llama3.2:1b`
- Close other applications
- Check system resources

**Memory issues:**
- Reduce model size
- Restart Ollama: `ollama stop && ollama serve`
- Check available RAM

**Webhook not working:**
- Ensure workflow is activated
- Check webhook URL is correct
- Verify N8N instance is accessible

## 🛠️ Customization

### Change the Model
1. **Pull a different model**: `ollama pull llama3.2:7b`
2. **Update the workflow**: Change model name in "Ollama Chat Model" node
3. **Adjust parameters** for your needs

### Modify Response Length
- **Shorter responses**: Reduce "Num Predict" to 50-75
- **Longer responses**: Increase "Num Predict" to 200-300

### Add System Prompts
- **Edit the Agent node** to add custom instructions
- **Modify behavior** for specific use cases

## 🔒 Security & Privacy

✅ **Complete Privacy** - All processing happens locally
✅ **No Data Leakage** - No external API calls
✅ **Offline Capable** - Works without internet
✅ **Customizable** - Full control over the AI

## 📞 Support

- **Issues**: Create a GitHub issue
- **Questions**: Check the N8N community
- **Ollama Help**: Visit [ollama.ai](https://ollama.ai)

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

**Created by**: [mstimaj](https://github.com/mstimaj)  
**Part of**: N8N Simple Flows Collection  
**Signature**: forward ▸ upward ▸ onward 