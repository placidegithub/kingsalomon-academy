# 🚀 Do This Right Now - Step by Step

Follow these steps **in order**. I'll guide you through each one!

---

## ✅ Step 1: Commit Your Code (2 minutes)

**Open Command Prompt** in your project folder and run:

```bash
git commit -m "Ready for deployment - all files prepared"
git push
```

**What this does:** Saves all the prepared files and pushes them to GitHub.

**If you get an error:** Tell me what the error says and I'll help fix it!

---

## ✅ Step 2: Create GitHub Account (5 minutes)

1. Go to: **https://github.com/signup**
2. Enter your email: **placidehenry0@gmail.com**
3. Create a password
4. Username: **kingsalomon** (or if taken, use what GitHub suggests)
5. Verify your email

**Done?** Tell me and we'll move to Step 3!

---

## ✅ Step 3: Create Repository (2 minutes)

1. After logging into GitHub, click the **"+"** icon (top right)
2. Click **"New repository"**
3. Name: **kingsalomon-academy**
4. Click **"Create repository"**

**Done?** Tell me and we'll move to Step 4!

---

## ✅ Step 4: Push Code (3 minutes)

In Command Prompt, run:

```bash
git remote set-url origin https://github.com/kingsalomon/kingsalomon-academy.git
git push -u origin main
```

(If you used a different username, replace "kingsalomon" with your username)

**Done?** Tell me and we'll move to Step 5!

---

## ✅ Step 5: Sign Up for Render (3 minutes)

1. Go to: **https://render.com**
2. Click **"Get Started for Free"**
3. Click **"Sign up with GitHub"**
4. Authorize Render

**Done?** Tell me and we'll move to Step 6!

---

## ✅ Step 6: Create Database (5 minutes)

1. In Render, click **"New +"** → **"PostgreSQL"**
2. Name: **kingsalomon-db**
3. Region: **Frankfurt (EU Central)** or **Ireland (EU West)**
4. Plan: **Free**
5. Click **"Create Database"**
6. Wait 2-3 minutes
7. Click on the database
8. **Copy the "Internal Database URL"** - you'll need this!

**Done?** Tell me you copied the database URL and we'll move to Step 7!

---

## ✅ Step 7: Create Web Service (10 minutes)

1. Click **"New +"** → **"Web Service"**
2. Connect your GitHub repository: **kingsalomon/kingsalomon-academy**
3. Settings:
   - Name: **kingsalomon-academy**
   - Region: Same as database
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn --bind 0.0.0.0:$PORT wsgi:app`
   - Plan: **Free**
4. Scroll down to **"Environment Variables"**
5. Add these variables (one by one):
   - `FLASK_ENV` = `production`
   - `SECRET_KEY` = (from .env.template file)
   - `DATABASE_URL` = (paste the database URL you copied)
   - `PORT` = `10000`
6. Click **"Create Web Service"**
7. Wait 5-10 minutes for deployment

**Done?** Your app will be live! 🎉

---

## 🎉 Step 8: Test Your App (2 minutes)

1. Visit: **https://kingsalomon-academy.onrender.com**
2. Wait 30-60 seconds (first visit wakes up the app)
3. Login with:
   - Username: **admin**
   - Password: **admin123**
4. **Change the password immediately!**

**Congratulations! Your app is live!** 🚀

---

## 💬 Need Help?

At any step, just tell me:
- "I'm on Step X"
- "I got an error: [error message]"
- "What do I do next?"

I'll help you immediately!

---

**Ready to start?** Begin with Step 1 and tell me when you're done with each step!

