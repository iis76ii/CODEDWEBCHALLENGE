# Learnr — Personal Learning Dashboard

A full-stack web app to track courses, goals, streaks, and weekly study activity — with a built-in **AI Tutor** powered by OpenRouter.

![Status](https://img.shields.io/badge/status-live-brightgreen) ![Node](https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js) ![DB](https://img.shields.io/badge/database-JSON%20file-orange) ![OpenRouter](https://img.shields.io/badge/AI-OpenRouter-6366f1)

---

## 🌐 Live Links

| | URL |
|--|--|
| **Frontend (Vercel)** | [https://codedwebsite.vercel.app](https://codedwebsite.vercel.app) |
| **Backend (Render)**  | [https://codedwebchallenge.onrender.com](https://codedwebchallenge.onrender.com) |

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
