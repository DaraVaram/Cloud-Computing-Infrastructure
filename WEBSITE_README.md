# Cloud Computing Infrastructure Website

This repository has been converted into a beautiful Jekyll website hosted on GitHub Pages!

## 🌐 Live Website

Your website is now available at: **https://daravaram.github.io/Cloud-Computing-Infrastructure**

## 🚀 How to Enable GitHub Pages

To make your website live, follow these steps:

1. **Push your changes to GitHub:**
   ```bash
   git add .
   git commit -m "Add Jekyll website structure"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click on "Settings" tab
   - Scroll down to "Pages" section
   - Under "Source", select "GitHub Actions"
   - The website will automatically build and deploy!

## 📁 Website Structure

```
├── _config.yml           # Jekyll configuration
├── _layouts/             # Custom page layouts
│   └── lecture.html      # Layout for lecture pages
├── _lectures/            # Individual lecture pages
│   ├── lecture-1.md
│   ├── lecture-2.md
│   └── ...
├── _ai_notes/            # AI-generated summaries
│   ├── lecture1.md
│   └── ...
├── _pages/               # Main navigation pages
│   ├── lectures.md
│   ├── ai-notes.md
│   └── mcqs.md
├── figures/              # Images and diagrams
├── .github/workflows/    # GitHub Actions for deployment
└── index.md              # Homepage
```

## ✨ Features

- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Beautiful Navigation**: Easy-to-use navigation between lectures
- **AI Notes Integration**: Dedicated section for AI-generated summaries
- **MCQ Section**: Practice questions area (ready for content)
- **Automatic Deployment**: Updates automatically when you push changes
- **SEO Optimized**: Search engine friendly with proper meta tags

## 🎨 Customization

### Changing Colors/Theme
Edit `_config.yml` and the CSS in individual page files to customize colors and styling.

### Adding New Content
- **New Lectures**: Add markdown files to `_lectures/` folder with proper frontmatter
- **New AI Notes**: Add markdown files to `_ai_notes/` folder
- **MCQ Questions**: Edit `_pages/mcqs.md` to add actual questions

### Site Configuration
Edit `_config.yml` to change:
- Site title and description
- Author information
- Navigation menu items
- Social links

## 📱 Mobile Optimized

The website is fully responsive and looks great on all devices with:
- Mobile-friendly navigation
- Optimized typography
- Touch-friendly buttons
- Fast loading times

## 🔧 Local Development

To run the website locally:

1. Install Ruby and Jekyll
2. Run `bundle install`
3. Run `bundle exec jekyll serve`
4. Visit `http://localhost:4000`

## 📄 Original Content

All your original markdown files remain unchanged:
- `Lecture-1.md` through `Lecture-5.md`
- `AI/Lecture1.md` through `AI/Lecture5.md`
- `MCQs/Selection.md`
- `README.md` (this file)

The website uses converted versions in the `_lectures/` and `_ai_notes/` directories with proper Jekyll formatting.

---

**Note**: After pushing to GitHub and enabling Pages, it may take a few minutes for your website to become available. Check the Actions tab to see the deployment progress!