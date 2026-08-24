# Setting up your site

## 1. Create the GitHub repo
1. Go to github.com and create a **new repository** named exactly `YOUR-GITHUB-USERNAME.github.io`
   (replace YOUR-GITHUB-USERNAME with your actual GitHub username — this exact name is required for GitHub Pages).
2. Don't initialize it with a README (we already have files to push).

## 2. Push these files
From inside this folder, run:
```bash
git init
git add .
git commit -m "Initial site setup"
git branch -M main
git remote add origin https://github.com/YOUR-GITHUB-USERNAME/YOUR-GITHUB-USERNAME.github.io.git
git push -u origin main
```

## 3. Enable GitHub Pages
1. On GitHub, go to your new repo → **Settings** → **Pages**.
2. Under "Build and deployment", set Source to **Deploy from a branch**, branch = `main`, folder = `/ (root)`.
3. Save. Your site will be live in a minute or two at `https://YOUR-GITHUB-USERNAME.github.io`.

## 4. Before/after pushing — three things still to finish

### a) Replace placeholders
Search the repo for `YOUR-GITHUB-USERNAME` (in `_config.yml`) and replace with your real username.

### b) Add your photo
Replace `images/profile.png` with your own headshot (keep the same filename, or update
`avatar:` in `_config.yml` to match your new filename).

### c) CV page
The CV page (`_pages/cv.md`) links out to your Google Doc CV. Make sure that Doc's
sharing setting is "Anyone with the link" → Viewer, or visitors will hit a
"request access" page instead of your CV.

### d) Add publications
Open `publications_sheet.xlsx` (provided alongside this zip) and add a row per paper.
Then either:
- Send me the completed sheet and I'll generate the publication pages for you, or
- Convert it to `markdown_generator/publications.tsv` (same columns) and run the
  `markdown_generator/publications.ipynb` notebook yourself — it writes one `.md` file
  per row into `_publications/`.

## Local preview (optional)
If you have Ruby installed:
```bash
bundle install
bundle exec jekyll serve
```
Then visit `http://localhost:4000`.
