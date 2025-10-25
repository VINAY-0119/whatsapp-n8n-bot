#WhatsApp AI Bot n8n Workflow

This repository contains an n8n workflow for handling WhatsApp messages via the WhatsApp Cloud API.
Supports text, voice, image, and document messages, with AI-powered responses using OpenAI GPT models.

Features

Receive WhatsApp messages (text, voice, image, document)

Convert voice messages to text

Analyze images and generate descriptive context

AI-powered responses using OpenAI GPT models

Optional voice replies

Maintain conversation context with a memory buffer

Setup Instructions
1. WhatsApp Cloud API

Create a Facebook Developer App

Go to WhatsApp > Getting Started and set up your WhatsApp Business Account

Obtain credentials:

Credential	Description
Client ID	Your WhatsApp App Client ID
Client Secret	Your WhatsApp App Client Secret
Phone Number ID	Your WhatsApp Business Phone Number ID
Access Token	Your WhatsApp Access Token

Keep credentials secure. Do not commit them to GitHub.

2. n8n Workflow

Import whatsapp-n8n-workflow.json into n8n

Update nodes with your credentials:

Node	Field
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

WhatsApp Trigger node listens for incoming messages

Messages are routed by type (text, voice, image, document)

Responses (text or voice) are sent automatically

5. Notes

Voice messages are converted to text before AI processing

Images are analyzed using OpenAI vision models

Memory buffer allows context-aware responses

Customize bot personality via the AI Response Engine node

6. Contributing

Fork the repository

Make improvements or fixes

Submit a pull request with a clear description
