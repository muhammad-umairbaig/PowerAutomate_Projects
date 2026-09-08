AI-Powered Email Classification & Routing

An intelligent email automation solution built with Microsoft Power Automate Desktop (PAD), Microsoft Outlook / Office 365, Google Gemini API, and CSV-based training examples.

The automation reads unread emails, uses Gemini AI to classify each email into a predefined business category, and automatically moves the email to the corresponding Outlook folder.

🚀 Project Overview

Managing large numbers of incoming emails manually can be time-consuming and inconsistent.

This project automates the email classification process by combining RPA and Generative AI.

The workflow:

Fetches unread emails from the Outlook Inbox.

Reads example emails from a CSV training dataset.

Sends the current email subject and body to the Gemini API.

Uses the CSV examples as classification references.

Receives the AI classification.

Extracts the classification from the JSON response.

Automatically moves the email to the appropriate Outlook folder.

🛠️ Technologies Used

Microsoft Power Automate Desktop

Microsoft Outlook / Office 365

Google Gemini API

REST API

JSON

CSV

RPA (Robotic Process Automation)

Generative AI

📂 Email Categories

The automation classifies emails into one of the following categories:

Category

Purpose

HR

Human Resources related emails

Finance

Finance, payments, invoices, and accounting related emails

Operations

Operational and process-related emails

Marketing

Marketing and promotional business emails

Spam

Unwanted, suspicious, phishing, or junk emails

Unclassified

Emails that do not reasonably fit another category

🔄 Automation Workflow

                 Outlook Inbox
                       │
                       ▼
              Fetch Unread Emails
                       │
                       ▼
              Read CSV Dataset
                       │
                       ▼
              Get Email Subject
                       │
                       ▼
                Get Email Body
                       │
                       ▼
                Gemini AI API
                       │
                       ▼
             JSON Response
                       │
                       ▼
          Extract Classification
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
         HR         Finance     Operations
          │            │            │
          └────────────┼────────────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
      Marketing       Spam     Unclassified
          │            │            │
          └────────────┼────────────┘
                       ▼
              Move Email to Folder

⚙️ Power Automate Desktop Process

1. Get Unread Emails

Power Automate Desktop connects to the Office 365 mailbox and retrieves unread emails from the Inbox.

The workflow processes the email information including:

Email Subject

Email Body Preview

Email ID

2. Load Training Dataset

A CSV file containing example emails is loaded into a DataTable.

These examples are provided to Gemini as references to help it understand the expected classification patterns.

3. Prepare AI Prompt

The automation creates a structured prompt containing:

Classification instructions

Available categories

Classification rules

Example emails from the CSV

Current email subject

Current email body

Gemini is instructed to return only one category.

4. Send Request to Gemini

The prompt is sent to the Google Gemini API through the Invoke Web Service action in Power Automate Desktop.

The API returns a JSON response.

5. Parse JSON Response

The Gemini response is converted into a Power Automate Desktop Custom Object.

The generated classification is extracted from the response.

Example response path:

GeminiObj['candidates'][0]['content']['parts'][0]['text']

6. Route the Email

Based on the returned classification, Power Automate Desktop moves the email into the corresponding Outlook folder.

For example:

HR           → HR folder
Finance      → Finance folder
Operations   → Operations folder
Marketing    → Marketing folder
Spam         → Spam folder
Unclassified → Unclassified folder

✨ Key Features

Automated unread email processing

AI-powered email classification

Gemini API integration

CSV-based classification examples

Six predefined email categories

Automatic Outlook folder routing

JSON response handling

Power Automate Desktop RPA workflow

Reduced manual email sorting

Scalable approach for business email management

📊 Example

Incoming Email

Subject:

Annual Leave Policy Update

Body:

Please review the updated annual leave policy
and the changes effective from next month.

AI Classification

HR

Result

The email is automatically moved from:

Inbox

to:

HR
