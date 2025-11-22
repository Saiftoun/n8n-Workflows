# 🤖 n8n AI Agent Telegram Bot: The Ultimate AI Productivity Assistant

!(https://i.imgur.com/example-workflow-diagram.png)

An **Intelligent Telegram chatbot** powered by an **AI Agent**, the **Groq LLM**, and seamless integrations with Google services.

---

## 📖 Overview

This project implements a sophisticated **n8n workflow** that creates an **AI-powered Telegram bot** capable of handling complex, conversational tasks.

Triggered by incoming Telegram messages, the bot uses **Groq's high-performance chat model** to process queries, retain context via memory, and perform external actions like scheduling events, querying spreadsheets, and sending emails. Responses are intelligently routed and sent back directly to the user via Telegram, making this workflow an ideal solution for **personal assistants**, **productivity tools**, or **automated support systems**.

---

## ✨ Features

| Category | Feature | Description |
| :--- | :--- | :--- |
| **Messaging** | 🔄 **Telegram Integration** | Triggers on incoming messages for real-time, interactive conversations. |
| **Intelligence** | 🧠 **AI-Powered Agent** | Uses the **Groq Chat Model** for rapid, natural language understanding and decision-making. |
| **Memory** | 💾 **Context Memory** | Utilizes **Simple Memory** (backed by a database) for conversation persistence and context retention. |
| **Automation** | 💬 **Tool Actions** | Executes tasks like creating Google Calendar events, reading Google Sheets data, and sending Gmail messages. |
| **Reliability** | 🔍 **Output Parsing** | Ensures reliable handling and formatting of tool results for accurate, human-readable responses. |
| **Scalability** | 📄 **Extensible Design** | Easily add more custom tools, LLMs, or integrations within the n8n environment. |

---

## 🏗️ Architecture & Workflow Components

This workflow is structured around the **n8n AI Agent** design pattern:

| Component | Role | Connected Nodes |
| :--- | :--- | :--- |
|  |
| **Telegram Trigger** | Captures incoming messages and initiates the process. | Telegram Trigger |
| **AI Agent** | The central orchestrator that processes inputs, maintains memory, and decides which tool to call. | AI Agent |
| **Groq Chat Model** | Provides the powerful LLM reasoning core for the Agent. | Groq Chat Model |
| **Simple Memory** | Stores and retrieves conversation history for multi-turn chats. | Simple Memory |
| **ToolOutput Parser** | Standardizes and formats outputs from tools before they return to the Agent. | ToolOutput Parser |
| **Integrated Tools** | | |
| **Google Calendar** | Handles requests to add, modify, or query events. | Create Event in Google Calendar |
| **Google Sheets** | Handles requests to read specific data from spreadsheets. | Get Row(s) in Google Sheets |
| **Gmail** | Handles requests to send notifications or messages. | Send Message in Gmail |
| **Telegram Sender** | Returns the final, processed response back to the user. | Send Text Message (Telegram) |

---

## 🚀 Getting Started

### Prerequisites

You must have accounts and API keys for the following services:

* **Telegram Bot token** (created via BotFather).
* **Groq API key** (sign up at [groq.com](https://groq.com)).
* **Google OAuth2 credentials** (with scopes for Calendar, Sheets, and Gmail).
* **A Hosting Environment** for n8n (e.g., Render, Railway, or a self-hosted Docker instance).
* **A Database** (PostgreSQL recommended for persistent Simple Memory).

### Installation

1.  **Import the Workflow:**
    * Download or create `ai-agent-telegram-workflow.json` based on the diagram.
    * In your n8n instance: Click **"Add workflow"** → **"Import from File"**.
2.  **Configure Credentials:**
    * Go to **Settings** → **Credentials** in n8n.
    * Add and configure the required credentials: `Telegram Bot API`, `Groq API`, and `Google OAuth2`. **(Ensure you include the necessary scopes: `calendar`, `spreadsheets`, and `gmail.send`)**

### Quick Start (Deployment on Render Example)

1.  **Configure Database for Memory:**
    * Use **Render** or your preferred provider to create a **PostgreSQL** database service.
    * Configure the **Simple Memory** node with your database connection details (e.g., set environment variables like `DB_TYPE=postgresdb`, `host`, `database`, `user`, and `password`).
2.  **Deploy n8n on Render:**
    * In the Render dashboard: **New → Web Service → Docker**.
    * Use the official n8n image: `n8nio/n8n`.
    * Set necessary **environment variables** (e.g., basic authentication, webhook URL, and database credentials).
3.  **Activate the Workflow:**
    * Save all node configurations.
    * Click the **"Active"** toggle in the n8n editor to enable the bot.

---

## 💡 Usage

Interact with your Telegram bot using natural language. The AI Agent will decide whether to respond conversationally or execute a tool-based task.

| Category | Example Queries | Agent Action |
| :--- | :--- | :--- |
| **Scheduling** | `"Schedule a team sync for tomorrow at 3 PM about project updates"` | Executes **Google Calendar** tool. |
| **Data Retrieval** | `"What's in row 5 of my budget spreadsheet?"` | Executes **Google Sheets** tool. |
| **Communication** | `"Send an email to team@example.com with subject 'Weekly Report' and body 'It's attached.'"` | Executes **Gmail** tool. |
| **Conversational** | `"What is the capital of France and how are you today?"` | **Groq Chat Model** responds conversationally without tool use. |

---

## 🛠️ Tech Stack

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Workflow Engine** | n8n (Docker on Render) | Low-Code Automation & Orchestration |
| **Chat Model** | Groq LLM | High-Speed AI Reasoning |
| **Memory Storage** | PostgreSQL / Simple Memory | Conversation Context Persistence |
| **Messaging** | Telegram API | Real-Time User Interface |
| **Integrations** | Google APIs | External Action Execution |

---

## 🤝 Contributing & Contact

Contributions are welcome! Feel free to:

* Report bugs and suggest new features by **opening an Issue** on GitHub.
* Submit pull requests to improve code or documentation.

📧 **Contact:** For questions or feedback, please open an issue on the repository.

---
*Built with ❤️ using n8n, Groq AI, and Render hosting.*
*License: MIT License (see the `LICENSE` file for details).*
