# Quickstart: Deploy to Cloudflare Pages in 5 Minutes

## 1️⃣ Update Calendly Link (Required)

Open `index.html` and find these two lines:

**Line 112** (Header button):
```html
<a href="#demo" class="cta-primary" ...>Book a Demo</a>
```
This is fine - it scrolls to the demo section.

**Line 563** (Main CTA button):
```html
<!-- REPLACE THIS URL -->
<a href="https://calendly.com/your-calendly-link" class="cta-secondary" ...>

<!-- WITH YOUR ACTUAL CALENDLY LINK -->
<a href="https://calendly.com/yourname/30min" class="cta-secondary" ...>
```

## 2️⃣ Deploy to Cloudflare Pages

### Fastest Method: Direct Upload

1. **Go to Cloudflare**
   - Visit: https://dash.cloudflare.com
   - Click **Pages** in left sidebar
   - Click **Create a project**

2. **Upload Files**
   - Click **Upload assets**
   - Project name: `host-overflow-website`
   - Drag this entire folder into the upload area
   - Click **Deploy site**

3. **Done!**
   - Your site is live at: `https://host-overflow-website.pages.dev`
   - Total time: ~2 minutes

### Alternative: GitHub Integration (for auto-updates)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial Host Overflow landing page"
   git push origin main
   ```

2. **Connect to Cloudflare**
   - Cloudflare Pages → **Create a project**
   - Click **Connect to Git**
   - Select your `host-overflow--website` repository
   - Build settings: Leave everything empty
   - Click **Save and Deploy**

3. **Auto-deploys**
   - Every time you push to GitHub, site auto-updates
   - Great for ongoing changes

## 3️⃣ Add Custom Domain (Optional)

If you own `hostoverflow.com`:

1. **In Cloudflare Pages project**
   - Go to **Custom domains** tab
   - Click **Set up a custom domain**
   - Enter: `hostoverflow.com`
   - Click **Continue**

2. **DNS Setup**
   - If domain is already on Cloudflare: Automatic! ✨
   - If not: Add CNAME record at your registrar:
     - Name: `@` or `hostoverflow.com`
     - Value: `host-overflow-website.pages.dev`

3. **Add www subdomain** (optional)
   - Also add: `www.hostoverflow.com`
   - Enable redirect to apex domain

## 4️⃣ Enable Free Analytics (Optional)

1. **In Cloudflare Dashboard**
   - Go to **Web Analytics**
   - Click **Add a site**
   - Enter: `hostoverflow.com`

2. **Copy the script**
   - Add to `index.html` before `</head>`

3. **Privacy-friendly, cookie-free analytics!**

## That's It!

Your professional landing page is now live and ready for the Macaroni Grill demo.

---

## Quick Reference

| Action | URL |
|--------|-----|
| Cloudflare Dashboard | https://dash.cloudflare.com |
| Your Pages URL | https://host-overflow-website.pages.dev |
| Custom domain (when setup) | https://hostoverflow.com |
| Local preview | Open `index.html` in browser |

## Need Help?

- **Detailed guide**: See `DEPLOY_CLOUDFLARE.md`
- **All docs**: See `README.md`
- **Next steps**: See `NEXT_STEPS.md`

---

**Deployment time: ~5 minutes**
**Cost: Free (Cloudflare Pages free tier)**
**Performance: Global CDN, auto-SSL, HTTP/3**
