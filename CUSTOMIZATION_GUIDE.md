# Customization Guide

This guide will help you personalize your portfolio site with your own content, style, and branding.

## Step-by-Step Customization

### Step 1: Basic Information

#### Edit `hugo.toml`:

```toml
title = 'John Doe - Developer & Creator'  # Change this

[params]
  author = 'John Doe'  # Your name
  description = 'Full-stack developer, photographer, and avid reader'  # Your tagline
  email = 'john.doe@example.com'  # Your email
  phone = '+1-555-123-4567'  # Your phone
```

### Step 2: Social Media Links

#### Update social links in `hugo.toml`:

```toml
[params.social]
  twitter = 'https://twitter.com/johndoe'
  linkedin = 'https://linkedin.com/in/johndoe'
  github = 'https://github.com/johndoe'
  instagram = 'https://instagram.com/johndoe'
  youtube = 'https://youtube.com/@johndoe'
```

To add more social platforms, edit:
1. `hugo.toml` - Add new social links
2. `themes/personal/layouts/index.html` - Add new social cards
3. `themes/personal/layouts/_default/social.html` - Add new widget sections

### Step 3: About Me Page

#### Edit `content/about.md`:

Replace the placeholder text with your actual information:

- **Who I Am**: Your introduction and current role
- **My Career**: Professional background and achievements
- **My Philosophy**: Your values and approach to work/life
- **My Hobbies**: What you enjoy doing in your free time

Example:

```markdown
## Who I Am

I'm a full-stack developer based in San Francisco, passionate about building 
elegant solutions to complex problems. When I'm not coding, you'll find me 
exploring the city with my camera or diving into a good sci-fi novel.
```

### Step 4: Things I Do - Tech Section

#### Edit `content/things-i-do/tech.md`:

Update with your actual:
- Technologies you work with
- Programming languages you know
- Projects you've built
- Skills and expertise

Example:

```markdown
### Skills

- **Languages**: Python, JavaScript, TypeScript, Ruby
- **Frameworks**: React, Django, Ruby on Rails, Next.js
- **Tools**: Docker, Kubernetes, AWS, PostgreSQL

### Recent Projects

#### E-commerce Platform
Built a scalable e-commerce platform serving 100k+ users using React and Django.

#### Open Source Library
Created and maintain a popular React component library with 5k+ GitHub stars.
```

### Step 5: Things I Do - Other Sections

#### Reading (`content/things-i-do/reading.md`):
- Add books you're currently reading
- Write actual book reviews
- Share your reading goals

#### Writing (`content/things-i-do/writing.md`):
- Link to published articles
- Showcase your writing projects
- Share work in progress

#### Photography (`content/things-i-do/photography.md`):
- Describe your photography style
- Add your actual equipment
- Link to photo galleries

### Step 6: Add Your Photos

1. **Get a featured photo** (800x400px recommended):
   - Place it in `static/images/profile-featured.jpg`
   - Or update the path in `themes/personal/layouts/index.html`

2. **Add more photos**:
   - Place them in `static/images/`
   - Reference in markdown: `![Description](/images/photo.jpg)`

3. **Optimize images**:
   - Compress images for web
   - Use appropriate dimensions
   - Consider using WebP format

### Step 7: Color Scheme

#### Edit `themes/personal/static/css/style.css`:

Change the color variables at the top:

```css
:root {
  --primary-color: #2c3e50;      /* Main brand color */
  --secondary-color: #3498db;    /* Accent color */
  --accent-color: #e74c3c;       /* Highlight color */
  --text-color: #333;            /* Body text */
  --text-light: #666;            /* Secondary text */
  --bg-color: #fff;              /* Background */
  --bg-light: #f8f9fa;          /* Light background */
}
```

**Color Scheme Ideas:**

- **Professional Blue**: `#1e3a8a`, `#3b82f6`, `#60a5fa`
- **Creative Purple**: `#6b21a8`, `#a855f7`, `#c084fc`
- **Warm & Friendly**: `#ea580c`, `#f97316`, `#fb923c`
- **Minimalist Gray**: `#1f2937`, `#4b5563`, `#6b7280`
- **Nature Green**: `#065f46`, `#059669`, `#10b981`

