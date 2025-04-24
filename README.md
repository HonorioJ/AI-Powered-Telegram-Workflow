
# 🤖 AI-Powered Telegram Bot Workflow for Video Summarization using n8n
An AI-powered automation workflow triggered via Telegram that:  Scrapes and summarizes blog content using OpenRouter  Converts the summary to a realistic avatar video using HeyGen (for both voice and avatar)   Publishes the generated video to YouTube

🚀 This project is a fully automated and production-ready **n8n workflow** that transforms blog/article links into **AI-generated avatar videos**, triggered directly from **Telegram**.

![Workflow Screenshot](https://github.com/urstruly-bunny/AI-Powered-Telegram-Workflow/blob/main/WORKFLOW%20IMAGE.png)

---

## 🧠 Overview

This workflow showcases a real-world application of AI and automation using **n8n**, ideal for tech content creators or media companies looking to scale their video generation efforts.

### ✨ Key Features

- 📩 **Triggered via Telegram**  
  Users send a message containing a **subject topic** and blog/article **URLs** (e.g., from `https://www.vastdata.com/blog`).

- 🔄 **Smart Parsing & Scraping**  
  A `Function` node parses the message, and an `HTTP Request (GET)` + `HTML Extract` node scrapes article content.

- 🤖 **AI Summarization with OpenRouter**  
  The scraped content is summarized using a **Basic LLM Chain** powered by **OpenRouter's Mistral model**.

- 🎤 **AI Video Generation with HeyGen**  
  The summary is converted into an avatar-based video using **HeyGen**, leveraging:
  - ✅ Voice ID
  - ✅ Avatar ID
  - ✅ API Key via `Manual Input` → `HTTP POST` → `HTTP GET`

- 📤 **Upload to YouTube**  
  Final video is uploaded using the `YouTube` node, authenticated via **OAuth2** (Client ID + Secret required).

---

## 🛠️ How to Run Locally

Follow these steps to deploy the workflow on your local system:

1. ⬇️ **Download the Workflow**  
   - Grab the `.json` file from this repository.

2. 🐳 **Run n8n with Docker**  
   Use Docker to host n8n locally.

3. 🌐 **Expose Webhook with Ngrok**  
   - Set up an HTTPS webhook using [Ngrok](https://ngrok.com/) to allow Telegram to reach your local instance.

4. 🔐 **Prepare Your API Credentials**  
   You'll need the following keys:
   - `OpenRouter API Key`
   - `HeyGen API Key`
   - `Voice ID` & `Avatar ID`
   - `YouTube OAuth2` credentials (Client ID & Secret)

5. 🧩 **Update Nodes in Workflow**  
   Paste your credentials into the appropriate nodes:
   - Telegram
   - HTTP Request
   - HeyGen (Manual Node)
   - YouTube

---
## 🧩 Tech Stack

- **n8n** – Automation platform
- **Telegram Bot** – User trigger
- **OpenRouter** – AI summarization (Mistral model)
- **HeyGen** – AI avatar video generation
- **YouTube API** – Video publishing

## 💡 Example Use Case

Send a message to your Telegram bot like:
Subject: Recent Software changes
Link: https://www.vastdata.com/blog
🎬 The bot will scrape the article, summarize it with AI, generate an avatar video with narration, and upload it to your YouTube channel — fully automated.

A DEMO VIDEO IS

