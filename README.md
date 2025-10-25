# WhatsApp AI Bot n8n Workflow

This repository contains an **n8n workflow** for handling WhatsApp messages via the **WhatsApp Cloud API**.  
It supports **text, voice, image, and document messages**, with AI-powered responses using **OpenAI**.

---

## Features

- Receive WhatsApp messages (text, voice, image, document).  
- Convert voice messages to text.  
- Analyze images and generate descriptive context.  
- AI-powered responses using OpenAI GPT models.  
- Optional voice replies to user messages.  
- Maintain conversation context with memory buffer.  

---

## Setup Instructions

### 1. WhatsApp Cloud API

1. Create a [Facebook Developer App](https://developers.facebook.com/).  
2. Go to **WhatsApp > Getting Started** and set up your **WhatsApp Business Account**.  
3. Obtain these credentials:

| Credential        | Description                           |
|------------------|---------------------------------------|
| Client ID         | YOUR_WHATSAPP_CLIENT_ID               |
| Client Secret     | YOUR_WHATSAPP_CLIENT_SECRET           |
| Phone Number ID   | YOUR_WHATSAPP_PHONE_NUMBER_ID         |
| Access Token      | YOUR_WHATSAPP_ACCESS_TOKEN            |

> **Keep credentials secure**. Do not commit them to GitHub.

---

### 2. n8n Workflow

1. Import the workflow JSON (`whatsapp-n8n-workflow.json`) into n8n.  
2. Update nodes with your credentials:

| Node                         | Field                                  |
|-------------------------------|---------------------------------------|
| WhatsApp Trigger              | Webhook ID (unique)                    |
| Send Message (WhatsApp node)  | Phone Number ID                        |
| HTTP Request / Media Nodes    | Authentication → Bearer Access Token  |
| OpenAI Nodes (Text/Voice/Image) | API Key                               |

---

### 3. Environment Variables (Optional but Recommended)

```bash
WHATSAPP_CLIENT_ID=YOUR_WHATSAPP_CLIENT_ID
WHATSAPP_CLIENT_SECRET=YOUR_WHATSAPP_CLIENT_SECRET
WHATSAPP_PHONE_NUMBER_ID=YOUR_WHATSAPP_PHONE_NUMBER_ID
WHATSAPP_ACCESS_TOKEN=YOUR_WHATSAPP_ACCESS_TOKEN
OPENAI_API_KEY=YOUR_OPENAI_API_KEY








4. Running the Bot

Start your n8n instance.

The WhatsApp Trigger node listens for incoming messages.

Messages are routed and processed by type (text, voice, image, document).

Responses (text or voice) are sent automatically.

5. Notes

Voice messages are converted to text before AI processing.

Images are analyzed using OpenAI Vision models.

Memory buffer allows context-aware responses.

Customize bot personality via the AI Response Engine node system prompt.

6. Contributing

Fork the repository.

Make improvements.

Submit a pull request with a clear description of changes.
