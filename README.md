# 🎟️ n8n Ticket Webhook API

This project contains an n8n workflow that simulates a backend API for handling ticket creation requests.

It validates incoming data, prevents duplicate tickets using Google Sheets, and returns proper HTTP status codes.

## 🚀 Features

- Webhook endpoint to receive ticket data
- Request validation (required fields check)
- Duplicate ticket detection using `ticket_id`
- Conditional logic using IF nodes
- Proper HTTP responses:
  - `400` → Invalid request
  - `409` → Duplicate ticket
  - `200` → Ticket successfully created
- Data persistence in Google Sheets

## 🧠 Workflow Logic

1. **Receive Ticket Webhook**
2. **Validate Request**
   - If invalid → Return 400
3. **Lookup Ticket by ID**
4. **Check if Duplicate**
   - If duplicate → Return 409
5. **Create Ticket in Sheet**
6. **Return Success (200)**

## 📦 Example Request

```json
{
  "ticket_id": "12345",
  "email": "user@example.com",
  "status": "open"
}

📤 Example Responses
❌ 400 – Invalid Request
{
  "success": false,
  "error": "Missing required fields"
}

❌ 409 – Duplicate Ticket
{
  "success": false,
  "error": "Duplicate ticket_id"
}

✅ 200 – Success
{
  "success": true,
  "message": "Ticket created successfully"
}
```

## 🛠 Tech Used

n8n (workflow automation)

Google Sheets

HTTP Webhooks

Conditional Logic (IF nodes)

## 🎯 Purpose

This project demonstrates:

API-like workflow design

Input validation

Business logic handling

Duplicate prevention strategy

Proper HTTP status code usage

## 📁 File

ticket-webhook-workflow.json → Exported n8n workflow file

## 🔮 Future Improvements

Stronger schema validation

Logging system

Migration to database (PostgreSQL)

Deployment using Docker

## 👩‍💻 Author

Ashley Arce – Automation & Backend Enthusiast
Email: ashleyarce171@gmail.com

Portfolio: https://github.com/asssarce

Built as part of my automation and backend learning journey 🚀
