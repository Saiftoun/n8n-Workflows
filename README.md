
n8n AI Agent Telegram Bot 🤖
Intelligent Telegram chatbot powered by AI agent, Groq LLM, and seamless integrations with Google services

📖 Overview
An n8n workflow that creates an AI-powered Telegram bot capable of handling conversational tasks. Triggered by Telegram messages, the bot uses Groq's high-performance chat model to process queries, retain context via memory, and perform actions like scheduling events, querying spreadsheets, and sending emails. Responses are sent back via Telegram, making it ideal for personal assistants, productivity tools, or automated support systems.

✨ Features
🔄 Telegram Integration - Triggers on incoming messages for real-time interactions
🧠 AI-Powered Agent - Uses Groq Chat Model for natural language understanding and generation
💾 Context Memory - Simple database-backed memory for conversation persistence
💬 Tool Actions - Executes tasks like creating calendar events, reading Google Sheets, and sending Gmail
🔍 Output Parsing - Ensures reliable handling of tool results for accurate responses
📄 Extensible Design - Easily add more tools or integrations in n8n
🏗️ Architecture
Workflow Components
Main Pipeline:

Telegram Trigger → Captures incoming messages and updates
AI Agent → Central orchestrator that processes inputs and decides on actions
Groq Chat Model → Generates intelligent responses using Groq's LLM
Simple Memory → Stores and retrieves conversation context from a database
ToolOutput Parser → Formats outputs from tools for the agent
Integrated Tools:
Create Event in Google Calendar → Adds events based on user requests
Get Row(s) in Google Sheets → Retrieves data from specified sheets
Send Message in Gmail → Sends emails for notifications
Send Text Message (Telegram) → Returns responses to the user
🚀 Getting Started
Prerequisites
Telegram Bot token (create via BotFather)
Groq API key (sign up at groq.com)
Google OAuth2 credentials (for Calendar, Sheets, and Gmail)
Render account for hosting (free tier available)
Installation
Import the Workflow:
Download or create ai-agent-telegram-workflow.json based on the diagram
In n8n: Click "Add workflow" → "Import from File"
Select the JSON file or recreate nodes manually
Configure Credentials:
Go to Settings → Credentials
Add the following credentials:
Telegram Bot API
Groq API
Google OAuth2 (scopes: calendar, spreadsheets, gmail.send)
Quick Start
Set up Telegram Bot:
Create a bot via BotFather and get the token
Configure the Telegram Trigger node with the token
Configure Database for Memory:
Use Render to create a PostgreSQL database
Enable necessary extensions if needed
Add connection details to the Simple Memory node (e.g., DB_TYPE=postgresdb, host, etc.)
Set up Groq and Google Integrations:
Add Groq API key to the Groq Chat Model node
Configure Google tool nodes with OAuth credentials
Deploy on Render:
In Render dashboard: New → Web Service → Docker
Use official n8n image: n8nio/n8n
Set environment variables (e.g., N8N_BASIC_AUTH_ACTIVE=true, database creds)
Add persistent disk for /home/node/.n8n
Attach PostgreSQL database service
Deploy and access at your Render URL (e.g., https://your-service.onrender.com)
Activate the Workflow:
Save all node configurations
Click "Active" toggle to enable
💡 Usage
Interacting with the Bot
Message your Telegram bot with natural language queries
The AI agent processes the request, using tools as needed
Receive responses directly in Telegram
Example Queries
text
"Schedule a meeting for tomorrow at 3 PM about project updates"
"What's in row 5 of my budget spreadsheet?"
"Send an email to team@example.com with subject 'Weekly Report'"
"Tell me about my calendar events for next week"
🛠️ Tech Stack
Component	Technology
Workflow Engine	n8n (Docker on Render)
Chat Model	Groq LLM
Memory Storage	Simple Database (PostgreSQL on Render)
Messaging	Telegram API
Integrations	Google Calendar, Sheets, Gmail
Output Handling	ToolOutput Parser
AI Orchestration	n8n AI Agent
🤝 Contributing
Contributions are welcome! Feel free to:

Report bugs
Suggest new features
Submit pull requests
Improve documentation
📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

📧 Contact
For questions or feedback, please open an issue on GitHub.

Built with ❤️ using n8n, Groq AI, and Render hosting
