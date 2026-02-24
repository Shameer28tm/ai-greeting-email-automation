AI Greeting Email Automation (n8n Workflow)
Overview

This project is an AI-powered email automation workflow built using n8n.
It reads recipient data from Google Sheets, generates personalized greeting messages using an AI model, sends emails via Gmail, and updates delivery status back to the spreadsheet.

The goal is to automate personalized communication while maintaining controlled sending intervals and delivery tracking.

Key Features

Reads recipient data from Google Sheets

AI-generated greeting messages (max 15 words)

Location-aware personalized messaging

Sentiment-aware greeting generation

Automated Gmail email delivery

Status tracking ("Sended" / "Canceled") in Google Sheets

Controlled delay between emails to avoid API limits

Sequential processing (one email at a time)

Workflow Architecture
Manual Trigger
    ↓
Google Sheets (Read Data)
    ↓
Loop Over Items
    ↓
Wait Node (Delay Control)
    ↓
AI Model (Greeting Generation)
    ↓
Gmail Send Message
    ↓
IF Condition (Success Check)
    ↓
Google Sheets Update Status
Tech Stack
Component	Technology
Automation Platform	n8n
AI Model	Google Gemini API
Email Service	Gmail API
Data Source	Google Sheets
Version Control	GitHub
Google Sheet Format

Your spreadsheet should contain:

Name	Location	EmailID	Status
John	Chennai	john@email.com
	(auto updated)

Status Values:

Sended → Email delivered successfully

Canceled → Email sending failed

Setup Instructions
1. Clone Repository
git clone https://github.com/Shameer28tm/ai-greeting-email-automation.git
2. Import Workflow into n8n

Open n8n dashboard

Click Import Workflow

Upload email-automation.json

3. Configure Credentials

You must connect:

Google Sheets API

OAuth or Service Account authentication

Provide sheet access

Gmail API

Connect sender Gmail account

Example sender:

Zclouddigitechx25@gmail.com
Gemini AI API

Add API key in n8n credentials

Ensure quota availability

4. Adjust Delay Settings

Recommended delay:

15–20 seconds between emails

Prevents API rate-limit errors

Execution
Manual Run

Use Manual Trigger for testing.

Automated Run (Optional)

You can replace Manual Trigger with:

Schedule Trigger (daily/hourly)

Webhook Trigger

Google Sheets Trigger

Error Handling Strategy

Common issues and fixes:

Issue	Cause	Solution
API quota exceeded	Too many AI requests	Increase delay or upgrade plan
Email not sending	Gmail OAuth issue	Reconnect Gmail credentials
Sheet not updating	Wrong column mapping	Use row_number matching
Use Cases

Marketing greeting campaigns

Customer engagement automation

Internship/demo automation projects

AI workflow learning projects

Portfolio demonstration

Security Notes

Never commit API keys publicly

Use environment variables where possible

Restrict Google Sheet access appropriately

Future Improvements

Retry logic for failed emails

Bulk scheduling support

Advanced sentiment personalization

Dashboard analytics integration

Email template customization

Author

Shameer
AI Automation & Workflow Enthusiast

GitHub:
https://github.com/Shameer28tm

License

This project is open for learning and demonstration purposes.
Modify and use as needed.

Refrance flow img
<img width="1024" height="1536" alt="ChatGPT Image Feb 25, 2026, 12_09_32 AM" src="https://github.com/user-attachments/assets/1c1ee47e-eb5d-4b03-af65-6c6961f4700c" />

