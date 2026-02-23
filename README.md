# djaym7.com

Personal academic website for Jay Desai.

## File Structure

```
djaym7.com/
├── index.html   # Single-page site (all content)
├── style.css    # Styles, dark/light mode, responsive
├── CNAME        # Custom domain config for GitHub Pages
└── README.md    # This file
```

## Deploy on GitHub Pages

1. Create a new GitHub repository named `djaym7.github.io`
2. Push this folder's contents to the `main` branch:
   ```bash
   cd djaym7.com
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/djaym7/djaym7.github.io.git
   git branch -M main
   git push -u origin main
   ```
3. Go to **Settings > Pages** in the repository
4. Under "Source", select `Deploy from a branch`, branch `main`, folder `/ (root)`
5. The site will be live at `https://djaym7.github.io` within a few minutes

## Connect Custom Domain (djaym7.com)

### GitHub Side
1. In the repository **Settings > Pages > Custom domain**, enter `djaym7.com`
2. Check "Enforce HTTPS" (may take a few minutes to provision the certificate)
3. The `CNAME` file is already included in the repo

### Namecheap DNS Side
1. Log in to Namecheap and go to **Domain List > Manage > Advanced DNS**
2. Remove any existing A or CNAME records for the root domain
3. Add these A records pointing to GitHub Pages:
   | Type | Host | Value            |
   |------|------|------------------|
   | A    | @    | 185.199.108.153  |
   | A    | @    | 185.199.109.153  |
   | A    | @    | 185.199.110.153  |
   | A    | @    | 185.199.111.153  |
4. Add a CNAME record for `www`:
   | Type  | Host | Value               |
   |-------|------|---------------------|
   | CNAME | www  | djaym7.github.io.   |
5. DNS propagation can take up to 24 hours

## Updating Content

Edit `index.html` directly. No build step needed. Push changes to `main` and GitHub Pages will redeploy automatically.

## Features

- Light/dark mode toggle (respects system preference, persists choice)
- Responsive design (mobile-friendly)
- No JavaScript frameworks or build tools
- Fast loading (pure HTML + CSS, minimal inline JS for theme toggle)
