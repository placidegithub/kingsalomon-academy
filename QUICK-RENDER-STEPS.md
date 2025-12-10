# ⚡ Quick Reference - Render Web Service Setup

## 🎯 Quick Steps (Copy/Paste Ready)

### Step 1: Click "New +" → "Web Service"

### Step 2: Connect Repository
- Find: `placidegithub/kingsalomon-academy` (or your repo name)
- Click "Connect"

### Step 3: Settings (Fill These Exactly)

**Name:**
```
kingsalomon-academy
```

**Region:**
```
[Same as your database - Frankfurt or Ireland]
```

**Build Command:**
```
pip install -r requirements.txt
```

**Start Command:**
```
gunicorn --bind 0.0.0.0:$PORT wsgi:app
```

**Plan:**
```
Free
```

### Step 4: Environment Variables (Add These 4)

**Variable 1:**
- Key: `FLASK_ENV`
- Value: `production`

**Variable 2:**
- Key: `SECRET_KEY`
- Value: (Copy from `.env.template` file)

**Variable 3:**
- Key: `DATABASE_URL`
- Value: (Paste your Internal Database URL)

**Variable 4:**
- Key: `PORT`
- Value: `10000`

### Step 5: Click "Create Web Service"

### Step 6: Wait 5-10 minutes

### Step 7: Copy your app URL when it says "Your service is live at..."

---

## 📋 Where to Find Things

**SECRET_KEY:**
- File: `.env.template` in your project folder
- Look for: `SECRET_KEY=...`
- Copy everything after the `=`

**DATABASE_URL:**
- Render Dashboard → Your Database → "Internal Database URL"
- Copy the entire URL (starts with `postgresql://`)

---

## ✅ Quick Checklist

- [ ] Repository connected
- [ ] Name set to `kingsalomon-academy`
- [ ] Region matches database
- [ ] Build Command: `pip install -r requirements.txt`
- [ ] Start Command: `gunicorn --bind 0.0.0.0:$PORT wsgi:app`
- [ ] Plan: Free
- [ ] All 4 environment variables added
- [ ] Clicked "Create Web Service"
- [ ] Waiting for deployment...

---

**That's it!** Follow these steps and your app will be live! 🚀

