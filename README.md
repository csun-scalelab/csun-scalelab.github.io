# SCALE Lab Website

Smart Coordination and Locomotion Laboratory — static website for GitHub Pages.

## Files

```
index.html        ← Home page
team.html         ← Team members
publications.html ← Publications list (with filter buttons)
contact.html      ← Contact info + open positions
style.css         ← Shared stylesheet
nav.js            ← Mobile nav toggle
```

## Deploying to GitHub Pages

### 1. Create a GitHub repository

Go to https://github.com/new and create a new **public** repository.

Name it either:
- `scale-lab-usc.github.io` — if you want the URL to be `https://scale-lab-usc.github.io`
- Any name, e.g. `website` — URL will be `https://scale-lab-usc.github.io/website`

### 2. Push the files

```bash
cd scale-lab-website
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/YOUR_ORG/YOUR_REPO.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch: `main`, folder: `/ (root)`
4. Click **Save**

Your site will be live at `https://YOUR_ORG.github.io/YOUR_REPO` within ~60 seconds.

## Customizing the content

### Update placeholder content
Search for the following and replace with real information:
- `Dr. Lena Chen` → your PI's name
- `LC`, `AR`, `SK`, etc. → initials for member avatar circles
- Email addresses (`lchen@usc.edu`, `scalelab@usc.edu`)
- University/department name
- Building/room number

### Add a real photo for the PI
Replace the `.pi-avatar` div with an `<img>` tag:
```html
<img src="images/pi-photo.jpg" alt="Dr. Lena Chen" class="pi-avatar" style="object-fit:cover;" />
```

### Add publications
Copy a `.pub-entry` block in `publications.html` and fill in the details.
The `data-topic` attribute controls which filter button shows it — use any combination of:
`locomotion`, `multiagent`, `learning`

### Change colors
Edit the CSS variables at the top of `style.css`:
```css
--navy:   #0e1a2b;   /* header/hero background */
--accent: #1d6fa4;   /* links and highlights    */
--gold:   #b8903a;   /* available for accents   */
```

### Add Google Analytics
Paste your GA tag just before `</head>` in each HTML file.

## Adding a custom domain

1. Buy a domain (e.g. `scalelab.usc.edu` via your university IT, or a public registrar)
2. In GitHub Pages settings, enter your custom domain
3. Add a `CNAME` file to the repo root containing just your domain:
   ```
   scalelab.usc.edu
   ```
4. Point your DNS to GitHub's servers (see https://docs.github.com/pages/custom-domain)
