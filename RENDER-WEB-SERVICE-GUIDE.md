# 🌐 Step-by-Step: Create Web Service on Render

This guide will walk you through creating your web service on Render, step by step.

---

## 📍 Where You Are

You've already:
- ✅ Created your PostgreSQL database on Render
- ✅ Copied the Internal Database URL
- ✅ Now you need to create the Web Service

---

## 🚀 Step 1: Click "New +" → "Web Service"

1. **Look at the top right** of your Render dashboard
2. You'll see a blue button that says **"New +"**
3. **Click on it**
4. A dropdown menu will appear
5. **Click on "Web Service"** (it's usually the first option)

**What you'll see:** A page asking you to connect a Git repository

---

## 🔗 Step 2: Connect Your GitHub Repository

You'll see a list of your GitHub repositories. Here's what to do:

### Option A: If You See Your Repository Listed

1. **Look for**: `placidegithub/kingsalomon-academy` (or `kingsalomon/kingsalomon-academy` if you created it)
2. **Click on it** to select it
3. Click the **"Connect"** button

### Option B: If You Don't See Your Repository

1. Click **"Configure account"** or **"Connect GitHub"**
2. Authorize Render to access your repositories
3. Refresh the page
4. Your repository should now appear
5. Click on it and then **"Connect"**

**What happens next:** You'll see a form with settings to fill in

---

## ⚙️ Step 3: Fill in the Settings

You'll see a form with several fields. Fill them in **exactly** as shown:

### Field 1: Name
- **Find the field labeled "Name"** (usually at the top)
- **Type exactly**: `kingsalomon-academy`
- (This is what your app will be called on Render)

### Field 2: Region
- **Find the "Region" dropdown**
- **Select the SAME region** where you created your database
  - If your database is in "Frankfurt (EU Central)", choose that
  - If your database is in "Ireland (EU West)", choose that
- **Important:** It MUST be the same region as your database!

### Field 3: Branch
- **Find the "Branch" field**
- It should already say `main` or `master`
- **Leave it as is** (don't change it)

### Field 4: Root Directory
- **Find "Root Directory"** field
- **Leave it EMPTY** (don't type anything)
- This tells Render your code is in the root of the repository

### Field 5: Environment
- **Find "Environment" dropdown**
- **Select**: `Python 3`
- (This tells Render you're using Python)

### Field 6: Build Command
- **Find "Build Command"** field
- **Type exactly** (copy and paste this):
  ```
  pip install -r requirements.txt
  ```
- This tells Render to install all your Python packages

### Field 7: Start Command
- **Find "Start Command"** field
- **Type exactly** (copy and paste this):
  ```
  gunicorn --bind 0.0.0.0:$PORT wsgi:app
  ```
- This tells Render how to start your app

### Field 8: Plan
- **Find "Plan" section**
- **Select**: `Free` (it should be selected by default)
- This is the free tier

---

## 📝 Step 4: Scroll Down to Environment Variables

1. **Scroll down** on the page
2. Look for a section called **"Environment Variables"** or **"Environment"**
3. You'll see a button that says **"Add Environment Variable"** or **"Add"**
4. **Click it** to add your first variable

---

## 🔐 Step 5: Add Environment Variables (One by One)

You need to add **4 variables**. Add them **one at a time**:

### Variable 1: FLASK_ENV

1. Click **"Add Environment Variable"**
2. A form will appear with two fields:
   - **Key** (left field): Type: `FLASK_ENV`
   - **Value** (right field): Type: `production`
3. Click **"Add"** or **"Save"**

### Variable 2: SECRET_KEY

1. Click **"Add Environment Variable"** again
2. **Key**: Type: `SECRET_KEY`
3. **Value**: 
   - Open the file `.env.template` in your project folder
   - Find the line that says `SECRET_KEY=...`
   - Copy everything after the `=` sign
   - Paste it in the Value field
   - It should look like: `-{18FH1KKA-i=[FYkYacF,S*8{0LU-YbD"Ip#TvC`[G6k25w#V`
4. Click **"Add"** or **"Save"**

### Variable 3: DATABASE_URL

1. Click **"Add Environment Variable"** again
2. **Key**: Type: `DATABASE_URL`
3. **Value**: 
   - Paste the **Internal Database URL** you copied earlier
   - It should start with: `postgresql://`
   - It should look like: `postgresql://kingsalomon_user:password@dpg-xxxxx-a.frankfurt-postgres.render.com/kingsalomon_academy`
4. Click **"Add"** or **"Save"**

### Variable 4: PORT

1. Click **"Add Environment Variable"** again
2. **Key**: Type: `PORT`
3. **Value**: Type: `10000`
4. Click **"Add"** or **"Save"**

**After adding all 4 variables, you should see them listed like this:**
```
FLASK_ENV = production
SECRET_KEY = (your long secret key)
DATABASE_URL = (your database URL)
PORT = 10000
```

---

## ✅ Step 6: Click "Create Web Service"

1. **Scroll to the bottom** of the page
2. Look for a big blue button that says **"Create Web Service"**
3. **Click it**
4. Render will start deploying your app!

---

## ⏳ Step 7: Wait for Deployment (5-10 minutes)

After clicking "Create Web Service", you'll see:

### What Happens:

1. **Build Logs Appear**
   - You'll see text scrolling showing what Render is doing
   - It will say things like:
     - "Collecting Flask..."
     - "Installing packages..."
     - "Building application..."

2. **Build Process** (3-5 minutes)
   - Render installs all your Python packages
   - It builds your application
   - You'll see: `Successfully installed Flask...`

3. **Starting Service** (1-2 minutes)
   - Render starts your application
   - You'll see: `Starting gunicorn...`
   - Then: `Application is live!`

4. **Success!** ✅
   - You'll see: **"Your service is live at: https://kingsalomon-academy.onrender.com"**
   - **Copy this URL!** This is your live website!

---

## 🎯 Visual Guide - What Each Field Looks Like

```
┌─────────────────────────────────────────┐
│ Name: [kingsalomon-academy        ]     │
│                                         │
│ Region: [Frankfurt (EU Central) ▼]     │
│                                         │
│ Branch: [main                    ]      │
│                                         │
│ Root Directory: [              ]       │
│                                         │
│ Environment: [Python 3          ▼]     │
│                                         │
│ Build Command:                          │
│ [pip install -r requirements.txt]       │
│                                         │
│ Start Command:                          │
│ [gunicorn --bind 0.0.0.0:$PORT wsgi:app]│
│                                         │
│ Plan: ○ Free  ● Starter  ○ Standard    │
└─────────────────────────────────────────┘
```

---

## 🔍 Environment Variables Section

After scrolling down, you'll see:

```
Environment Variables
┌─────────────────────────────────────┐
│ Key              Value              │
├─────────────────────────────────────┤
│ FLASK_ENV        production         │
│ SECRET_KEY       (your key)         │
│ DATABASE_URL     (your URL)         │
│ PORT             10000               │
└─────────────────────────────────────┘
[+ Add Environment Variable]
```

---

## ⚠️ Common Mistakes to Avoid

1. **Wrong Region**: Make sure it matches your database region!
2. **Wrong Build Command**: Must be exactly `pip install -r requirements.txt`
3. **Wrong Start Command**: Must be exactly `gunicorn --bind 0.0.0.0:$PORT wsgi:app`
4. **Missing Environment Variables**: Add all 4!
5. **Wrong DATABASE_URL**: Must be the "Internal Database URL", not the external one

---

## 🆘 If Something Goes Wrong

### Problem: Can't find my repository
- **Solution**: Click "Configure account" and reconnect GitHub

### Problem: Build fails
- **Solution**: Check the logs - look for error messages. Common issues:
  - Missing dependency in requirements.txt
  - Syntax error in code
  - Wrong Python version

### Problem: Service won't start
- **Solution**: 
  - Check environment variables are all set
  - Verify DATABASE_URL is correct
  - Check logs for error messages

### Problem: Can't add environment variable
- **Solution**: Make sure you clicked "Add Environment Variable" button first

---

## ✅ Checklist - Before Clicking "Create Web Service"

Make sure you have:
- [ ] Name: `kingsalomon-academy`
- [ ] Region: Same as your database
- [ ] Build Command: `pip install -r requirements.txt`
- [ ] Start Command: `gunicorn --bind 0.0.0.0:$PORT wsgi:app`
- [ ] Plan: Free
- [ ] FLASK_ENV = production
- [ ] SECRET_KEY = (from .env.template)
- [ ] DATABASE_URL = (from your database)
- [ ] PORT = 10000

**If all checked, you're ready to deploy!** 🚀

---

## 🎉 After Deployment

Once you see "Your service is live at...", you're done!

1. **Copy the URL** (e.g., `https://kingsalomon-academy.onrender.com`)
2. **Visit it in your browser**
3. **Wait 30-60 seconds** (first visit wakes up the app)
4. **You should see your homepage!** ✅

---

**Need help with a specific step?** Tell me which step you're on and I'll help you! 💪

