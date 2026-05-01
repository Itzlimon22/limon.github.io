# Portfolio Website Setup Guide

## ✅ Current Status

Your al-folio portfolio website is now set up and ready! Here's what has been completed:

- ✅ Repository cloned
- ✅ Configuration customized with your information
- ✅ Ruby 3.3.11 installed
- ✅ Python 3.13 installed
- ✅ Dependencies installed (ImageMagick, nbconvert, Ruby gems)
- ✅ Development server running on http://localhost:4000

## 🎯 Personal Information Configured

- **Name:** Limon Howlader
- **Email:** limon.eece22@gmail.com
- **GitHub:** Itzlimon22
- **Institution:** Military Institute of Science and Technology (MIST)
- **Site URL:** https://limon.github.io

## 🚀 Next Steps

### 1. View Your Site Locally

Visit http://localhost:4000 in your browser to see your portfolio website running locally.

### 2. Deploy to GitHub Pages

#### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Create a repository named: `limon.github.io`
3. Make it **public** (required for GitHub Pages free tier)
4. Do NOT initialize with README, .gitignore, or license

#### Step 2: Connect Local Repository

```bash
cd "/Users/limon/protfolio website"
git remote remove origin
git remote add origin https://github.com/itzlimon22/limon.github.io.git
git branch -M main
git push -u origin main
```

#### Step 3: Enable GitHub Pages

1. Go to your repository: https://github.com/itzlimon22/limon.github.io
2. Settings → Pages
3. Select "Deploy from a branch"
4. Choose branch: `main`
5. Select folder: `/ (root)`
6. Save

#### Step 4: Wait for Deployment

Your site will be available at: https://limon.github.io in a few minutes

### 3. Customize Your Content

#### Profile Picture

1. Replace `/assets/img/prof_pic.jpg` with your photo
2. Keep the same filename or update `_pages/about.md`

#### About Page

Edit [`_pages/about.md`](/_pages/about.md) to write your bio and research interests

#### CV

1. Replace `/assets/pdf/cv.pdf` with your CV
2. Update the path in [`_data/socials.yml`](_data/socials.yml) if needed

#### Blog Posts

Create new blog posts in `_posts/` directory:

```
_posts/YYYY-MM-DD-title-of-post.md
```

#### Projects

Add your projects in `_projects/` directory

#### Publications (Bibliography)

Edit `_bibliography/papers.bib` with your publications in BibTeX format

### 4. Code Formatting (Important!)

Before pushing changes, format your code:

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
npm install --save-dev prettier @shopify/prettier-plugin-liquid
npx prettier . --write
```

## 📁 Important Files to Customize

| File                       | Purpose                 |
| -------------------------- | ----------------------- |
| `_config.yml`              | Main site configuration |
| `_data/socials.yml`        | Social media links      |
| `_pages/about.md`          | Your bio/about section  |
| `_pages/cv.md`             | CV page                 |
| `_pages/publications.md`   | Publications page       |
| `_projects/`               | Your projects           |
| `_posts/`                  | Blog posts              |
| `_bibliography/papers.bib` | Publications in BibTeX  |
| `assets/img/prof_pic.jpg`  | Your profile picture    |

## 🔧 Development Commands

### Start Development Server

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
cd "/Users/limon/protfolio website"
bundle exec jekyll serve --port 4000
```

### Build Production Site

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
JEKYLL_ENV=production bundle exec jekyll build
```

### Format Code

```bash
npx prettier . --write
```

## 🐛 Troubleshooting

### Port 4000 Already in Use

```bash
lsof -i :4000 | grep LISTEN | awk '{print $2}' | xargs kill
```

### Ruby/Bundler Issues

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
bundle install
```

### Clear Build Cache

```bash
rm -rf _site/ .jekyll-cache/
```

## 📚 Useful Resources

- [al-folio Documentation](https://github.com/alshedivat/al-folio)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [BibTeX Format Guide](http://www.bibtex.org/)
- [Markdown Guide](https://www.markdownguide.org/)

## 🎨 Theme Customization

The al-folio theme is highly customizable:

- Colors: Edit `_sass/_themes.scss`
- Layouts: Edit files in `_layouts/`
- Styles: Edit files in `_sass/`
- Javascript: Add files to `assets/js/`

For detailed customization, see [CUSTOMIZE.md](./CUSTOMIZE.md)

---

**Happy Portfolio Building! 🎉**

If you have any questions or issues, refer to the al-folio [documentation](https://github.com/alshedivat/al-folio) or the [troubleshooting guide](./TROUBLESHOOTING.md).
