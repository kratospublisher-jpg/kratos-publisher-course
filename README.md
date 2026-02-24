# Kratos Publisher — Christian Book Publishing Course

A production-ready course platform for Christian authors, built with Node.js/Express and Supabase authentication.

## 🚀 Go Live in 4 Steps

### Step 1: Supabase Setup (5 min)

1. Go to [supabase.com](https://supabase.com) → **New Project**
2. Copy your **Project URL** and **anon public key** from Settings → API
3. Go to **SQL Editor** → paste the contents of `supabase-setup.sql` → **Run**
4. In **Authentication → URL Configuration**, add your Railway URL to "Redirect URLs" after deploy

### Step 2: Add Supabase Credentials to the App

Open `public/index.html` and find this section (around line 470):

```javascript
const SUPABASE_URL = window.SUPABASE_URL || '';
const SUPABASE_ANON_KEY = window.SUPABASE_ANON_KEY || '';
```

Replace with your Supabase credentials:

```javascript
const SUPABASE_URL = 'https://your-project-id.supabase.co';
const SUPABASE_ANON_KEY = 'your-anon-key-here';
```

Also update `server.js` line 17 with your Supabase URL for the Content Security Policy.

### Step 3: Push to GitHub

```bash
cd kratos-course
git init
git add .
git commit -m "Initial commit - Kratos Publisher Course Platform"
git remote add origin https://github.com/YOUR_USERNAME/kratos-publisher-course.git
git push -u origin main
```

### Step 4: Deploy on Railway (2 min)

1. Go to [railway.app](https://railway.app) → **New Project** → **Deploy from GitHub Repo**
2. Select your `kratos-publisher-course` repo
3. Railway auto-detects the `Dockerfile` or Node.js setup
4. Add environment variables in Railway dashboard:
   - `PORT` = `3000`
   - `NODE_ENV` = `production`
5. Click **Deploy** → Railway gives you a `.railway.app` URL
6. (Optional) Add a custom domain in Railway Settings → Domains

## 📁 Project Structure

```
kratos-course/
├── public/
│   ├── index.html          # Full course platform (SPA)
│   └── images/
│       └── logo.jpg        # Kratos logo
├── server.js               # Express server
├── package.json            # Dependencies
├── railway.toml            # Railway config
├── Dockerfile              # Container config
├── supabase-setup.sql      # Database migration
├── .env.example            # Environment template
└── README.md               # This file
```

## 🎨 Brand Colors (from logo)

| Color   | Hex       | Usage            |
|---------|-----------|------------------|
| Orange  | `#FF8C00` | Module 1, CTAs   |
| Yellow  | `#FFD700` | Module 4, accents|
| Cyan    | `#00D4FF` | Primary accent   |
| Red     | `#FF1744` | Module 5, alerts |
| Blue    | `#2979FF` | Module 3, links  |
| Magenta | `#FF00FF` | Module 6, accents|

## ✨ Features

- **18 lessons** across 6 modules with expandable content
- **Progress tracking** with localStorage + Supabase cloud sync
- **Authentication** via Supabase (email/password)
- **Dark theme** matching Kratos brand identity
- **Fully responsive** — works on mobile, tablet, desktop
- **Production-ready** — compression, helmet security, CORS

## 🔧 Local Development

```bash
npm install
npm start
# Visit http://localhost:3000
```

## 📝 Customization

- **Add lesson content**: Expand the `courseData` array in `index.html`
- **Add video**: Embed YouTube/Vimeo in lesson content sections
- **Add payments**: Integrate Stripe via Supabase Edge Functions
- **Custom domain**: Add in Railway Settings → Domains
