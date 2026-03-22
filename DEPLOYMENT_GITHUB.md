# GitHub Hosting Guide 🚀

Complete guide to host your Hugo site on GitHub (code + live site).

## Part 1: Push Your Code to GitHub

### Step 1: Initialize Git (if not already done)

```bash
cd /Users/himelnagrana/Projects/ifelseandetc
git init
git add .
git commit -m "Initial commit: Personal portfolio site"
```

### Step 2: Create GitHub Repository

1. Go to [github.com](https://github.com)
2. Click the **+** icon (top right) → **New repository**
3. Name it: `ifelseandetc` (or any name you prefer)
4. **Don't** initialize with README (you already have one)
5. Click **Create repository**

### Step 3: Connect and Push

Replace `YOUR_USERNAME` with your GitHub username:

```bash
git remote add origin https://github.com/YOUR_USERNAME/ifelseandetc.git
git branch -M main
git push -u origin main
```

✅ **Your code is now on GitHub!**

---

## Part 2: Deploy Your Live Site

You have **3 options** for hosting:

### Option A: GitHub Pages with GitHub Actions (Recommended ⭐)

This automatically builds and deploys your site when you push changes.

#### Setup:

1. **Enable GitHub Pages:**
   - Go to your repo → **Settings** → **Pages**
   - Under "Source", select **GitHub Actions**

2. **Create workflow file** (already created below - see `.github/workflows/hugo.yml`)

3. **Push the workflow:**
   ```bash
   git add .github/workflows/hugo.yml
   git commit -m "Add GitHub Actions workflow for Hugo"
   git push
   ```

4. **Wait for deployment** (~1-2 minutes)
   - Go to **Actions** tab to see build progress
   - Once complete, your site will be live!

5. **Access your site:**
   ```
   https://YOUR_USERNAME.github.io/ifelseandetc/
   ```

**Note:** Update `baseURL` in `hugo.toml`:
```toml
baseURL = 'https://YOUR_USERNAME.github.io/ifelseandetc/'
```

---

### Option B: Netlify (Easiest, Custom Domain Support)

1. Go to [netlify.com](https://www.netlify.com/)
2. Sign up/Login with GitHub
3. Click **Add new site** → **Import an existing project**
4. Choose your GitHub repo
5. Configure:
   - **Build command:** `hugo`
   - **Publish directory:** `public`
   - **Hugo version:** Add environment variable:
     - Key: `HUGO_VERSION`
     - Value: `0.120.0` (or latest)
6. Click **Deploy site**

✅ **Your site is live!** Netlify gives you a URL like: `your-site.netlify.app`

**Bonus:** You can add a custom domain in Netlify settings.

---

### Option C: Vercel (Fast, Modern)

1. Go to [vercel.com](https://vercel.com/)
2. Sign up/Login with GitHub
3. Click **Add New** → **Project**
4. Import your GitHub repo
5. Vercel auto-detects Hugo:
   - Framework: Hugo
   - Build command: `hugo`
   - Output directory: `public`
6. Click **Deploy**

✅ **Live in seconds!** URL: `your-site.vercel.app`

---

## Option A Details: GitHub Actions Workflow

The workflow file `.github/workflows/hugo.yml` will:
- ✅ Automatically build your site when you push
- ✅ Deploy to GitHub Pages
- ✅ No manual building needed

### Workflow Features:

- **Trigger:** Runs on push to `main` branch
- **Hugo Version:** Latest stable
- **Build:** Compiles your Hugo site
- **Deploy:** Publishes to GitHub Pages

---

## Custom Domain Setup

### For GitHub Pages:

1. Buy a domain (Namecheap, Google Domains, etc.)
2. Add DNS records:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   
   Type: A
   Name: @
   Value: 185.199.109.153
   
   Type: A
   Name: @
   Value: 185.199.110.153
   
   Type: A
   Name: @
   Value: 185.199.111.153
   
   Type: CNAME
   Name: www
   Value: YOUR_USERNAME.github.io
   ```
3. In GitHub repo → Settings → Pages → Custom domain
4. Enter your domain and save
5. Enable **Enforce HTTPS**

### For Netlify/Vercel:

1. Go to site settings → Domain settings
2. Add your custom domain
3. Follow DNS configuration instructions
4. SSL is automatic!

---

## Updating Your Site

After initial setup, updating is simple:

```bash
# Edit your content files
# Then commit and push:

git add .
git commit -m "Updated about page"
git push
```

- **GitHub Actions:** Deploys automatically in 1-2 minutes
- **Netlify/Vercel:** Deploys automatically in 30-60 seconds

---

## Important: Update baseURL

Based on your hosting choice, update `hugo.toml`:

**GitHub Pages:**
```toml
baseURL = 'https://YOUR_USERNAME.github.io/ifelseandetc/'
```

**Netlify:**
```toml
baseURL = 'https://your-site.netlify.app/'
```

**Vercel:**
```toml
baseURL = 'https://your-site.vercel.app/'
```

**Custom Domain:**
```toml
baseURL = 'https://yourdomain.com/'
```

---

## Troubleshooting

### Site looks broken (no CSS):

**Problem:** Wrong `baseURL` in `hugo.toml`

**Solution:** Make sure `baseURL` matches your site URL exactly

### GitHub Actions failing:

1. Check Actions tab for error logs
2. Verify repo has Pages enabled
3. Ensure workflow file is in `.github/workflows/`

### 404 errors:

- Check that `public/` folder is being generated
- Verify all links use absolute paths starting with `/`
- Check file names match (case-sensitive)

### Build fails:

- Check Hugo version compatibility
- Look at build logs for specific errors
- Test locally: `hugo` (should build without errors)

---

## Quick Command Reference

```bash
# Local development
hugo server -D

# Build site locally
hugo

# Git commands
git status                    # Check changes
git add .                     # Stage all changes
git commit -m "message"       # Commit changes
git push                      # Push to GitHub

# Create new branch
git checkout -b feature-name
git push -u origin feature-name
```

---

## Recommended: GitHub Pages Setup

**Pros:**
✅ Free forever  
✅ Automatic builds with Actions  
✅ Direct GitHub integration  
✅ SSL/HTTPS included  
✅ Custom domain support  

**Cons:**
❌ Slightly slower than Netlify/Vercel  
❌ More manual setup initially  

---

## Next Steps

1. ✅ Push code to GitHub
2. ✅ Choose hosting option (GitHub Pages/Netlify/Vercel)
3. ✅ Update `baseURL` in `hugo.toml`
4. ✅ Test your live site
5. ✅ Share your URL!

**Need help?** Check the troubleshooting section or GitHub Actions logs.

---

*Your site will be live and automatically updated every time you push to GitHub!* 🎉

