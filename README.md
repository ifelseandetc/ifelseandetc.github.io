# Personal Portfolio Site

A markdown-based personal portfolio website built with Hugo, featuring a newspaper-style design with widgets for showcasing your work, blogs, photography, and social presence.

## Features

✅ **Markdown-based** - Easy to maintain and update  
✅ **Newspaper Design** - Elegant masthead and column layouts  
✅ **Widget Layout** - Homepage with beautiful widget sections  
✅ **Responsive** - Works perfectly on all devices  
✅ **Fast & Lightweight** - Built with Hugo static site generator  
✅ **Easy Customization** - Simple configuration and styling  

## Quick Start

### Prerequisites

1. Install Hugo (extended version recommended):
   ```bash
   # macOS
   brew install hugo
   
   # Windows (using Chocolatey)
   choco install hugo-extended
   
   # Linux
   snap install hugo
   ```

### Running the Site

1. **Start the Hugo development server:**
   ```bash
   hugo server -D
   ```

2. **Open your browser and visit:**
   ```
   http://localhost:1313
   ```

3. **The site will auto-reload when you make changes!**

### Building for Production

To generate the static site for deployment:

```bash
hugo
```

This creates a `public/` directory with all your static files ready to deploy.

## Site Structure

```
├── content/                  # All your markdown content
│   ├── _index.md            # Homepage content
│   ├── about.md             # About Me page
│   ├── contact.md           # Contact page
│   ├── other-worlds.md      # Social media page
│   └── things-i-do/         # Things I Do section
│       ├── _index.md        # Section overview
│       ├── tech.md          # Tech subsection
│       ├── reading.md       # Reading subsection
│       ├── writing.md       # Writing subsection
│       └── photography.md   # Photography subsection
├── themes/personal/         # Custom theme
│   ├── layouts/             # HTML templates
│   └── static/css/          # Stylesheets
├── static/images/           # Your images and photos
└── hugo.toml               # Site configuration
```

## Customization

### 1. Update Site Information

Edit `hugo.toml`:

```toml
title = 'Your Name - Personal Site'

[params]
  author = 'Your Name'
  description = 'Your description'
  email = 'your.email@example.com'
  phone = '+1-234-567-8900'

[params.social]
  twitter = 'https://twitter.com/yourusername'
  linkedin = 'https://linkedin.com/in/yourusername'
  github = 'https://github.com/yourusername'
  instagram = 'https://instagram.com/yourusername'
  youtube = 'https://youtube.com/@yourusername'
```

### 2. Add Your Content

Edit the markdown files in `content/`:

- **About Me** (`content/about.md`) - Your bio, career, philosophy, hobbies
- **Things I Do** (`content/things-i-do/*.md`) - Your activities and projects
- **Other Worlds** (`content/other-worlds.md`) - Social media presence
- **Contact** (`content/contact.md`) - Contact information

### 3. Add Images

Place your images in `static/images/`:

- `profile-featured.jpg` - Main featured photo (recommended: 800x400px)
- Add any other images and reference them in markdown as `/images/filename.jpg`

### 4. Customize Colors

Edit `themes/personal/static/css/style.css` and modify the CSS variables:

```css
:root {
  --primary-color: #2c3e50;
  --secondary-color: #3498db;
  --accent-color: #e74c3c;
  /* ... more variables */
}
```

### 5. Add Social Media Widgets

For the "Other Worlds" page, you can embed real social media widgets:

- **Twitter**: Get embed code from [publish.twitter.com](https://publish.twitter.com/)
- **Instagram**: Use services like SnapWidget or Juicer
- **YouTube**: Use YouTube's embed code for playlists or channels
- **GitHub**: Use GitHub profile cards or repository widgets

Edit `themes/personal/layouts/_default/social.html` to add the embed codes.

## Content Tips

### Adding Blog Posts

Create a new section for blog posts:

```bash
hugo new blog/my-first-post.md
```

### Adding Photos

For photography galleries, you can:

1. Create a photo gallery section
2. Use Hugo's image processing
3. Or embed services like Flickr, 500px, or SmugMug

### Book Reviews

Add book review posts in a dedicated section with structured data:

```markdown
---
title: "Book Title"
author: "Author Name"
rating: 5
date: 2025-11-11
---

Your review here...
```

## Deployment

### Netlify (Recommended)

1. Push your code to GitHub
2. Connect your repo to Netlify
3. Set build command: `hugo`
4. Set publish directory: `public`
5. Deploy!

### GitHub Pages

```bash
# Build the site
hugo

# Deploy public/ folder to GitHub Pages
```

### Vercel

1. Import your Git repository
2. Set framework preset to "Hugo"
3. Deploy!

### Traditional Hosting

Upload the contents of the `public/` folder to your web server.

## Maintenance

### Adding New Pages

```bash
hugo new section-name/page-name.md
```

### Updating Content

Simply edit the markdown files and commit. If using continuous deployment (Netlify, Vercel), your site will automatically rebuild.

### Backup

Your entire site is markdown files - just commit to Git for version control and backup!

## Customization Ideas

- **Add a Blog**: Create a `content/blog/` section for regular posts
- **Photo Gallery**: Add an image gallery plugin or service
- **Newsletter**: Integrate Mailchimp or Substack
- **Analytics**: Add Google Analytics or Plausible
- **Comments**: Add Disqus or utterances for blog comments
- **Search**: Add Algolia or Lunr.js for site search
- **Dark Mode**: Add a theme toggle for dark/light mode

## Troubleshooting

**Site not loading?**
- Make sure Hugo is installed: `hugo version`
- Check that you're in the project directory
- Try `hugo server --debug` for detailed logs

**Images not showing?**
- Verify images are in `static/images/`
- Use absolute paths: `/images/photo.jpg`
- Check image file extensions match

**Styles not applying?**
- Clear browser cache
- Check CSS file path in `baseof.html`
- Verify theme name matches in `hugo.toml`

## Support

For Hugo documentation and help:
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hugo Discourse](https://discourse.gohugo.io/)

## License

This theme is open source and available under the MIT License.

---

**Built with ❤️ using Hugo**

Enjoy your new personal portfolio site! 🎉

