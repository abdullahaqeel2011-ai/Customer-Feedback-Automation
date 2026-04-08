🛠️ Customer Complaint & Feedback Automation

📌 Project Overview
This project is an automated customer complaint and feedback handling system built using n8n. It captures complaints via a webhook, categorizes them, sends email notifications to the appropriate team, and ensures all messages are properly tracked.

With this workflow, businesses can streamline complaint management, improve response time, and enhance customer satisfaction.

🚀 Features

• 📩 Webhook-based Complaint Intake – Accept customer complaints in real-time.
• 📝 Input Validation – Ensures required fields (Name, Email, Account Number, Complaint Type, Message) are provided.
• 🔄 Smart Categorization – Automatically routes complaints like:
• Card Issue
• Online Banking
• Loan Inquiry
• ⚠️ Uncategorized Complaint Handling – Flags all other complaints for manual review.
• 📧 Email Notification System – Sends notifications to the support team for timely action.
• 🗂️ Data Tracking – All complaint details are structured for easy logging or further storage (Google Sheets integration optional).
• ⏱️ Time-Saving Automation – Reduces manual work and accelerates complaint resolution.

⚙️ How to Run n8n (Docker)
docker run -it --rm \
  -p 5678:5678 \
  n8nio/n8n

Open in browser: http://localhost:5678

📥 How to Import Workflow

• Open n8n
• Click Import
• Upload customer-complaint-workflow.json

🧪 How to Test (cURL)
curl -X POST http://localhost:5678/webhook/customer-complaint \
-H "Content-Type: application/json" \
-d '{
  "CustomerName": "John Doe",
  "AccountNumber": "123456789",
  "ComplaintType": "Card Issue",
  "Message": "My card is blocked"
}'
🧩 Workflow Logic

• Webhook Node – Receives customer complaints.
• Edit Fields Node – Standardizes and assigns incoming fields (CustomerName, AccountNumber, ComplaintType, Message).
• If Node – Checks complaint type:
• Card Issue / Online Banking / Loan Inquiry → Routes to main notification email.
• All other complaints → Routed as “Uncategorized” email.
• Gmail Nodes – Send emails with formatted HTML content to the support team.

📊 Daily Summary & Reporting

(Optional: Extend workflow to generate daily summaries including:)

• Total complaints received
• Complaint type breakdown
• Priority assessment
• Alerts for repeated or critical issues

⚠️ Error Handling

• Any failed node triggers an error capture.
• Sends alert emails to the administrator.
• Prevents loss of critical complaints.

👤 Author 

Abdullah Aqeel 

AI Automation Engineer | SQAE
