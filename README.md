# Telegram-bot-and-lovable-n8n-bot-connection-

# Telegram Integration & Dr. Strange Appointment Scheduler

## Project Overview
This project implements an end-to-end automation using n8n and Lovable:
1. A Telegram-based interaction system using a Telegram Trigger.
2. A frontend appointment booking system for “Dr. Strange” built using Lovable, integrated with n8n via Webhook.

The workflow replaces the default Chat Trigger with a Telegram Trigger and processes appointment data submitted from the Lovable frontend.

---

## Tech Stack
- n8n (Workflow Automation)
- Telegram Bot API
- Lovable (Frontend Builder)
- Webhooks (HTTP POST)

---

## Task 1: Telegram Trigger Integration

### Description
- Replaced the Chat Trigger with a Telegram Trigger.
- Users can interact with the workflow via Telegram messages.
- Workflow responds back to the same Telegram chat.

### Setup
1. Create a Telegram bot using BotFather.
2. Copy the Bot Token.
3. Paste the token into the Telegram Trigger node:


---

## Task 2: Lovable Frontend + Webhook Integration

### Frontend (Lovable)
Project Name: **Dr Strange Appointment Scheduler**

Form Fields:
- Full Name (required)
- Phone Number (required)
- Email (required)
- Preferred Date (required)
- Preferred Time (optional)
- Reason for Visit (optional)

On submission, the form sends a POST request to the n8n webhook.

Webhook placeholder:


---

## n8n Webhook Logic

1. Receive form data via HTTP POST.
2. Validate required fields.
3. Generate an appointment ID and timestamp.
4. Respond to frontend with confirmation JSON.
5. Send appointment confirmation to Telegram (if Telegram ID is available).

---

## Sample Request (Lovable → n8n)

```json
{
  "full_name": "Jane Doe",
  "phone": "+919876543210",
  "email": "jane@example.com",
  "preferred_date": "2026-02-05",
  "preferred_time": "15:00",
  "reason_for_visit": "Consultation"
}

{
  "status": "ok",
  "appointment_id": "apt_20260201_1234",
  "message": "Appointment confirmed for Jane Doe on 2026-02-05 at 15:00"
}
