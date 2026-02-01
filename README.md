🖨️ Scan2Print

QR-based File Upload & Print Queue System

Scan2Print is a lightweight, production-ready system that allows customers to upload documents for printing using a QR code, while shopkeepers manage print jobs through a simple dashboard.

This project is designed with real-world print shops in mind: fast, reliable, no logins, no apps, no confusion.

🚀 Why Scan2Print?

Most local print shops still rely on:

WhatsApp file sharing

USB drives

Repeated explanations from customers

Scan2Print solves this with:

A single QR scan

A simple upload page

A clean print queue dashboard

No training required.

🧠 Architecture Overview (SoundBox Model)

Scan2Print follows the same battle-tested architecture used in the SoundBox project:

🔹 Frontend (Shared)

One shared upload page hosted on GitHub Pages

Used by all shops

Shop is identified via URL parameter (?shop=abc)

QR codes point directly to this page

🔹 Backend (Per Shop)

Each shop has its own isolated backend:

One Google Apps Script Web App

One Google Sheet (job log)

One Google Drive folder (uploaded files)

One dashboard (Apps Script HTML)

This ensures:

No data mixing between shops

Easy onboarding

Simple scaling

🧩 System Components
1️⃣ Customer Upload Page

Hosted on GitHub Pages

Mobile-first, QR-friendly

Uploads a single file

Clear success message: “Please inform the shopkeeper”

2️⃣ Shopkeeper Dashboard

Hosted inside Apps Script

Manual refresh (no auto polling)

Filters by:

Status (Active / Done / All)

Date (Today / Week / Month / All)

Actions:

Open file

Mark job as Done

3️⃣ Backend Logic

Google Apps Script

File upload → Google Drive

Job tracking → Google Sheets

Soft status updates (no deletes)

📊 Data Model

Each shop maintains a simple sheet:

Timestamp	File Name	File URL	Status
2026-02-01 10:32	resume.pdf	Drive link	ACTIVE
2026-02-01 10:21	photo.jpg	Drive link	DONE
🔐 Design Principles

No login required

No auto refresh (shopkeeper controls refresh)

Fire-and-forget uploads (customer doesn’t wait)

Soft deletes using status

Low quota usage (Apps Script safe)

🛠️ Tech Stack

Frontend: HTML, CSS, Vanilla JavaScript

Hosting: GitHub Pages

Backend: Google Apps Script

Storage: Google Drive

Database: Google Sheets

No frameworks. No build tools. No vendor lock-in.

📱 Example Flow

Customer scans QR code

Uploads file

Sees success message

Tells shopkeeper

Shopkeeper clicks Refresh

Opens file → prints → marks Done

Simple and predictable.

📦 Repository Structure
scan2print/
├── index.html      # Shared customer upload page
├── README.md       # Project documentation
└── assets/         # (Optional) logos / images

🎯 Current Status

✅ Upload page complete

✅ Dashboard complete

✅ Backend wired

✅ End-to-end tested

🔄 Multi-shop onboarding in progress

🔮 Future Enhancements

Multi-file uploads

WhatsApp auto notification

Print options (copies, color, size)

Shop analytics

Admin panel for shop onboarding

👨‍💻 About the Project

Scan2Print is built as a practical, real-world system, not a demo.
The focus is reliability, simplicity, and scalability for small businesses.
