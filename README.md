
# Juspay Design Codethon – Setup Guide

Welcome to the **Design Codethon**! This guide helps you build your project from scratch — with modern tools, fast UI libraries, and AI-powered assistance.

Each participant will push their project to a **dedicated repo under**:  
[`https://github.com/juspay-codethon`](https://github.com/juspay-codethon)

---

## Step 0: Enable Temporary Admin Access via Kandji

1. Open **Kandji Self Service**
2. Search **"Temporary Admin Access"**
3. Click **Install** to enable admin rights
4. Proceed with the setup steps below

---

## 1. GitHub Setup Using PAT (Personal Access Token)

### A. Configure Git

```bash
git config --global user.name "your-name"
git config --global user.email "your-email@example.com"
```

### B. Generate a GitHub PAT

1. Go to: [https://github.com/settings/tokens](https://github.com/settings/tokens)
2. Click: **“Generate new token (classic)”**
3. Set:
   - **Note**: `Codethon Access`
   - **Expiration**: 30 days
   - **Scopes**:
     - `repo`
     - `workflow`
     - `read:org`
4. Click **Generate token** and **copy it immediately**

### C. Clone Your Repo

You’ll get your repo name (e.g., `codethon-yourname`) from the team. Run:

```bash
git clone https://github.com/juspay-codethon/codethon-yourname.git
```

When prompted:
- Username: your GitHub username
- Password: paste the **PAT**

---

## 2. Install Node.js via Kandji

1. Open **Kandji Self Service**
2. Search **“Node.js”**
3. Click **Install**

Verify:
```bash
node -v
npm -v
```

---

## 3. Create Project with Vite

We’ll use [Vite](https://vitejs.dev/) for a fast frontend dev experience.

### A. Create New Vite App

```bash
npm create vite@latest
```

- App Name: `my-app`
- Framework: `React`
- Variant: `TypeScript`

Then:

```bash
cd my-app
npm install
```

---

## 4. Setup Tailwind CSS (From Scratch)

### A. Install Tailwind

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### B. Configure Tailwind

Edit `tailwind.config.js`:

```js
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### C. Add Tailwind to CSS

In `src/index.css`, add:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Then import this in `main.tsx`:

```ts
import './index.css';
```

---

## 5. Setup shadcn/ui Components

### A. Initialize shadcn/ui

```bash
npx shadcn-ui@latest init
```

Choose:
- App directory: `src`
- Tailwind config: `tailwind.config.js`
- Alias: `@/components` (recommended)

### B. Add Components

```bash
npx shadcn-ui@latest add button
npx shadcn-ui@latest add card
npx shadcn-ui@latest add dialog
```

Explore all: https://ui.shadcn.dev/docs/components

---

## 6. Setup Cline + Gemini for AI-Powered Coding

### A. Install Cline Extension

1. Open **Cursor** or **VS Code**
2. Go to Extensions → Search `Cline` → Install

### B. Get Gemini API Key

1. Visit: [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Generate a key

### C. Configure Cline

1. Open Cline sidebar in your IDE
2. Go to **Settings → API Configuration**
3. Set:
   - **API Provider**: `Google Gemini`
   - **API Key**: Paste your key
   - **Model**: `gemini-2.0-flash-001`
4. Save

---

## Useful Dev Resources

- [shadcn/ui Components](https://ui.shadcn.dev/docs/components)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Lucide Icons](https://lucide.dev)
- [Vite Docs](https://vitejs.dev/guide/)
- [Gemini AI Studio](https://aistudio.google.com/app)

---

## Final Checklist

- [ ] Temporary admin via Kandji enabled
- [ ] GitHub repo cloned using PAT
- [ ] Node.js installed via Kandji
- [ ] Vite project created
- [ ] Tailwind CSS configured
- [ ] shadcn/ui components added
- [ ] Gemini API key set in Cline

---

## Questions?

Reach out on `#codethon-support` Slack channel. Happy coding, and bring your designs to life
