# Quick Start Guide 🚀

Get your personal portfolio site up and running in 5 minutes!

## Prerequisites

You need Hugo installed. Check if you have it:

```bash
hugo version
```

If not installed:

**macOS:**
```bash
brew install hugo
```

**Windows (Chocolatey):**
```bash
choco install hugo-extended
```

**Linux (Snap):**
```bash
snap install hugo
```

## Launch Your Site (3 Steps)

### 1. Navigate to the project
```bash
cd /Users/himelnagrana/Projects/ifelseandetc
```

### 2. Start the development server
```bash
hugo server -D
```

### 3. Open your browser
Go to: **http://localhost:1313**

That's it! Your site is running! 🎉

## What You'll See

- **Homepage** with newspaper-style layout
- **About Me** section
- **Things I Do** widgets (Tech, Reading, Writing, Photography)
- **Other Worlds** social media section
- **Contact** page

## Next Steps

### Customize Your Site

1. **Update your info** in `hugo.toml`
2. **Edit content** in `content/` folder
3. **Add your photo** to `static/images/profile-featured.jpg`
4. **Customize colors** in `themes/personal/static/css/style.css`

See `CUSTOMIZATION_GUIDE.md` for detailed instructions.

### Build for Production

When ready to deploy:

```bash
hugo
```

This creates a `public/` folder with your static site.

### Deploy

Upload the `public/` folder to:
- **Netlify** (recommended - connects to Git)
- **Vercel** (great for Hugo)
- **GitHub Pages**
- **Any web host**

## Need Help?

- Read the full `README.md`
- Check `CUSTOMIZATION_GUIDE.md`
- Visit [Hugo Documentation](https://gohugo.io/documentation/)

---

**Enjoy building your personal brand! 🌟**

