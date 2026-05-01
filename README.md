# Learnr — Personal Learning Dashboard

A full-stack web app to track courses, goals, streaks, and weekly study activity — with a built-in **AI Tutor** powered by OpenRouter.

![Status](https://img.shields.io/badge/status-live-brightgreen) ![Node](https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js) ![DB](https://img.shields.io/badge/database-JSON%20file-orange) ![OpenRouter](https://img.shields.io/badge/AI-OpenRouter-6366f1)

---

## 🌐 Live Links

| | URL |
|--|--|
| **Frontend (Vercel)** | [https://codedwebsite.vercel.app](https://codedwebsite.vercel.app) |
| **Backend (Render)**  | Update after deploy |

---

## ✨ Features

- 🔐 **Auth** — Register / Login with JWT, auto session restore
- 📊 **Dashboard** — Streak banner, metrics, weekly activity bar chart
- 📚 **Courses** — Add, track, delete courses with progress bars
- 🎯 **Goals** — Set targets with deadlines, track and delete goals
- 📈 **Stats** — Total hours, heatmap, completion rate
- 🤖 **AI Tutor** — Chat powered by OpenRouter (Llama 3.1 free)
- 🗄️ **JSON Database** — Pure JS, no native deps, works everywhere

---

## 🗂 Project Structure

```
learnr/
├── frontend/
│   ├── index.html       ← Full SPA (HTML + CSS + JS)
│   └── vercel.json      ← Vercel deploy config
├── backend/
│   ├── server.js        ← Express REST API + OpenRouter AI
│   ├── package.json     ← Pure JS deps only
│   ├── render.yaml      ← Render deploy config
│   └── .env.example
├── .gitignore
└── README.md
```

---

## 🚀 Local Development

### 1. Clone
```bash
git clone https://github.com/YOUR_USERNAME/learnr-dashboard.git
cd learnr-dashboard
```

### 2. Backend
```bash
cd backend
npm install
cp .env.example .env
npm start
# → http://localhost:3001
```

### 3. Frontend
```bash
open frontend/index.html
# or: npx live-server frontend
```

### 4. Demo account
```
Email:    demo@learnr.app
Password: demo123
```

---

## ☁️ Deployment

### Step 1 — Push to GitHub
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/learnr-dashboard.git
git push -u origin main
```

### Step 2 — Deploy Backend to Render (free)

1. Go to [render.com](https://render.com) → **New → Web Service**
2. Connect your GitHub repo
3. Set **Root Directory** to `backend`
4. **Build Command:** `npm install`
5. **Start Command:** `node server.js`
6. Go to **Environment** tab and add:

| Variable | Value |
|----------|-------|
| `JWT_SECRET` | Long random string (see below) |
| `OPENROUTER_API_KEY` | From [openrouter.ai/keys](https://openrouter.ai/keys) |
| `FRONTEND_URL` | `https://codedwebsite.vercel.app` |

Generate JWT secret:
```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

7. Click **Deploy** → copy your Render URL (e.g. `https://learnr-backend.onrender.com`)
8. Update `RENDER_URL` in `frontend/index.html` with your actual Render URL
9. Push the update → Vercel auto-redeploys

### Step 3 — Deploy Frontend to Vercel

1. Go to [vercel.com](https://vercel.com) → **New Project** → import GitHub repo
2. Set **Root Directory** to `frontend`
3. Framework: **Other**
4. Click **Deploy**

### Step 4 — Get OpenRouter API Key

1. Go to [openrouter.ai](https://openrouter.ai) → sign up free
2. Go to [openrouter.ai/keys](https://openrouter.ai/keys) → **Create Key**
3. Paste into Render as `OPENROUTER_API_KEY`

Uses **`meta-llama/llama-3.1-8b-instruct:free`** — completely free.

---

## 🗄️ Database

Uses Node's built-in `fs` to store data in `db.json` — zero native compilation, works on every platform.

| Table | Purpose |
|-------|---------|
| `users` | Accounts, bcrypt passwords, streak |
| `courses` | Per-user course tracking |
| `goals` | Learning goals with progress |
| `activity` | Daily study hours |
| `chats` | AI conversation history |

---

## 🔌 API Reference

```
POST /api/auth/register   { name, email, password }
POST /api/auth/login      { email, password }
GET  /api/auth/me

GET    /api/courses
POST   /api/courses
PUT    /api/courses/:id
DELETE /api/courses/:id

GET    /api/goals
POST   /api/goals
DELETE /api/goals/:id

GET  /api/activity/week
POST /api/activity/log    { hours }
GET  /api/stats

POST /api/ai/chat         { message, history[] }
GET  /api/ai/history

GET  /api/health
GET  /ping
```

> All routes except `/api/auth/*` require `Authorization: Bearer <token>`

---

## 🤖 AI Usage

Built with **Claude (Anthropic)**:
- Designed full UI/UX — dark theme, layout, components
- Built Express backend with JSON storage and REST API
- Integrated OpenRouter AI with personalized system prompts
- Wrote Vercel + Render deployment configs
- Generated this README

**Built without AI:**
- Product requirements and feature decisions
- Choosing the tech stack and platforms
- Reviewing, testing, and deploying all code

---

## 🛠 Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | Vanilla HTML/CSS/JS (SPA) |
| Hosting | Vercel |
| Backend | Node.js + Express |
| Hosting | Render |
| Database | JSON file (fs module) |
| Auth | JWT + bcrypt |
| AI | OpenRouter (Llama 3.1 8B free) |

---

## 📄 License

MIT
