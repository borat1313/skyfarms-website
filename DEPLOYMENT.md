# SkyFarms Website Deployment Guide

This guide walks you through hosting your SkyFarms website on Vercel with a custom domain (no Claude in the URL).

---

## Option 1: Deploy via GitHub + Vercel (Recommended)

**Why GitHub + Vercel?**
- GitHub keeps your code backed up
- Vercel auto-deploys whenever you push changes
- Clean URLs and fast CDN
- Free tier is generous
- Easy to invite team members

### Step 1: Create a GitHub Repository

1. Go to **github.com** and sign in (create account if needed)
2. Click **New Repository** (green button, top right)
3. Repository name: `skyfarms-website`
4. Description: `SkyFarms website — CEA platform`
5. Choose **Public** (or Private if you prefer)
6. **Do NOT** initialize with README (we already have one)
7. Click **Create Repository**

### Step 2: Upload Your Files to GitHub

GitHub gives you two options. **Option A is easier if you're not comfortable with Git:**

#### Option A: Drag & Drop (Easiest)
1. On your new repo page, you'll see "uploading an existing file"
2. Click that link (or drag files into the empty repo area)
3. Select all files from your `skyfarms-site/` folder:
   - `index.html`
   - `technology.html`
   - `farms.html`
   - `investors.html`
   - `partner.html`
   - `styles.css`
   - `_redirects`
   - `vercel.json`
   - `.gitignore`
   - `README.md`
4. Commit message: `Initial commit: SkyFarms website`
5. Click **Commit changes**

#### Option B: Command Line (If you have Git installed)
```bash
# In your skyfarms-site folder
git init
git add .
git commit -m "Initial commit: SkyFarms website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/skyfarms-website.git
git push -u origin main
```

### Step 3: Deploy to Vercel

1. Go to **vercel.com** and sign in (use GitHub account)
2. Click **New Project**
3. Under "Import Git Repository", click **GitHub** and authorize Vercel
4. Find and click your `skyfarms-website` repo
5. Click **Import**
6. Leave all settings at default (Vercel auto-detects static site)
7. Click **Deploy**

Done! Vercel gives you a URL like `skyfarms-website.vercel.app`

### Step 4 (Optional): Add Your Custom Domain

1. In Vercel project dashboard, go to **Settings → Domains**
2. Click **Add Domain**
3. Enter your domain (e.g., `skyfarms.ca`)
4. Vercel shows you DNS settings
5. Go to your domain registrar (GoDaddy, Namecheap, etc.)
6. Update DNS to point to Vercel (follow Vercel's instructions on screen)
7. Wait 5–30 minutes for DNS to propagate

**Now your site lives at your custom domain with zero Claude branding.**

---

## Option 2: Vercel Direct (No GitHub)

If you want to skip GitHub:

1. Go to **vercel.com**
2. Click **New Project**
3. Upload your files directly (no Git needed)
4. Vercel deploys immediately
5. (Still add a custom domain in Step 4 above)

---

## Option 3: Netlify (Similar to Vercel)

If you prefer Netlify over Vercel:

1. Go to **netlify.com** and sign up
2. Click **Add New Site → Import an Existing Project**
3. Connect GitHub (or drag-and-drop files)
4. Netlify auto-detects and deploys
5. Same custom domain option in settings

---

## Making Updates

Once deployed:

**If using GitHub:**
- Edit files in your repo
- Commit and push changes
- Vercel auto-deploys (usually within 60 seconds)

**If using direct Vercel upload:**
- Go to Vercel dashboard
- Redeploy or upload new files

---

## What Your Team Will See

Your final URL will look like:
- `https://skyfarms.ca` (if you add your domain)
- `https://skyfarms-website.vercel.app` (Vercel default)

**Not:** `https://claude.ai/...` or anything with "Claude" in it.

When you present this to your team, you're presenting *your site*, on *your domain*, with *your branding*.

---

## OG Images (Social Preview Cards)

Right now your pages reference `/og/og-{page}.jpg` for LinkedIn, Twitter, etc.

To add these:

1. Create 1200×630 PNG/JPG images for:
   - `og-home.jpg`
   - `og-investors.jpg`
   - `og-partner.jpg`
   - `og-technology.jpg`
   - `og-farms.jpg`

2. Upload them to your site:
   - Push an `/og/` folder with all 5 images to your repo
   - Or upload via Vercel dashboard

3. That's it—social shares will now show your custom images.

---

## Questions?

- **Vercel docs**: https://vercel.com/docs
- **GitHub docs**: https://docs.github.com
- **Domain setup help**: Your domain registrar's support team

Good luck! 🚀
