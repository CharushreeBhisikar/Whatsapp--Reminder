# 🤖 WhatsApp Reminder Bot using Twilio, Flask, and Google Sheets

A smart reminder system that lets users set WhatsApp reminders using natural language like:

> *"Remind me to call mom at 5 PM today"*

This bot extracts the task and time from the message, stores it in a Google Sheet, and sends a WhatsApp reminder at the exact time using Twilio's WhatsApp API.

## 🔧 Features

✅ Set reminders using plain language (e.g., "remind me to study at 7 PM")  
✅ Stores tasks in **Google Sheets**  
✅ Sends real-time **WhatsApp messages** using **Twilio API**  
✅ Background scheduler checks for due tasks  
✅ Supports multiple users  
✅ Timezone-aware (`Asia/Kolkata` by default)


## 📦 Project Structure

📁 whatsapp_reminder/
├── app.py # Main Flask app
├── creds.json # Google API credentials
├── requirements.txt # All dependencies
└── README.md # Project documentation

## 📲 WhatsApp Sandbox Setup (Twilio)

> ⚠️ Required if you're using Twilio's free/trial sandbox account.

1. Go to your [Twilio WhatsApp Sandbox](https://www.twilio.com/console/sms/whatsapp/sandbox)
2. Send the given keyword (`join ...`) to this number on WhatsApp: +14155238886

3. Use that number (`whatsapp:+14155238886`) as the **sender (`from_`)** in your code.

## 📄 Google Sheets Setup

1. Go to [Google Developers Console](https://console.developers.google.com/)
2. Create a new project → Enable **Google Sheets API** and **Google Drive API**
3. Create Service Account credentials and download `creds.json`
4. Share your Google Sheet with the service account email (`...@...gserviceaccount.com`)
5. The sheet must have these headers:

time	task	sender
2025-07-11 17:30	Go to gym	whatsapp:+91xxxxxxxxxx

## 🚀 Installation & Running

### 1. Clone the repo

git clone https://github.com/your-username/whatsapp-reminder-bot.git
cd whatsapp-reminder-bot
2. Install requirements

pip install -r requirements.txt
3. Add your creds.json (Google API) in the root folder
4. Set up your Twilio credentials

Edit app.py:

account_sid = 'ACxxxxxxxxxxxxxxxxxxxxxxxxxx'
auth_token = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxx'
from_number = 'whatsapp:+14155238886'  # Twilio sandbox number

5. Start the Flask app
python app.py
App will run on http://localhost:5000

🧪 Test the Bot
Open a browser and visit:

http://localhost:5000/test
✅ If set up correctly, you'll receive a WhatsApp message.

✍️ How to Use (via WhatsApp)
Send a message like:
Remind me to drink water at 8:30 PM today
The bot will:
Extract time and task
Store it in the Google Sheet
Send a WhatsApp reminder at that time

🛠️ Technologies Used
🐍 Python 3
🌐 Flask (API backend)
🧠 dateparser (for natural language time)
📊 Google Sheets API (task storage)
📩 Twilio WhatsApp API (message delivery)
⏱️ Custom scheduler using threading

📅 Future Improvements
 Support recurring reminders
 Web frontend for viewing/editing reminders
 Voice input support
 Push to production (Render/Heroku deployment)

🔐 Disclaimer
This project uses Twilio Sandbox, which only allows sending messages to joined or verified numbers.

Never upload creds.json or sensitive Twilio keys to GitHub.

🙌 Acknowledgements:
Twilio WhatsApp API
Google Sheets Python API
dateparser Library

📩 Contact
Made with ❤️ by Nayan Meshram and Charushree Bhisikar

Let me know if you want:
- A deployment guide for **Render**, **Railway**, or **Heroku**
- A GUI or dashboard for managing reminders
- To package this into a public GitHub repository

I'm here to assist you with full project polish!
