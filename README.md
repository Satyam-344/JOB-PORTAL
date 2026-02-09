# Job Portal

A full-stack Job Portal web application built with **React, Node.js, Express, MongoDB, and Redux**.

---

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Folder Structure](#folder-structure)
5. [Installation](#installation)
6. [Usage](#usage)
7. [Contributing](#contributing)
8. [License](#license)

---

## Overview
This Job Portal allows users to:
- Browse jobs by category
- Apply for jobs
- Manage their profile
- Admins can manage jobs, companies, and applications

It has a **React frontend**, a **Node.js/Express backend**, and **MongoDB** for data storage. State management is handled with **Redux**.

---

## Features
- User authentication & profile management
- Job listing, filtering, and search
- Admin dashboard for managing jobs, companies, and applications
- Responsive UI with Tailwind CSS
- Modern React components and hooks for clean UI

---

## Tech Stack
- **Frontend:** React, Redux, Tailwind CSS, Vite  
- **Backend:** Node.js, Express.js  
- **Database:** MongoDB  
- **Authentication:** JWT  
- **Other:** REST API, Axios for API calls

---

## Folder Structure
jobportal-yt-main/
│
├─ backend/
│ ├─ controllers/ # Route handlers
│ ├─ middlewares/ # Authentication & error handling
│ ├─ models/ # MongoDB schemas
│ ├─ routes/ # API routes
│ ├─ utils/ # Helper functions
│ ├─ package.json
│ └─ index.js # Server entry point
│
├─ frontend/
│ ├─ src/
│ │ ├─ components/ # Reusable components (HeroSection, FilterCard, LatestJobs, etc.)
│ │ ├─ hooks/ # Custom hooks (useGetAllJobs, useGetCompanies, etc.)
│ │ ├─ lib/ # Utility functions
│ │ ├─ redux/ # Redux slices and store
│ │ ├─ App.jsx
│ │ ├─ main.jsx
│ │ └─ index.css
│ ├─ public/ # Public assets (images, logo, etc.)
│ ├─ package.json
│ └─ vite.config.js
│
├─ .gitignore
├─ README.md
└─ package-lock.json


---

## Installation

### Backend
```bash
cd backend
npm install
npm run dev


## frontend

cd frontend
npm install
npm run dev

Usage......

1.Register/Login as a user
2.Browse jobs, filter by category, and apply to jobs
3.Admin can manage jobs, companies, and applications
4.Redux handles state for jobs, user data, and applications


#Contributing......

1.Fork the repository
2.Create your feature branch: git checkout -b feature-name
3.Commit your changes: git commit -m 'Add some feature'
4.Push to the branch: git push origin feature-name

