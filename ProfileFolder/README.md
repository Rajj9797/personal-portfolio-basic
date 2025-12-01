# Personal Portfolio (Static)

A minimal static HTML/CSS site with a GitHub Actions workflow to deploy to GitHub Pages.

Features
- Simple HTML + CSS starter files (`index.html`, `css/style.css`)
- Local development scripts using `live-server` or Python
- GitHub Actions workflow to automatically publish your site to GitHub Pages on push to `main`

Quick start

1) Open the project in your editor (VS Code recommended):

```bash
# assuming you're in the folder
code .
```

2) Edit files
- `index.html` — Edit content
- `css/style.css` — Update styling

3) Preview locally
- Option A (Python built-in server):

```bash
# Python 3
python -m http.server 8080
# Open http://localhost:8080 in your browser
```

- Option B (npm & live-server)

```bash
# install dependencies and start (requires Node.js)
npm install
npm run dev
# Open http://localhost:3000
```

Create a GitHub repo & push

Option 1 — using the GitHub CLI (`gh`)

```bash
gh repo create my-portfolio --public --source=.
# Or create private if you prefer --private

git add .
git commit -m "Initial site"
# Push to the default branch (main)
git branch -M main
git push -u origin main
```

Option 2 — without `gh` (manually via GitHub website)

- Create a new repository in your GitHub account via https://github.com/new
- Follow the repo instructions to push an existing repo from the command line:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<YOUR_USER>/<YOUR_REPO>.git
git push -u origin main
```

Deploy (GitHub Actions)

- On push to `main`, the `.github/workflows/deploy.yml` workflow runs and deploys the site to GitHub Pages using the official `actions/deploy-pages` flow.
- The site will publish automatically; to view the published URL, go to:

  https://<your-username>.github.io/<your-repo>

  or check the repository's **Settings > Pages** for the exact URL.

Notes and troubleshooting

- If you prefer to host from a `docs/` folder, move your files into `docs/` and update `.github/workflows/deploy.yml` to upload `docs/` instead of `.`.
- If your GitHub repository's default branch is not `main`, either update the `on.push.branches` field in the workflow or rename your branch to `main`.
- If GitHub Pages settings are not configured automatically, visit **Settings > Pages** and choose the branch / folder.

Customization ideas

- Add more HTML pages, a projects list, or JSON data to render dynamically
- Replace the build process with a static site generator if you need templates

Enjoy editing your site — edit `index.html` and `css/style.css`, then commit & push to deploy automatically. ✨
