# 🚀 Ujjwwal AI — Personal AI Workspace

<div align="center">
  <img src="client/public/favicon.svg" width="100" height="100" alt="UJ Logo" />
  <h3><strong>Ujjwwal AI</strong></h3>
  <p><em>Your private, production-grade personal AI workspace accessible from any device.</em></p>
</div>

---

## 📌 Overview

**Ujjwwal AI** is a production-ready, full-stack personal AI workspace engineered for seamless multi-device productivity. Whether you are working from your **Windows laptop, smartphone, tablet, or college campus computer**, Ujjwwal AI delivers an intelligent, unified assistant experience with strict zero-client key leakage security.

---

## 🏗️ Architecture

```
ujjwwal-ai/
├── client/                     # Frontend (React 18, TypeScript, Vite, Tailwind CSS)
│   ├── public/                 # PWA Manifest, UJ Monogram Vector Logo, Favicons
│   ├── src/
│   │   ├── components/         # Layout, Chat, Studio Tools, Documents, Settings
│   │   ├── context/            # Theme, Auth, Chat Streaming, Privacy Contexts
│   │   ├── services/           # Typed API Clients, SSE Streaming, Auth Helpers
│   │   └── types/              # Clean Domain Types
│   ├── Dockerfile              # Multi-stage container build with Nginx
│   └── nginx.conf              # Reverse proxy & SPA router
│
├── server/                     # Backend API (Node.js, Express, TypeScript)
│   ├── src/
│   │   ├── config/             # Zod Environment Validation, PostgreSQL Pool
│   │   ├── database/           # Production Schema (PostgreSQL/Supabase) & Seeds
│   │   ├── middleware/         # JWT Auth, Rate Limiter, Helmet Security, Error Handler
│   │   ├── routes/             # Health, Auth, AI, Documents, User, Prompts
│   │   └── services/           # Google Gemini AI Provider, Auth, Database Repo
│   └── Dockerfile              # Production Node.js runner
│
├── docker-compose.yml          # Container stack (Postgres + Server + Client)
├── .env.example                # Central configuration template
└── package.json                # Monorepo workspaces and scripts
```

---

## 🔒 Security Guarantee: Zero Client-Side API Key Exposure

- Your **Google Gemini API Key is never bundled into client JavaScript** or exposed over network headers.
- All AI queries, stream buffers, and document intelligence requests flow exclusively through secure server endpoints (`/api/ai/*`).
- Includes **Rate Limiting** (`express-rate-limit`), **Helmet** security headers, **CORS whitelisting**, and **JWT authentication**.

---

## ⚡ Quick Start (Phase 1)

### 1. Prerequisites
- **Node.js** v18+ or v20+
- **npm** v9+
- (Optional) **Docker** & **Docker Compose**

### 2. Install Dependencies
From the root directory:
```bash
npm run install:all
```

### 3. Configure Environment Variables
Copy `.env.example` to `server/.env`:
```bash
# In server directory:
cp .env.example server/.env
```

Open `server/.env` and add your **Google Gemini API key**:
```ini
GEMINI_API_KEY=your_gemini_api_key_here
GEMINI_MODEL=gemini-2.5-flash
```
*(Get a free key at [Google AI Studio](https://aistudio.google.com/app/apikey))*.

> 💡 **Offline/Demo Mode**: If `GEMINI_API_KEY` is not provided, the backend automatically runs in **Setup Mode**, providing a guided walkthrough on where to get and insert your key without crashing.

### 4. Run Development Servers
Start both backend (Port 5000) and frontend (Port 5173) concurrently:
```bash
npm run dev
```

Open your browser at:
**[http://localhost:5173](http://localhost:5173)**

---

## 📱 Multi-Device & PWA Access (Laptop, Phone, Tablet)

1. **Local Wi-Fi Access**:
   The Vite dev server is configured with `host: true`. Find your computer's local IP address (e.g. `192.168.1.15`), and open `http://192.168.1.15:5173` on your phone or tablet connected to the same Wi-Fi.

2. **Install as PWA**:
   - **Chrome / Edge (Desktop)**: Click the **Install app** icon in the address bar.
   - **Safari (iOS / iPadOS)**: Tap **Share** ➡️ **Add to Home Screen**.
   - **Chrome (Android)**: Tap the three dots ➡️ **Install app** / **Add to Home screen**.

---

## 🐳 Docker Deployment

To launch the complete PostgreSQL database, Node.js API, and Nginx frontend in isolated Docker containers:

```bash
docker compose up --build
```
- Frontend UI: `http://localhost:5173`
- Backend API: `http://localhost:5000`
- PostgreSQL: `localhost:5432`

---

## 🛠️ Phase 1 Foundation Features Included

1. **AI Chat**: Multi-turn conversation with real-time SSE streaming responses, syntax-highlighted code blocks with copy buttons, and model selector.
2. **AI Studio Tools**:
   - **Summarizer**: Executive summaries with key takeaways.
   - **Translator**: Technical polyglot translator preserving code formatting.
   - **Code Assistant**: Clean code refactoring and bug analysis.
   - **Writing Assistant**: Tone adjustment and prose polishing.
   - **Text Modifier**: Custom user instructions.
3. **Document Intelligence**: Upload and analyze `.txt`, `.csv`, `.md`, `.json`, `.pdf`, `.docx` files with targeted query questions.
4. **Prompt Library**: Curated pre-built system prompts with 1-click launch into AI Chat.
5. **Command Palette (`Ctrl+K` / `⌘K`)**: Rapid navigation and actions modal.
6. **Themes**: Dark, Light, and System themes with smooth transitions.
7. **Privacy & GDPR Controls**:
   - Custom Cookie Consent banner & settings modal.
   - Full workspace **Data Export (JSON)**.
   - Permanent workspace **Data Purge / Right to be Forgotten**.
8. **Scalable Database Architecture**: Full PostgreSQL/Supabase schema (`users`, `conversations`, `messages`, `prompts`, `preferences`) with automatic dev fallback so you can run instantly without database configuration.

---

## 📄 License
MIT © Ujjwal
