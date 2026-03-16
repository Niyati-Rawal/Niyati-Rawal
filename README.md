# 🚀 How to Deploy Your Portfolio on GitHub Pages
### A complete guide for Niyati Raval's portfolio — niyati513@gmail.com](https://niyati-rawal.github.io/portfolio)

---

## PART 1 — Upload Your Portfolio Files

### Step 1: Create a new GitHub repository

1. Go to [github.com](https://github.com) and log in as **Niyati-Rawal**
2. Click the **+** icon (top-right) → **New repository**
3. Name it exactly: `portfolio`
   - ✅ Full repo name: `Niyati-Rawal/portfolio`
4. Set it to **Public**
5. ✅ Check "Add a README file"
6. Click **Create repository**

---

### Step 2: Upload your files

Your portfolio needs this folder structure:

```
portfolio/
├── index.html          ← main file (already done ✅)
├── style.css           ← your styles (already done ✅)
├── mediaqueries.css    ← responsive styles (already done ✅)
├── script.js           ← your JavaScript (already done ✅)
└── assets/
    ├── nr.png          ← your profile photo (already done ✅)
    └── NewResume_Niyati_Raval.pdf   ← your resume (already done ✅)
```

**To upload:**
1. Go to your new `portfolio` repo on GitHub
2. Click **Add file** → **Upload files**
3. Drag and drop: `index.html`, `style.css`, `mediaqueries.css`, `script.js`
4. Click **Commit changes**
5. Now create the `assets` folder:
   - Click **Add file** → **Create new file**
   - Type `assets/placeholder.txt` in the name field
   - Add any text, commit it — this creates the folder
6. Go into the `assets` folder, click **Add file** → **Upload files**
7. Upload: `nr.png` and `NewResume_Niyati_Raval.pdf`
8. Commit changes

> **⚠️ Important:** In your `index.html`, the image path is `assets/nr.png` — this will work correctly once the `assets/` folder is created.

---

### Step 3: Enable GitHub Pages

1. In your `portfolio` repo, click **Settings** (top menu)
2. Scroll down to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Under **Branch**, select `main` → `/ (root)`
5. Click **Save**
6. Wait ~2 minutes ⏳
7. Refresh — you'll see:
   > ✅ **Your site is live at: `https://niyati-rawal.github.io/portfolio`**

**That's it! Your portfolio is live! 🎉**

---

## PART 2 — Set Up Your Profile README

The profile README is what people see when they visit `github.com/Niyati-Rawal`. It's a special repository.

### Step 4: Create your profile repository

1. Go to GitHub → **+** → **New repository**
2. Name it exactly: `Niyati-Rawal`
   - ✅ It must match your username exactly (capital N, capital R, hyphen)
   - Full name: `Niyati-Rawal/Niyati-Rawal`
3. Set to **Public**
4. ✅ Check "Add a README file"
5. Click **Create repository**
6. GitHub will say: *"✨ Niyati-Rawal/Niyati-Rawal is a special repository."*

### Step 5: Add the README.md content

1. In the `Niyati-Rawal` repo, click the **README.md** file
2. Click the **pencil icon** ✏️ (Edit this file)
3. **Select all** the existing content and **delete** it
4. **Paste** the full content from the `README.md` file provided with this guide
5. Click **Commit changes** → **Commit directly to main**

---

## PART 3 — Update the Portfolio URL

After Step 3, your live URL is `https://niyati-rawal.github.io/portfolio`

In the README.md, this line already has that URL:
```
[![Portfolio](https://img.shields.io...)](https://niyati-rawal.github.io/portfolio)
```
✅ No change needed — it's already correct!

Also update your portfolio's `index.html` — the GitHub icon link already points to your profile, which is correct.

---

## PART 4 — Set Up the Snake Animation (Optional but cool 🐍)

The contribution snake animation needs a GitHub Action to generate it.

1. In the `Niyati-Rawal` (profile) repo, click **Actions** tab
2. Click **New workflow** → **set up a workflow yourself**
3. Name the file: `snake.yml`
4. Paste this content:

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"   # runs daily at midnight
  workflow_dispatch:       # manual trigger

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

5. Click **Commit changes**
6. Go to **Actions** → click the workflow → **Run workflow** (manual trigger)
7. Wait ~1 min → the SVG is generated on the `output` branch
8. The README already references: `...Niyati-Rawal/output/github-contribution-grid-snake-dark.svg` ✅

---

## PART 5 — SEO Tips (Get Found on Google)

These things are already done in the README, but here's what helps Google find "Niyati Raval":

| What | Where | Status |
|------|-------|--------|
| Your real name in the bio | GitHub profile Settings → Bio | ✅ Add "Niyati Raval" |
| Name in README headings | README.md | ✅ Done |
| Name in alt text of images | README.md | ✅ Done |
| SEO comment keywords in HTML | README.md | ✅ Done |
| LinkedIn URL in README | README.md | ✅ Done |
| Portfolio website URL | README.md | ✅ Done |
| GitHub profile bio | Settings → Public profile | 👉 Add manually |

### Set your GitHub profile bio (important for SEO!):
1. Click your avatar → **Settings**
2. Fill in:
   - **Name:** `Niyati Raval`
   - **Bio:** `Full Stack Developer · Python · Django · DRF · FastAPI · Ahmedabad, India`
   - **Location:** `Ahmedabad, Gujarat, India`
   - **Website:** `https://niyati-rawal.github.io/portfolio`
3. Click **Update profile**

---

## PART 6 — Fix Image Path in index.html

Open your `index.html` and find this line:
```html
<img src="assets/nr.png" alt="Niyati Raval" class="profile-img">
```
✅ This is already correct! The `assets/` folder path will work with GitHub Pages.

Also find the CV button:
```html
onclick="window.open('./assets/NewResume_Niyati_Raval.pdf')"
```
✅ This is already correct too!

---

## Summary — Final Checklist

```
[ ] Created repo: Niyati-Rawal/portfolio
[ ] Uploaded: index.html, style.css, mediaqueries.css, script.js
[ ] Created assets/ folder with nr.png and resume PDF
[ ] Enabled GitHub Pages → site is live
[ ] Created repo: Niyati-Rawal/Niyati-Rawal (profile README)
[ ] Pasted README.md content into the profile repo
[ ] Set GitHub profile bio with your name + location
[ ] (Optional) Set up snake animation GitHub Action
```

**Your live URLs after all steps:**
- 🌐 **Portfolio:** `https://niyati-rawal.github.io/portfolio`
- 👤 **GitHub Profile:** `https://github.com/Niyati-Rawal`

---

*Made with ☕ chai and a lot of git pushes — Niyati Raval*