### Step 8: Typography

Want to change fonts?

1. **Add Google Fonts** to `themes/personal/layouts/_default/baseof.html`:

```html
<head>
  ...
  <link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
</head>
```

2. **Update CSS variables**:

```css
:root {
  --font-serif: 'Merriweather', 'Georgia', serif;
  --font-sans: 'Open Sans', -apple-system, sans-serif;
}
```

### Step 9: Contact Page

#### Edit `content/contact.md`:

1. Update email and phone number
2. Add your location
3. Update FAQs with your actual answers
4. Adjust availability and response times

### Step 10: Social Media Widgets

#### For Twitter:

1. Go to [publish.twitter.com](https://publish.twitter.com/)
2. Enter your Twitter URL
3. Choose "Embedded Timeline"
4. Copy the code
5. Paste into `themes/personal/layouts/_default/social.html` in the Twitter widget section

#### For Instagram:

1. Use a service like [SnapWidget](https://snapwidget.com/)
2. Create a widget
3. Copy the embed code
4. Paste into the Instagram widget section

#### For YouTube:

1. Go to your YouTube channel
2. Click "Customize channel"
3. Get embed code for channel/playlist
4. Paste into the YouTube widget section

## Advanced Customization

### Adding Blog Functionality

1. Create blog section:
   ```bash
   hugo new blog/_index.md
   ```

2. Add list template:
   Create `themes/personal/layouts/blog/list.html`

3. Add blog posts:
   ```bash
   hugo new blog/my-first-post.md
   ```

### Adding Comments

Using utterances (GitHub-based):

1. Install utterances app on your repo
2. Add script to your single post template:
   ```html
   <script src="https://utteranc.es/client.js"
           repo="yourusername/your-repo"
           issue-term="pathname"
           theme="github-light"
           crossorigin="anonymous"
           async>
   </script>
   ```

### Adding Analytics

#### Google Analytics:

1. Get your GA tracking ID
2. Add to `hugo.toml`:
   ```toml
   [params]
     googleAnalytics = "G-XXXXXXXXXX"
   ```
3. Add tracking code to `baseof.html`

#### Plausible Analytics (Privacy-friendly):

1. Sign up at plausible.io
2. Add script to `baseof.html`:
   ```html
   <script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
   ```

### Adding Search

Use Lunr.js for client-side search:

1. Generate search index during build
2. Add search box to navigation
3. Implement search results page

### Dark Mode

1. Add dark mode CSS variables
2. Create toggle button
3. Use JavaScript to switch themes
4. Store preference in localStorage

## Testing Your Changes

After each change:

1. **Check locally**: `hugo server -D`
2. **Test on mobile**: Use browser dev tools
3. **Validate HTML**: Use W3C validator
4. **Check performance**: Use Lighthouse
5. **Test all links**: Ensure nothing is broken

## Getting Help

If you need help customizing:

1. Check [Hugo documentation](https://gohugo.io/documentation/)
2. Look at [Hugo themes](https://themes.gohugo.io/) for inspiration
3. Ask on [Hugo Discourse](https://discourse.gohugo.io/)
4. Search Stack Overflow

## Checklist

Before going live:

- [ ] Updated all personal information
- [ ] Added real content to all pages
- [ ] Uploaded featured photo and other images
- [ ] Tested all links
- [ ] Updated social media links
- [ ] Customized colors to match your brand
- [ ] Tested on mobile devices
- [ ] Added analytics
- [ ] Set up contact form (if desired)
- [ ] Optimized images for web
- [ ] Tested page load speed
- [ ] Added favicon
- [ ] Checked spelling and grammar
- [ ] Configured domain name
- [ ] Set up SSL certificate

## Next Steps

Once your site is live:

1. **Share it** on your social media
2. **Add it** to your email signature
3. **Link it** from your other profiles
4. **Update regularly** with new content
5. **Monitor** analytics to see what's popular
6. **Gather feedback** from friends and colleagues
7. **Iterate and improve** based on feedback

---

Enjoy building your personal brand online! 🚀

