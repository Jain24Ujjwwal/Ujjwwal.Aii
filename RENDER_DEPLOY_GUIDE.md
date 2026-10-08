# 🚀 How to Deploy Ujjwwal Jain AI to Render.com (24/7 Free Hosting)

This guide walks you through deploying **Ujjwwal Jain AI** as a free Web Service on [Render.com](https://render.com) so it stays online **24/7 even when your laptop is completely powered off**.

---

## 📋 Render.com Configuration Settings

When creating a new **Web Service** on Render, enter these exact settings:

| Setting | Value to Enter |
| :--- | :--- |
| **Name** | `ujjwwal-jain-ai` (or your choice) |
| **Language / Environment** | `Node` |
| **Branch** | `main` (or `master`) |
| **Region** | Oregon (US West) or Singapore |
| **Build Command** | `npm run build` |
| **Start Command** | `npm run start` |
| **Instance Type** | `Free` |

---

## 🔑 Environment Variables on Render

In the **Environment Variables** section on Render, add the following key-value pairs:

1. **`NODE_ENV`**:  
   `production`
2. **`PORT`**:  
   `10000` *(Render sets this dynamically, but adding 10000 ensures full alignment)*
3. **`GEMINI_API_KEY`**: *(Optional)*  
   Your Google Gemini API key if you want backend AI responses directly from Google.

*(Note: Zero passwords required! The workspace unlocks automatically for full instant access across all devices).*

---

## ⚡ Quick 3-Step Deployment Walkthrough

### Step 1: Upload Project to GitHub
1. Go to [GitHub.com](https://github.com) and click **New Repository**.
2. Name it `ujjwwal-ai` and set it to **Private** (or Public).
3. Upload/push your project files. *(The project already includes `.gitignore` to keep uploads fast and clean)*.

### Step 2: Connect to Render.com
1. Go to [Render.com](https://render.com) and sign in with GitHub.
2. Click **New +** in the top right $\rightarrow$ Select **Web Service**.
3. Select your `ujjwwal-ai` repository.

### Step 3: Click "Create Web Service"
1. Type `npm run build` as Build Command and `npm run start` as Start Command (or Render will read `render.yaml` automatically).
2. Click **Create Web Service**.
3. Render will build and launch your site at:  
   👉 `https://ujjwwal-jain-ai.onrender.com`

**🎉 Once deployed, this link will run 24 hours a day, 7 days a week, 365 days a year even when your computer is completely shut down!**
