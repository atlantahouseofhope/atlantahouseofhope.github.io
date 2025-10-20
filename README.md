# Atlanta House of Hope Website

This is the source code for the Atlanta House of Hope website, built with Hugo and hosted on GitHub Pages.

## Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.143.1 or compatible version)
- Git

## Project Structure

- `main` branch: Source code and content
- `gh-pages` branch: Built/published site (via `public/` worktree)

## Local Development

### Preview the Site Locally

1. Navigate to the project directory
2. Run the Hugo development server:
   ```bash
   hugo server
   ```
3. Open your browser to `http://localhost:1313/`
4. The site will auto-reload as you make changes

### Stop the Server

Press `Ctrl+C` in the terminal

## Making Updates

### Push Changes to Main Branch

Use this when you want to save your work but not publish to the live site yet.

```bash
# Check status
git status

# Add your changes
git add .

# Commit with a message
git commit -m "Describe your changes here"

# Push to GitHub
git push origin main
```

## Publishing to Live Site

### Deploy to GitHub Pages

When you're ready to update the live website:

#### Option 1: Manual Steps

```bash
# 1. Build the site
hugo

# 2. Navigate to the public folder (gh-pages branch)
cd public

# 3. Add all changes
git add .

# 4. Commit
git commit -m "Update site"

# 5. Push to gh-pages
git push origin gh-pages

# 6. Return to main directory
cd ..
```

#### Option 2: Use Deployment Script

**On Linux/Mac:**
```bash
./deploy.sh
```

**On Windows:**
```bash
deploy.bat
```

The live site will update at `https://atlantahouseofhope.github.io/` within a few minutes.

## Troubleshooting

### If you see deprecated function errors

Make sure your Hugo templates use:
- `css.Sass` instead of `resources.ToCSS`
- `css.PostCSS` instead of `resources.PostCSS`

### If the public folder gets out of sync

```bash
# Remove the worktree
git worktree remove public

# Recreate it
git worktree add public gh-pages
```

## Files That Are Ignored

The following generated files are not tracked in the `main` branch:
- `public/` (the built site)
- `resources/_gen/` (Hugo's asset cache)
- `.hugo_build.lock`
- `hugo_stats.json`

## Additional Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
