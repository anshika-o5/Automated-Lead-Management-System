# Automated Lead Management System

## Project Overview
An automated customer enquiry management system built using n8n. It collects customer enquiries through a web form, validates the submitted information, assigns lead scores, stores records in Google Sheets, and sends automated email notifications.

## Tech Stack
- **Frontend:** HTML, CSS, JavaScript
- **Automation:** n8n
- **Workflow Environment:** Docker, Ubuntu Linux
- **Database:** Google Sheets
- **Email Integration:** Gmail
- **Backend Integration:** Webhooks and HTTP requests

## Features

1. **Customer Enquiry Form** – Collects name, email, service requirements and budget.
2. **Input Validation** – Checks submitted information before processing.
3. **Lead Scoring** – Assigns scores based on customer budget:
   - Below $500: Low priority (20 points)
   - $500–$999: Medium priority (50 points)
   - $1,000 and above: High priority (80 points)
4. **Google Sheets Integration** – Automatically stores customer enquiries and lead scores.
5. **Automated Emails** – Sends confirmation emails to customers and notifications to the business.
6. **Spam Protection** – Uses a honeypot field to identify suspicious submissions.
7. **Error Handling** – Sends email alerts when workflow executions fail.

## Workflow Architecture

Customer Form → Webhook → Input Validation → Data Processing → Lead Scoring → Google Sheets → Email Notifications → Response

Invalid submissions are rejected through a separate response branch.

A separate Error Handler workflow monitors execution failures and sends notifications.

## Project Structure

- `Documentation/` – Project documentation and backups.
- `Frontend/` – Customer enquiry form.
- `n8n Workflow/` – Exported n8n workflow.

## Current Limitations

- The application currently runs locally.
- The computer and Docker environment must remain running for the automation to work.
- Public deployment and production hosting have not yet been configured.
- Lead scoring currently uses predefined budget-based rules.

## Future Improvements

- Public deployment with HTTPS.
- Rate limiting and additional security measures.
- Custom backend using Python and FastAPI.
- Database integration using SQLite or PostgreSQL.
- Machine-learning-based lead classification.
- CRM dashboard for lead tracking and management.

## Project Status

Core automation, frontend integration, lead scoring, email notifications, spam protection and error handling have been implemented and tested.