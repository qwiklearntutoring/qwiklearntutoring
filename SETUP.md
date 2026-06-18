# Qwiklearn Website — GitHub Pages Setup Guide

## Folder Structure
```
qwiklearn/
├── index.html          ← Home page
├── about.html          ← About Ms. Steiner
├── services.html       ← Services & Pricing
├── studyhall.html      ← Virtual Study Hall
├── mathcamp.html       ← Math Camp 2026
├── css/
│   └── style.css       ← Shared styles
└── images/             ← Put YOUR images here (see below)
```

---

## Step 1 — Add Your Images

Place these image files in the `images/` folder:

| Filename                    | Used on          | Description                              |
|-----------------------------|------------------|------------------------------------------|
| `ms-steiner.jpg`            | About page       | Your photo (the selfie from the PDF)     |
| `studyhall-middle.jpg`      | Study Hall page  | Middle School Study Hall flyer/image     |
| `studyhall-high.jpg`        | Study Hall page  | High School Study Hall flyer/image       |
| `mathcamp-hero.jpg`         | Math Camp page   | Math Camp 2026 banner/flyer              |
| `hero-math.jpg`             | Home page        | A colorful math image for the hero       |

Then in each HTML file, replace the placeholder `<div>` with a real `<img>` tag:
```html
<!-- Replace this: -->
<div class="bio-photo-placeholder">...</div>

<!-- With this: -->
<img src="images/ms-steiner.jpg" alt="Ms. Steiner" class="bio-photo" style="border-radius:20px;">
```

---

## Step 2 — Push to GitHub

1. Create a new repository at https://github.com/new
   - Name it `qwiklearn` (or your domain name)
   - Set it to **Public**
   - Do NOT add a README (you already have files)

2. Open Terminal and run:
```bash
cd /path/to/qwiklearn   # navigate to your site folder
git init
git add .
git commit -m "Initial Qwiklearn website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/qwiklearn.git
git push -u origin main
```

---

## Step 3 — Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → scroll to **Pages** (left sidebar)
3. Under "Source", select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click **Save**
5. Your site will be live at: `https://YOUR_USERNAME.github.io/qwiklearn`

---

## Step 4 — Connect Your Custom Domain

1. In GitHub Pages Settings, under "Custom domain":
   - Type your domain (e.g. `qwiklearn.com`)
   - Click **Save**

2. Go to your domain registrar (GoDaddy, Namecheap, etc.) and add these DNS records:

**For a root domain (qwiklearn.com):**
Add 4 A records pointing to GitHub's IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For www subdomain:**
Add a CNAME record:
```
Name: www
Value: YOUR_USERNAME.github.io
```

3. Wait 10–30 minutes for DNS to propagate.

4. Back in GitHub Pages settings, check **"Enforce HTTPS"** once it's available.

---

## Making Updates Later

Whenever you change any file:
```bash
git add .
git commit -m "Update [describe what you changed]"
git push
```
GitHub Pages will auto-deploy within ~60 seconds.

---

## Customization Tips

- **Colors**: Edit the `:root` variables at the top of `css/style.css`
- **Email link**: Search for `qwiklearntutoring@gmail.com` across all files and update if needed
- **Prices**: Edit directly in `services.html`
- **Session times**: Edit directly in `studyhall.html` and `mathcamp.html`
- **Contact hours**: Appear in every footer — search `Sun–Thu` to find them all

---

Questions? The site is all plain HTML/CSS — no frameworks, no build step.
Open any `.html` file in a browser to preview locally before pushing.
