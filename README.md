WhatsApp AI Bot n8n Workflow

This repository provides a fully automated n8n workflow for handling WhatsApp messages via the WhatsApp Cloud API.
Supports text, voice, image, and document messages with AI-powered responses using OpenAI GPT models.

Features

Receive WhatsApp messages (text, voice, image, document)

Transcribe voice messages to text automatically

Analyze images and generate descriptive context

Generate AI-powered responses via OpenAI GPT models

Optional voice replies to user messages

Maintain conversation context using a memory buffer

Prerequisites

WhatsApp Business Account

n8n instance (self-hosted or cloud)

OpenAI API Key

Setup Instructions
1. WhatsApp Cloud API

Create a Facebook Developer App

Go to WhatsApp > Getting Started and configure your WhatsApp Business Account

Obtain the following credentials:

Credential	Description
Client ID	WhatsApp App Client ID
Client Secret	WhatsApp App Client Secret
Phone Number ID	WhatsApp Business Phone Number ID
Access Token	WhatsApp Access Token

Security Note: Keep credentials secure. Do not commit them to version control.

2. n8n Workflow

Import whatsapp-n8n-workflow.json into your n8n instance

Update workflow nodes with credentials:

Node	Required Field
WhatsApp Trigger	Webhook ID (unique)
Send Message (WhatsApp node)	Phone Number ID
HTTP Request / Media Nodes	Authentication → Bearer Access Token
OpenAI Nodes (Text/Voice/Image)	API Key
3. Environment Variables (Recommended)
WHATSAPP_CLIENT_ID=your_client_id
WHATSAPP_CLIENT_SECRET=your_client_secret
WHATSAPP_PHONE_NUMBER_ID=your_phone_number_id
WHATSAPP_ACCESS_TOKEN=your_access_token
OPENAI_API_KEY=your_openai_api_key

4. Running the Bot

Start your n8n instance

The WhatsApp Trigger node listens for incoming messages

Messages are routed based on type (text, voice, image, document)

Responses (text or voice) are sent automatically

5. Notes

Voice messages are transcribed to text before AI processing

Images are analyzed using OpenAI vision models

Context-aware responses are enabled via a memory buffer

Customize bot personality via the AI Response Engine system prompt

6. Contributing

Fork the repository

Implement improvements or fixes

Submit a pull request with a clear description of changes
