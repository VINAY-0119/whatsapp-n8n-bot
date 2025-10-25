WhatsApp n8n Bot Workflow

This repository contains an n8n workflow for handling WhatsApp messages via the WhatsApp Cloud API. The bot supports text, voice, image, and document messages, with AI responses powered by OpenAI.

Features

Receives WhatsApp messages (text, voice, image, document).

Converts voice messages to text.

Analyzes images and generates descriptive context.

AI-powered responses using OpenAI (GPT models).

Optional voice replies to user messages.

Maintains conversation context with memory buffer.

Setup Instructions
1. WhatsApp Cloud API

Create a Facebook Developer App
.

Go to WhatsApp > Getting Started and set up your WhatsApp Business Account.

Obtain the following credentials:

Client ID → YOUR_WHATSAPP_CLIENT_ID

Client Secret → YOUR_WHATSAPP_CLIENT_SECRET

Phone Number ID → YOUR_WHATSAPP_PHONE_NUMBER_ID

Access Token → YOUR_WHATSAPP_ACCESS_TOKEN

⚠️ Store these securely. Never commit secrets to GitHub.

2. n8n Workflow

Import the workflow JSON (whatsapp-n8n-workflow.json) into n8n.

Update these nodes with your credentials:

WhatsApp Trigger: Set Webhook ID (unique).

WhatsApp Send nodes: Add your Phone Number ID.

HTTP Request / Media Nodes: Use your Access Token.

OpenAI Nodes: Set your OpenAI API key (YOUR_OPENAI_API_KEY).

3. Environment Variables (Optional but Recommended)

Store sensitive information in n8n using environment variables:

WHATSAPP_CLIENT_ID=YOUR_WHATSAPP_CLIENT_ID
WHATSAPP_CLIENT_SECRET=YOUR_WHATSAPP_CLIENT_SECRET
WHATSAPP_PHONE_NUMBER_ID=YOUR_WHATSAPP_PHONE_NUMBER_ID
WHATSAPP_ACCESS_TOKEN=YOUR_WHATSAPP_ACCESS_TOKEN
OPENAI_API_KEY=YOUR_OPENAI_API_KEY

4. Running the Bot

Ensure your n8n instance is running.

The WhatsApp Trigger node will listen for incoming messages.

Messages are routed and processed by type (text, voice, image, document).

Responses (text or voice) are sent automatically.

5. Notes

Voice messages are converted to text before AI processing.

Images are analyzed using OpenAI Vision models.

Memory buffer allows context-aware responses.

Customize the bot personality via the AI Response Engine node system prompt.

6. Example Node Placeholders
Node	Placeholder Fields
WhatsApp Trigger	Webhook ID: YOUR_UNIQUE_WEBHOOK_ID
Send Message	Phone Number ID: YOUR_WHATSAPP_PHONE_NUMBER_ID
HTTP Request / Download Media	Authentication: Bearer YOUR_WHATSAPP_ACCESS_TOKEN
OpenAI (Text/Voice/Image)	API Key: YOUR_OPENAI_API_KEY
7. Contributing

Fork the repository.

Make improvements.

Submit a pull request with description.

8. License

This project is licensed under the MIT License.
