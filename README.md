# Cabinet Configurator

A self-contained 3D cabinet configurator (single `index.html`, no build step). Loads Three.js and fonts from CDNs, so it runs the moment it's served over HTTPS.

## Deploy to Vercel via GitHub

1. **Push this folder to a GitHub repo.**
   ```
   git init
   git add .
   git commit -m "Cabinet configurator"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/cabinet-configurator.git
   git push -u origin main
   ```

2. **Import it in Vercel.** In the Vercel dashboard: **Add New → Project → Import** your repo.
   - Framework preset: **Other** (Vercel auto-detects "no framework").
   - Build command: **none** (leave empty).
   - Output directory: leave as root.
   - Click **Deploy**. You'll get a live URL like `your-project.vercel.app` in ~20 seconds.

3. **Every future `git push` to `main` auto-deploys.** No manual step.

## Embed in Framer

In the Framer editor, add an **Embed** element → **URL** (iframe) mode → paste your Vercel URL. Give it a fixed or viewport height (e.g. `680px` or `80vh`); the app fills its container and the control panel floats on top, down to mobile.

## Custom domain (optional, later)

Vercel dashboard → project **Settings → Domains** → add `configurator.YOUR-DOMAIN.com` and follow the CNAME instructions at your DNS provider. HTTPS is issued automatically.

> **Note on `vercel.json`:** the `Content-Security-Policy` header restricts which sites may embed this app in an iframe (`frame-ancestors`). Replace `YOUR-DOMAIN.com` with the client's real domain, and confirm the `*.framer.app` / `*.framer.website` entries match where the Framer site is actually served. If you want to allow embedding from anywhere while testing, you can temporarily remove that one header.

## File map

- `index.html` — the entire app
- `vercel.json` — clean URLs + embedding/security headers
- `.gitignore` — ignores `.vercel`, OS cruft
