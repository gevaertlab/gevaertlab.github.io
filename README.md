# Gevaert Lab Website

Static website for the Gevaert Lab at Stanford University.

## Structure

```
gevaertlab/
├── index.html          # Home page
├── research.html       # Research projects
├── people.html         # Lab members
├── publications.html   # Publications (auto-fetches from PubMed)
├── contact.html        # Contact & location
├── css/
│   └── style.css       # Shared Stanford-themed styles
├── js/
│   └── main.js         # Shared JS (nav toggle, active link)
└── images/             # Local images (add headshots, logos here)
```

## Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `gevaertlab`)
2. Push this folder to the repository:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/YOUR_USERNAME/gevaertlab.git
   git push -u origin main
   ```
3. In the repo settings → Pages → set Source to **Deploy from a branch** → branch: `main`, folder: `/ (root)`
4. Your site will be live at `https://YOUR_USERNAME.github.io/gevaertlab/`

## Optional: Custom domain

To use a custom domain (e.g. `gevaertlab.stanford.edu` or `gevaertlab.org`):
1. Add a `CNAME` file to the repo root containing your domain name
2. Configure DNS with your domain registrar to point to GitHub Pages

## Updating content

- **People**: Edit `people.html` — add/remove person cards in the relevant section
- **Research projects**: Edit `research.html` — duplicate a project block and update text
- **Highlighted publications**: Edit the highlighted section in `publications.html`
- **All publications**: Auto-updated from PubMed on every page load (no action needed)
- **Photos**: Add images to the `images/` folder and update `src` attributes in HTML

## Publications auto-update

The publications page fetches live from NCBI PubMed E-utilities using the query:
`Gevaert O[LASTAU] NOT medRxiv NOT bioRxiv NOT Desmet NOT Camarillo NOT erratum`

This runs automatically when visitors load the page. Results are cached for the session.
No API key is required. If PubMed is unreachable, the page gracefully shows external links.
