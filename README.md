# ⚡ LeadFlow – Automated Client Request Management

## 📌 Project Overview

**LeadFlow** is an automation system built with **n8n** that manages incoming client requests from a form, prioritizes leads based on budget, stores them in a CRM (Airtable), and automatically handles notifications, follow-ups, and reply detection.

The system helps agencies **capture leads, track communication, and ensure no potential client is missed.**

---

# 🚀 Key Features

- Automatic client request intake from an online form
- Lead prioritization based on client budget
- Automatic CRM storage
- Email confirmation to clients
- Team alerts for new leads
- Automatic follow-up emails
- Reply detection and status update

---

# 🧩 System Architecture

The automation system is composed of **two main workflows**:

1️⃣ **Client Request Intake & Auto-Triage**  
2️⃣ **Reply Detection & Status Update**

---

# 📥 Workflow 1 – Client Request Intake & Auto-Triage

This workflow automatically processes new client requests submitted through a form.

### Process

1. **Client submits a form**
   - Form created with **Tally**
   - Client provides:
     - Name
     - Email
     - Phone
     - Requested service
     - Budget

2. **Data Processing**
   - Form data is cleaned and structured
   - Submission date is automatically generated

3. **Lead Prioritization**
   - If budget **> $2000 → Priority Lead**
   - Otherwise → Standard Lead

4. **CRM Storage**
   - Client information is stored in **Airtable**
   - Status is set to **Pending**

5. **Automatic Notifications**
   - Client receives a confirmation email
   - The team receives an alert email

6. **Follow-up Automation**
   - The system waits **48 hours**
   - If the client has not replied:
     - A follow-up email is sent automatically

7. **Status Update**
   - The system updates the CRM record to track communication.

---

# 📬 Workflow 2 – Reply Detection

This workflow detects when a client replies to an email.

### Process

1. **Monitor Gmail inbox**
   - The system checks for **new unread replies**

2. **Extract Client Email**
   - The sender email is parsed automatically

3. **Search CRM**
   - Airtable is queried to find the matching client

4. **Update Status**
   - Client status is updated to **Contacted**

5. **Team Notification**
   - The team receives an alert:
