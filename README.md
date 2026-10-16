# Naveen Annadurai — Portfolio

A static site: one `index.html` plus an `assets/` folder. No build step, no server code.

```
naveen-portfolio/
├── index.html      the whole site (styles and scripts are inside)
├── assets/         case-study screens, your photo, resume PDF
├── .nojekyll       tells GitHub Pages to serve files as-is
└── README.md       this file
```

The site loads three libraries (GSAP, Lenis, Three.js) and its fonts from public CDNs, so it needs an internet connection to look right.

## Preview it on your computer

Opening `index.html` by double-clicking mostly works, but browsers block some features on `file://`. For an accurate preview, run a tiny local server from this folder:

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

## Option 1: Netlify (easiest, about 2 minutes)

1. Go to https://app.netlify.com/drop and sign in (free).
2. Drag the whole `naveen-portfolio` folder onto the page.
3. Netlify gives you a link like `https://random-name.netlify.app`.
4. In **Site configuration → Change site name**, rename it, for example `naveen-annadurai.netlify.app`.

To update later: open the site in Netlify → **Deploys** → drag the folder in again.

## Option 2: GitHub Pages (free, link stays as long as the repo exists)

1. Create a GitHub account and a new **public** repository, for example `portfolio`.
2. On the repository page, click **Add file → Upload files**, drag in everything inside this folder (including the `assets` folder and `.nojekyll`), and commit.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute your site is live at `https://<your-username>.github.io/portfolio/`.

Tip: name the repository `<your-username>.github.io` and the site lives at `https://<your-username>.github.io/` with no extra path.

## Custom domain (optional)

Both Netlify and GitHub Pages support your own domain (for example `naveen.design`, bought from Namecheap, GoDaddy or Google Domains). In Netlify: **Domain management → Add a domain**. In GitHub: **Settings → Pages → Custom domain**. Each walks you through the DNS records.

## After you deploy

- **Link previews (WhatsApp, LinkedIn):** in `index.html`, change `<meta property="og:image" content="assets/naveen.webp">` to the full address, for example `https://naveen-annadurai.netlify.app/assets/naveen.webp`. Previews need an absolute URL.
- **Resume:** to update it, replace `assets/naveen-annadurai-resume.pdf` with a new file of the same name.
- **Photo:** replace `assets/naveen.webp` (portrait, roughly 600 × 640).

## Where things are in `index.html`

| To change | Search for |
|---|---|
| Hero headline | `intro-h` |
| Metrics strip | `class="metrics"` |
| Project cards | `class="cards"` |
| Case studies | `CASE: DEEPAGENT`, `CASE: LAB`, `CASE: HEALTHPLUS`, `CASE: APPOINTMENT` |
| About, Resume, Contact tabs | `===== ABOUT`, `===== RESUME`, `===== CONTACT` |
| Social links | `instagram.com`, `x.com`, `wa.me`, `linkedin.com` |
| Text on the 3D pass | `function drawFront` and `function drawBack` |
| Colours | the `:root{` block at the top of the `<style>` |
| Type scale and spacing | `--fs-` and `--s-` tokens in `:root` |
