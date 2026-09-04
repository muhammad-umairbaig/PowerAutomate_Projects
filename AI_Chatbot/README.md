# Gemini AI Chatbot using Power Automate Desktop

A simple AI-powered chatbot built using **Microsoft Power Automate Desktop (PAD)** and the **Google Gemini API**.

This project demonstrates how Power Automate Desktop can interact with an external AI API, send user prompts to Gemini, process the JSON response, extract the generated text, and display the AI response to the user.

## 🚀 Project Overview

The chatbot allows users to enter a question or message through a Power Automate Desktop input dialog.

The workflow then:

1. Takes the user's input.
2. Sends the prompt to the Google Gemini API.
3. Receives the API response in JSON format.
4. Converts the JSON response into a custom object.
5. Extracts the generated text from the response.
6. Displays the AI-generated response to the user.

## 🛠️ Technologies Used

- **Power Automate Desktop**
- **Google Gemini API**
- **REST API / Web Service**
- **JSON**
- **Power Automate Desktop Variables**

## 🔄 Workflow

```text
User
  ↓
Enter Prompt
  ↓
Power Automate Desktop
  ↓
Gemini API
  ↓
JSON Response
  ↓
Convert JSON to Custom Object
  ↓
Extract Generated Text
  ↓
Display AI Response
