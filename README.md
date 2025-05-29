
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

## 🛠️ Git Installation (macOS)

If Git is not already installed on your system, follow the steps below to install it via the command line:

### Install Using Homebrew

1. First, check if Homebrew is installed:

```bash
brew --version
```

2. If Homebrew is not installed, install it:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. Once Homebrew is installed, install Git:

```bash
brew install git
```

4. Verify the installation:

```bash
git --version
```

> You should see a version output like `git version 2.42.0` confirming it's installed successfully.

If `git` is not already installed on your machine, follow these steps:


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
cd codethon-yourname
```

When prompted:
- Username: your GitHub username
- Password: paste the **PAT**

---

## 1.1 Git Basics: Branch, Commit, Push

### A. Create and switch to a new branch

```bash
git checkout -b your-branch-name
```

### B. Stage and commit changes

```bash
git add .
git commit -m "your meaningful commit message"
```

### C. Push your branch to GitHub

```bash
git push origin your-branch-name
```

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

## Deploying Your App on Vercel
### Deploy via Vercel CLI

If you prefer deploying directly from the terminal:

1. Install Vercel CLI globally:

```bash
npm install -g vercel
```

2. Run the deployment command:

```bash
vercel
```

3. It will:
   - Ask to log in (use GitHub or email)
   - Ask for the root directory (`./`)
   - Ask if it’s a React project → Yes
   - Auto-detect Vite → Yes
   - Ask if you want to override settings → No (use defaults)

4. After a few seconds, your project will be live! 🚀

To redeploy after making changes:
```bash
vercel --prod
```


Once you're done building your project, you can deploy it to the internet using **Vercel** (which works seamlessly with Vite, React, and Tailwind).

### Deploy via Vercel Dashboard

1. Go to [https://vercel.com](https://vercel.com) and sign in with GitHub
2. Click **“Add New → Project”**
3. Import your repo from `juspay-codethon` org (e.g., `codethon-yourname`)
4. Vercel will auto-detect it's a Vite + React app — click **Deploy**
5. Done! 🎉 Your site is now live.

### What it sets up:
- Automatic deployment from the `main` or `dev` branch
- Custom preview URLs for every PR
- Performance-optimized static hosting

> Any future push to your repo will automatically trigger a new deployment

---

## Questions?

Reach out on `#product-design-internal` Slack channel. Happy coding, and bring your designs to life ✨
