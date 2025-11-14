## 🚀 Gmail Auto-Reply Draft Generator Using n8n + OpenAI Assistant

This workflow automates email reply drafting inside Gmail using n8n, OpenAI Assistants, and the Gmail API.
Whenever a Gmail thread contains a specific label (your "trigger label"), the workflow grabs the latest message, sends it to OpenAI for drafting a reply, converts the response into HTML, builds a valid Gmail raw email, and finally inserts the reply draft back into the same thread.

---


### 📌 Features

⏱ Automated Trigger Every 1 Minute
Checks Gmail threads periodically for a chosen label.


## 📥 Fetches Threads With Specific Labels
Only processes threads that match your trigger label(s).


## 🧵 Extracts the Last Email in the Thread
Retrieves the clean message body, subject, and sender.


## 🤖 Creates Reply Draft With OpenAI Assistant
Uses your configured Assistant to generate a professional email reply.


## 📝 Converts AI Markdown → HTML
Ensures the email is formatted correctly for Gmail.


## 📧 Builds RFC-Compliant Raw Gmail Message
Constructs the full email with headers + HTML body.


## 🔐 Encodes Message in Base64
Required by Gmail’s email creation API.


## 📬 Inserts Draft Back Into Gmail Thread
The final draft appears inside Gmail as if manually created.


## 🏷 Removes Trigger Label Automatically
Prevents reprocessing and keeps your inbox clean.


## 🧭 Workflow Overview
1. Schedule Trigger

Runs every minute to check for threads containing trigger labels.

2. Get Threads With Labels

Searches Gmail for threads marked with your AI-processing label.

3. Loop Through Threads

Processes each thread one by one.

4. Get Last Message in Thread

Extracts the most recent incoming message for reply generation.

5. OpenAI Assistant Drafts Reply

Sends email content to your configured Assistant.

6. Convert Markdown to HTML

Ensures Gmail receives clean HTML content.

---

## 🛠 Tech Stack

Component	Purpose

n8n	Workflow automation and orchestration

Gmail API	Retrieve emails, insert drafts, and manage labels

OpenAI Assistant API	Generate intelligent, context-aware email replies

JavaScript Code Node	Base64 encoding and dynamic field handling

Markdown → HTML Converter Node	Makes OpenAI responses email-friendly

HTTP Request Node	Sends Gmail drafts.create API call

---

## 📌 Prerequisites

You must configure:

Gmail OAuth2 credentials (GCP)

OpenAI Assistant ID

Gmail label to monitor (e.g., AI_Reply, autodraft)

Permissions for drafts and labels in Gmail API
