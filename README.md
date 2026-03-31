# 🍽️ AKIR Restaurant – Backend API

## 🚀 Overview
This is the backend API for the **AKIR Restaurant Website**.

It handles reservations, contact form submissions, and email notifications using a robust and fault-tolerant system.

---

## ✨ Features

- 📅 Reservation system with email notifications
- 📩 Contact form handling
- 📧 Email integration (Brevo / SMTP fallback)
- 🔁 Retry mechanism for failed email requests
- 🌐 CORS support for frontend communication
- ❤️ Health check endpoint
- 🛡️ Input validation & rate limiting

---

## 🛠️ Tech Stack

- Node.js
- Express.js
- Axios
- Brevo API (Email service)
- dotenv

---

## 📦 Installation & Setup

```bash
# Navigate to backend folder
cd Web_Restaurant_backend

# Install dependencies
npm install

# Start server
node server.js
⚙️ Environment Variables

Create a .env file:

PORT=4000

# Brevo Email API
BREVO_API_KEY=your_brevo_api_key

# Email settings
MAIL_FROM=AKIR Restaurant <akirrestaurants@gmail.com>
MAIL_TO=akirrestaurants@gmail.com

# CORS
CORS_ORIGINS=http://localhost:5175,https://akir-restaurant.vercel.app
🌐 API Endpoints
❤️ Health Check
GET /health

Returns server status.

📅 Reservations
POST /api/reservations

Body:

{
  "name": "",
  "email": "",
  "phone": "",
  "date": "",
  "time": "",
  "guests": "",
  "specialRequests": ""
}

✔ Sends email to:

Restaurant
Customer (if successful)
📩 Contact Form
POST /api/contact

Body:

{
  "name": "",
  "email": "",
  "subject": "",
  "message": ""
}

✔ Sends email to:

Restaurant
📧 Email System
Uses Brevo API (recommended)
Includes retry logic for network failures
Handles errors like:
ECONNRESET
ETIMEDOUT
Prevents full request failure when possible
🧪 Development
Default Port: 4000

Supports local frontend:

http://localhost:5175
Logging enabled for debugging
🚀 Deployment

Recommended platforms:

Render
Railway
Fly.io
Steps:
Deploy backend
Set environment variables
Update frontend .env:

VITE_API_URL=https://your-backend-url.com

⚠️ Important Notes
Backend must be running for:
Reservation form
Contact form
Emails may land in Spam/Promotions
Rotate API keys if exposed
Avoid exposing .env in GitHub

## 📩 Contact

**Author**: A Anusha 
📧 **Email**: [anu.addagatla18@gmail.com](mailto:anu.addagatla18@gmail.com)

📌 Future Improvements
Database integration (store reservations)
Admin dashboard
Email templates improvement
Rate limiting per user/IP
Logging & monitoring (Winston / Logtail)