# TakeFive · Website

Official landing page for [TakeFive](https://apps.apple.com/app/id6810940670) — a native macOS menu bar app that reminds you to stand up, stretch, and rest your eyes, while politely stepping aside during meetings and full-screen work.

## What is TakeFive?

TakeFive sits quietly in your Mac's menu bar and gently reminds you to take mindful breaks. It knows when you're in a meeting, presenting, or deep in focus — and stays out of the way.

## Tech Stack

- Static HTML / CSS / JavaScript (no build step)
- Deployed on **Cloudflare Pages** (global CDN)

## Project Structure

```
├── index.html       # Landing page
├── privacy.html     # Privacy policy
├── styles.css       # Design system
├── script.js        # Scroll-reveal & nav interactions
├── _headers         # Cloudflare Pages cache & security headers
└── assets/          # Optimized images (logo + screenshots)
```

## Local Development

No build step required. Serve the folder with any static server:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve
```

Then open http://localhost:8000

## Deployment (Cloudflare Pages)

The site deploys automatically from the `main` branch via Cloudflare Pages.

### First-time setup

1. Push this repo to GitHub.
2. In the [Cloudflare dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Select the `xiaoqi-website` repository.
4. Build settings (it's a plain static site):
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
5. Click **Deploy**.

Every subsequent `git push` to `main` redeploys automatically.

### Custom domain (`takefive.whynottryfor.com`)

Cloudflare Pages fully supports subdomains:

1. Make sure the apex domain `whynottryfor.com` is using **Cloudflare DNS** (nameservers pointed to Cloudflare).
2. In the Pages project → **Custom domains** → **Set up a custom domain**.
3. Enter `takefive.whynottryfor.com` and confirm — Cloudflare adds the CNAME record automatically.
4. HTTPS is provisioned automatically.

## License

MIT
