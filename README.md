Klickks Assignment — Login & Logout Flow (Full Stack Auth App)

A feature-complete authentication system built with React (frontend) and Node.js + Express + SQLite (backend), offering secure user registration, login, session handling, and protected routes.

Features
Backend (Node.js + Express + SQLite)

SQLite Database: Dynamically created with a users table.

Secure Password Storage: Passwords hashed using bcrypt.

Session Management: Managed by express-session with secure cookies.

RESTful API: Endpoints for register, login, authentication check, dashboard access, and logout.

Input Handling:

Email validation.

Prevention of duplicate accounts.

CORS Support: Configured to communicate with the frontend.

Frontend (React + Vite)

Modular Components: Includes Login, Register, and Dashboard.

Client-side Validation: Provides user feedback and form error handling.

Session Persistence: Maintains authenticated state across browser sessions.

Protected Routes: Restricts dashboard access to logged-in users only.

Responsive UI: Mobile-friendly layout with loading states for UX clarity.

Project Structure

project-root/
├── backend/
│   ├── server.js          # Express server setup
│   ├── db.js             # SQLite configuration
│   ├── routes/
│   │   └── auth.js       # Authentication endpoints
│   └── package.json      # Backend dependencies
├── frontend/
│   ├── src/
│   │   ├── main.jsx      # React entry point
│   │   ├── App.jsx       # Root component
│   │   └── components/
│   │       ├── Login.jsx
│   │       ├── Register.jsx
│   │       └── Dashboard.jsx
│   ├── index.html        # HTML template
│   ├── vite.config.js    # Build config
│   └── package.json      # Frontend dependencies
└── README.md             # (This file)

API Endpoints

Method	Endpoint	Description

POST	/api/register	Register a new user

POST	/api/login	Authenticate user & start session

GET	/api/check-auth	Check current auth status

GET	/api/dashboard	Access protected dashboard

POST	/api/logout	Logout & destroy session

Prerequisites

Node.js v14+

npm or yarn package manager

Backend

cd backend

npm install

npm start

Runs backend server at http://localhost:5000

Auto-creates users.db (SQLite)

Frontend

cd frontend

npm install

npm run dev

Runs frontend at http://localhost:3000

Usage Guide

Register: Create an account using email & password.

Login: Authenticate and initiate a session.

Dashboard: Access once logged in.

Logout: Use the logout function to end the session and return to login.

Security Highlights

Password hashing via bcrypt.

Session cookies using httpOnly.

Frontend access only via configured CORS origin.

Safe input handling and parameterized database queries to prevent SQL injection.

Database Schema

Column	Type	Description

id	INTEGER	Primary key (auto-increment)

email	TEXT	User email (unique)

password	TEXT	Bcrypt-hashed password

created_at	DATETIME	Account creation timestamp

Development Notes

Fast builds via Vite

Backend uses ES modules (check package.json)

UI styling via Tailwind CSS (via CDN)

Session lifespan: 24 hours

CORS restricted to http://localhost:3000
