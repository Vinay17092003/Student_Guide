# 🎓 Student Guide

A full-stack web app that helps Indian students choose a study path. Browse course information by education level, get personalised course suggestions from an interests form, and ask an AI chatbot any question.

**Stack:** React 18 · React Router 6 · Bootstrap 5 · Node.js · Express · MongoDB (Mongoose) · Google Gemini API

---

## ✨ Features

| Feature | What it does |
|---|---|
| **Auth** | Sign up / log in with username or email. Passwords hashed with bcrypt. |
| **Course explorer** | Info pages for Class 5–10, PUC, UG Courses, Engineering, Medical, BCA, Diploma and Competitive Exams. |
| **Interest-based suggestions** | Pick strongest subjects, interests, passions, hobbies (plus elective, discipline and skills for higher levels) and get matching course/career suggestions from MongoDB. |
| **AI chatbot** | Short, expert-style answers to any doubt, powered by Gemini, with conversation history. |
| **Help page** | Usage help for the app. |

---

## 🗂️ Project Structure

```
student-guide/
├── package.json            # Frontend (Create React App) dependencies & scripts
├── index.js                # Legacy entry file (CRA uses src/index.js)
├── public
├── src/
│   ├── index.js            # React entry point
│   ├── App.js              # Routes + login state (persisted in localStorage)
│   └── project/            # All pages & components
│       ├── LogIn.js, SignUp.js
│       ├── Home.js, Navbar.js, Help.js
│       ├── Class510.js, PUC.js, Diploma.js, UgCourses.js
│       ├── Engineering.js, Medical.js, Bca.js, CompetitiveExams.js
│       ├── Interests.js                 # Interests form (level selector)
│       ├── I_class5_10.js, I_pu.js, I_diploma_ug.js   # Level-specific forms
│       ├── Chatbot.js                   # Chat UI
│       └── *.css, *.jpg                 # Styles & carousel images
└── server/                # Backend API
    ├── server.js           # Express app, MongoDB connection, route mounting
    ├── package.json
    ├── routes/
    │   ├── auth.js         # /auth/signup, /auth/signin
    │   ├── formRoutes.js   # /form/get-suggestions
    │   └── chatBot.js      # /chatBot  (Gemini)
    └── models/             # Mongoose models
        ├── User.js         # collection: login_details
        ├── StrongestSubject.js  Passion.js  Hobbies.js
        ├── InterestSubject.js   Skills.js
        └── Electives.js         Discipline.js
```

---

## ✅ Prerequisites

- **Node.js** 18+ and npm
- **MongoDB** running locally on `mongodb://localhost:27017`
- A **Google Gemini API key** ([get one here](https://aistudio.google.com/app/apikey))

---

## 🚀 Getting Started

### 1. Install dependencies

```bash
# Frontend (from project root)
npm install

# Backend
cd server
npm install
```

### 2. Configure environment

Create `server/.env`:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

> `.env` is git-ignored — never commit your key.

### 3. Start MongoDB

Make sure `mongod` is running. The app uses the database **`StudentGuide`** (created automatically).

### 4. Run the backend

```bash
cd server
npm start
# 🚀 Server running at http://localhost:5000
```

### 5. Run the frontend

```bash
# from project root
npm start
# opens http://localhost:3000
```

---
