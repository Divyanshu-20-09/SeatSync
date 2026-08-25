# SeatSync 📚

### QR-Based Library Seat Booking & Management System

SeatSync is a web-based library seat booking system designed to make finding and reserving library seats faster and more efficient.

Instead of searching through the library to find an available seat, students can **scan the QR code attached to a seat** to instantly identify that seat, check its current availability, and book it.

The system also provides authentication, real-time seat status updates, booking management, and administrative controls for managing library seats and usage.

---

## 🚀 Live Demo

**Live Demo:** https://seatsync.vercel.app
---

## 💡 Problem

In a busy library, students often spend unnecessary time looking for an available seat. Even after finding a seat, there may be uncertainty about whether it has already been occupied or reserved.

This creates:

* ⏱️ Time wasted searching for seats
* ❓ Uncertainty about seat availability
* 🔄 Multiple users attempting to book the same seat
* 📋 Difficulty managing seat usage efficiently

## 💡 Solution

SeatSync connects each physical library seat with its digital status using a **unique QR code**.

A student can simply scan the QR code on a seat to access that specific seat in the application, check its availability, and book it.

This creates a direct connection between the **physical seat and its digital booking record**.

---

## ⚙️ How SeatSync Works

```text
        📱 Scan Seat QR Code
                │
                ▼
        💺 Identify Seat
                │
                ▼
       🔍 Check Availability
                │
          ┌─────┴─────┐
          │           │
       Available    Occupied
          │           │
          ▼           ▼
      ✅ Book       ❌ Cannot Book
          │
          ▼
    🔄 Update Seat Status
          │
          ▼
      📊 Database
```

---

## ✨ Key Features

### 👤 Authentication & User Management

* User registration and login
* OTP-based verification
* Role-based access for students and administrators
* Secure authentication through Supabase

### 💺 Seat Booking

* Scan a QR code to identify a specific seat
* View the current seat availability
* Book an available seat
* Release booked seats
* Prevent duplicate or conflicting bookings

### 📱 QR Code System

* Unique QR code associated with each library seat
* QR scanning directly from the web application
* QR code generation for seats
* Direct access to individual seat information

### 🔄 Real-Time Updates

Seat availability and booking status can be updated in real time, allowing users to see changes without relying on stale seat information.

### 🛠️ Admin Management

Administrators can manage library seating and monitor usage through the system.

* Manage seats
* Monitor seat availability
* Manage bookings
* Track library usage
* View usage-related analytics

---

## 🖥️ Application Flow

### Student

```text
Login / Sign Up
      ↓
Browse Library Seats
      ↓
Scan Seat QR
      ↓
View Seat Status
      ↓
Book / Release Seat
      ↓
Real-Time Status Update
```

### Administrator

```text
Admin Login
      ↓
Dashboard
      ↓
Manage Seats & Bookings
      ↓
Monitor Usage
      ↓
View Analytics
```

---

## 🛠️ Tech Stack

### Frontend

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square\&logo=react\&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square\&logo=typescript\&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square\&logo=tailwindcss\&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square\&logo=vite\&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat-square\&logo=reactrouter\&logoColor=white)

* React
* TypeScript
* Tailwind CSS
* Vite
* React Router

### Backend & Database

![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square\&logo=supabase\&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square\&logo=postgresql\&logoColor=white)

* Supabase
* PostgreSQL
* Supabase Authentication
* Real-time database updates

### QR & Supporting Libraries

* `html5-qrcode` — QR code scanning
* `qrcode.react` — QR code generation

---

## 🏗️ Architecture

```text
┌──────────────────────────────┐
│          User / Admin        │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       React Frontend         │
│  TypeScript + Tailwind CSS   │
└──────────────┬───────────────┘
               │
       ┌───────┴────────┐
       │                │
       ▼                ▼
  QR Scanning       Authentication
       │                │
       └───────┬────────┘
               │
               ▼
┌──────────────────────────────┐
│           Supabase           │
│  Authentication + Backend    │
│      + Real-time Data        │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│         PostgreSQL           │
│ Seats · Users · Bookings     │
│       · Usage Data           │
└──────────────────────────────┘
```

---

## 📂 Project Structure

```text
SeatSync/
│
├── 📁 src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── ...
│
├── 📁 public/
│
├── 📄 index.html
├── 📄 package.json
├── 📄 package-lock.json
├── 📄 vite.config.ts
├── 📄 tsconfig.json
│
├── 📄 supabase_schema.sql
├── 📄 .env.example
├── 📄 .gitignore
│
├── 📄 README.md
└── ...
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have installed:

* Node.js
* npm
* A Supabase project

### 1. Clone the repository

```bash
git clone https://github.com/Divyanshu-20-09/SeatSync.git
cd SeatSync
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file based on `.env.example`.

Add the required Supabase configuration values.

> **Do not commit your `.env` file or expose private credentials.**

### 4. Set up the database

Use the provided:

```text
supabase_schema.sql
```

to create the required database structure in your Supabase project.

### 5. Start the development server

```bash
npm run dev
```

Vite will provide the local development URL in the terminal.

---

## 🗄️ Database

SeatSync uses **PostgreSQL through Supabase** for storing and managing application data.

The database handles information related to:

* 👤 Users
* 💺 Library seats
* 📅 Bookings
* 🔄 Seat availability
* 📊 Usage information

Supabase also provides authentication and real-time functionality used by the application.

---

## 🔐 Security & Booking Logic

The application is designed to ensure that seat availability remains consistent between users.

The booking system helps prevent:

* Duplicate seat bookings
* Conflicting reservations
* Booking seats that are already occupied

Authentication and backend functionality are handled through Supabase.

---

## 📊 Admin Dashboard

SeatSync includes administrative functionality for managing and monitoring the library system.

Administrators can:

* Add and manage seats
* Monitor seat status
* Manage bookings
* Track seat usage
* View usage analytics

---

## 🔮 Future Improvements

Some areas that can be extended further include:

* 📜 Detailed booking history
* ⏳ Automatic booking expiration
* 🔔 Booking and expiry notifications
* 📊 More detailed usage analytics
* 📱 Improved mobile experience
* 🏫 Integration with existing college/library authentication
* ⚡ Further optimization of real-time seat management

---

## 👨‍💻 Author

### Divyanshu P

Computer Science Engineering student at VIT Chennai.

**GitHub:** [Divyanshu-20-09](https://github.com/Divyanshu-20-09)

---

<p align="center">
  <b>SeatSync</b> — Making library seat booking simpler through QR-based access.
</p>
