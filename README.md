# 🏥 ConnectCareApp — Facility-Based Digital Health Platform

**ConnectCare** is a role-based digital health platform designed to connect **patients (clients)** with **clinicians**, **nutritionists**, and **counsellors** under a shared facility environment.
Each facility manages its own users, data, and billing status — enabling secure and private health management, communication, and tracking.

---

## 🌟 Core Features

### 👥 Role-Based Access

* **Client (Patient):**

  * Can log in to view appointments, chat with healthcare providers, and track personal data (e.g., weight, height, BMI).
  * Can confirm attendance for appointments.
* **Nutritionist:**

  * Updates client metrics (weight, BMI).
  * Books nutrition sessions and sends individual or collective messages.
* **Clinician:**

  * Schedules clinical visits.
  * Tracks missed appointments.
  * Sends updates to clients privately or collectively.
* **Counsellor:**

  * Sends daily notes that “stick” at the top of the shared chart.
  * Can message clients or groups privately.

---

### 🏢 Facility-Based System

* Each **facility** is an independent unit with:

  * Its own database space for patients and staff.
  * A unique **facility name** required at login (alongside Clerk authentication).
  * A **billing flag** (`isPaid: true/false`) to control access.
* **If `isPaid: false`**, the facility has limited access until payment is verified.

---

### 💬 Private & Collective Chat

* Secure messaging for:

  * Private chats between staff and clients.
  * Group discussions (nutritionist, clinician, counsellor, and clients together).
* All messages are tied to facility and user roles for controlled access.

---

### 📅 Calendar & Appointment Management

* Health workers can:

  * Schedule sessions or visits with clients.
  * Sync appointments to **Google or Apple Calendar**.
  * Send reminders and notifications before sessions.
* Clients can confirm appointments and view them directly from their devices.

---

### 🔔 Notifications & Reminders

* Automated reminders for:

  * Upcoming appointments.
  * Missed visits.
  * Daily counsellor notes and motivational updates.
* Supports **push notifications** for real-time updates on web or mobile.

---

### 📊 Analytics Dashboard

* Facility admins can view:

  * **Performance metrics** — number of active patients, completed sessions, missed visits.
  * **Client progress** charts (weight, BMI, and attendance trends).
  * **Role activity** — clinician, nutritionist, and counsellor interactions.

---

### 🧾 Billing & Payment Dashboard

* Facility billing is handled at the organizational level.
* Boolean flag `isPaid: true/false` determines system access.
* The admin dashboard allows:

  * Managing payment confirmations.
  * Viewing payment history and expiry.
  * Automated reminders before subscription expiration.

---

## ⚙️ Tech Stack

### Frontend

* **React + Vite**
* **Tailwind CSS** for responsive design
* **Radix UI** for modals & dialogs
* **Clerk** for authentication and session management
* **Axios** for API integration

### Backend

* **Express.js** for REST APIs
* **MongoDB + Mongoose** for database management
* **JWT / Clerk Webhooks** for secured route access
* **Node Scheduler (node-cron)** for reminders and automation

---

## 📂 Project Structure

```bash
frontend/
 ├── src/
 │   ├── components/     # UI components (NoteCard, Dialogs, etc.)
 │   ├── pages/          # Main views (Dashboard, Login, etc.)
 │   ├── lib/api.js      # Axios API setup
 │   ├── App.jsx         # Main app entry
 │   └── index.css       # Tailwind setup

backend/
 ├── models/             # Mongoose schemas (User, Facility, Appointment, Message)
 ├── routes/             # Express routes
 ├── controllers/        # Business logic
 ├── server.js           # Server entry point
 └── config/             # Env and DB setup
```

---

## 🔐 Authentication & Roles

Powered by **Clerk**:

* Users log in with **email + facility name**.
* Backend assigns roles (client, clinician, nutritionist, counsellor) after authentication.
* Facility and role-based route protection ensures secure data separation.

---

## 🚀 Running the App Locally

### 1️⃣ Install dependencies

```bash
cd backend && npm install
cd ../frontend && npm install
```

### 2️⃣ Create `.env` files

**Frontend `.env`:**

```bash
VITE_API_URL=http://localhost:5000
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_key_here
```

**Backend `.env`:**

```bash
PORT=5000
MONGO_URI=your_mongodb_connection_string
CLERK_SECRET_KEY=your_clerk_secret_here
```

### 3️⃣ Run the servers

```bash
# Backend
cd backend
npm run dev

# Frontend
cd ../frontend
npm run dev
```

Then open: **[http://localhost:5173](http://localhost:5173)**

---

## 🧑‍💻 Author

**Sheryl Bita**
Full-Stack Developer | HealthTech Enthusiast
Building digital health platforms that empower both patients and healthcare teams.

---

## 🛡️ License & Legal Notice

**© 2025 Sheryl Bita — All rights reserved.**

This project (**ConnectCareApp**) is proprietary software and is the intellectual property of **Sheryl Bita**.  
Unauthorized copying, modification, redistribution, or use of this software, in whole or in part, is strictly prohibited  
without prior written permission from the author.

For licensing or partnership inquiries, please contact: [bitasheryl@gmail.com]

