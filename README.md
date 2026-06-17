# Job Portal

A full-stack Job Portal web application connecting job seekers with employers. Built with the MERN stack — MongoDB, Express.js, React.js, and Node.js.

🔗 **Live Demo:** [https://dist-three-lake-23.vercel.app](https://dist-three-lake-23.vercel.app)

---

## Overview

The platform supports two types of users:

- **Students / Job Seekers** — Register, browse job listings, search and filter jobs, apply with resume, track application status
- **Recruiters** — Register as recruiter, create company profile, post job listings, view and manage all applicants

---

## Features

- Secure authentication using JWT tokens stored in HTTP-only cookies
- Role-based access control — separate dashboards for students and recruiters
- Resume and profile photo upload via Cloudinary
- Keyword-based job search across title and description
- Application status tracking — Pending, Accepted, Rejected
- Persistent login session using Redux Persist
- Fully responsive UI built with Tailwind CSS
- Protected routes on both frontend and backend

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js, Vite, Redux Toolkit, React Router DOM |
| Styling | Tailwind CSS, Radix UI, Framer Motion |
| State Management | Redux Toolkit, Redux Persist |
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Authentication | JWT, Bcrypt.js |
| File Storage | Cloudinary, Multer |
| HTTP Client | Axios |
| Deployment | Vercel (frontend), Render (backend), MongoDB Atlas |

---

## Project Structure

```
JOB-PORTAL/
├── backend/
│   ├── controllers/          # Route handler logic
│   │   ├── user.controller.js
│   │   ├── job.controller.js
│   │   ├── company.controller.js
│   │   └── application.controller.js
│   ├── middlewares/
│   │   ├── isAuthenticated.js  # JWT verification middleware
│   │   └── mutler.js           # Multer file upload middleware
│   ├── models/               # Mongoose schemas
│   │   ├── user.model.js
│   │   ├── job.model.js
│   │   ├── company.model.js
│   │   └── application.model.js
│   ├── routes/               # API route definitions
│   ├── utils/
│   │   ├── db.js             # MongoDB connection
│   │   ├── cloudinary.js     # Cloudinary config
│   │   └── datauri.js        # File buffer to DataURI converter
│   ├── index.js              # Express server entry point
│   └── package.json
│
└── frontend/
    ├── src/
    │   ├── components/       # UI components
    │   │   ├── admin/        # Recruiter dashboard components
    │   │   ├── auth/         # Login & Signup
    │   │   ├── shared/       # Navbar, Footer
    │   │   └── ui/           # Reusable UI primitives
    │   ├── hooks/            # Custom React hooks
    │   ├── redux/            # Redux slices and store
    │   ├── utils/            # API endpoint constants
    │   ├── App.jsx           # Route definitions
    │   └── main.jsx
    ├── vercel.json           # SPA routing config for Vercel
    └── package.json
```

---

## Getting Started

### Prerequisites

- Node.js v18+
- MongoDB Atlas account
- Cloudinary account

### Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory:

```env
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/jobportal
PORT=8000
SECRET_KEY=your_jwt_secret_key
CLOUD_NAME=your_cloudinary_cloud_name
API_KEY=your_cloudinary_api_key
API_SECRET=your_cloudinary_api_secret
FRONTEND_URL=http://localhost:5173
```

```bash
npm run dev
```

### Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env.local` file in the `frontend/` directory:

```env
VITE_API_URL=http://localhost:8000
```

```bash
npm run dev
```

Frontend runs at `http://localhost:5173`
Backend runs at `http://localhost:8000`

---

## API Endpoints

### User
| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/v1/user/register` | Register new user |
| POST | `/api/v1/user/login` | Login |
| GET | `/api/v1/user/logout` | Logout |
| POST | `/api/v1/user/profile/update` | Update profile |

### Jobs
| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/v1/job/get` | Get all jobs (with keyword search) |
| GET | `/api/v1/job/get/:id` | Get job by ID |
| POST | `/api/v1/job/post` | Post a new job (recruiter) |
| GET | `/api/v1/job/getadminjobs` | Get recruiter's posted jobs |

### Applications
| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/v1/application/apply/:id` | Apply to a job |
| GET | `/api/v1/application/get` | Get applied jobs |
| GET | `/api/v1/application/:id/applicants` | Get all applicants for a job |
| POST | `/api/v1/application/status/:id/update` | Update application status |

### Companies
| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/v1/company/register` | Register a company |
| GET | `/api/v1/company/get` | Get all companies |
| GET | `/api/v1/company/get/:id` | Get company by ID |
| PUT | `/api/v1/company/update/:id` | Update company info |

---

## Deployment

- **Frontend** deployed on [Vercel](https://vercel.com) — set `VITE_API_URL` environment variable to your backend URL
- **Backend** deployed on [Render](https://render.com) — set all `.env` variables in Render's environment settings, set `FRONTEND_URL` to your Vercel URL
- **Database** hosted on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

---

## License

This project is open source and available under the [MIT License](LICENSE).
