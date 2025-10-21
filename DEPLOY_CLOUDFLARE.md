# Deploy to Cloudflare Pages

## Quick Deploy (Recommended)

### Option 1: GitHub Integration (Automatic Updates)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial landing page"
   git push origin main
   ```

2. **Connect to Cloudflare Pages**
   - Go to [Cloudflare Dashboard](https://dash.cloudflare.com)
   - Navigate to **Pages**
   - Click **Create a project**
   - Click **Connect to Git**
   - Select your repository: `host-overflow--website`
   - Configure build settings:
     - **Production branch**: `main`
     - **Build command**: (leave empty)
     - **Build output directory**: `/`
   - Click **Save and Deploy**

3. **Done!** Your site will be live at `https://host-overflow-website.pages.dev`

### Option 2: Direct Upload (No Git Required)

1. **Go to Cloudflare Pages**
   - Visit [Cloudflare Dashboard](https://dash.cloudflare.com) → Pages
   - Click **Create a project**
   - Click **Upload assets**

2. **Upload Files**
   - Drag and drop the entire `host-overflow--website` folder
   - Or select files: `index.html`, `.gitignore`
   - Click **Deploy site**

3. **Done!** Live in ~30 seconds.

## Custom Domain Setup (hostoverflow.com)

### If Domain is Already on Cloudflare

1. In your Pages project, go to **Custom domains**
2. Click **Set up a custom domain**
3. Enter: `hostoverflow.com`
4. Cloudflare will automatically configure DNS (no manual records needed!)
5. Also add `www.hostoverflow.com` and enable redirect to apex

### If Domain is NOT on Cloudflare

1. **Transfer domain to Cloudflare** (recommended)
   - Go to **Domain Registration** in Cloudflare
   - Click **Transfer domain**
   - Follow the transfer process (~7 days)

2. **Or use existing registrar**
   - In Cloudflare Pages → Custom domains → Add domain
   - Copy the CNAME records provided
   - Add to your domain registrar:
     - `CNAME` record: `hostoverflow.com` → `host-overflow-website.pages.dev`
     - `CNAME` record: `www` → `host-overflow-website.pages.dev`
   - Wait for DNS propagation (5-30 minutes)

## SSL Certificate

- ✅ **Automatic** - Cloudflare provides free SSL
- ✅ **No configuration needed**
- ✅ **Activated within minutes**

## Post-Deployment

### Check Your Site
```bash
# Your Cloudflare Pages URL
https://host-overflow-website.pages.dev

# With custom domain (after DNS setup)
https://hostoverflow.com
```

### Enable Web Analytics (Free!)

1. In Cloudflare Dashboard → **Web Analytics**
2. Click **Add a site**
3. Enter: `hostoverflow.com`
4. Copy the analytics script
5. Add to `index.html` before `</head>`:

```html
<!-- Cloudflare Web Analytics -->
<script defer src='https://static.cloudflareinsights.com/beacon.min.js'
        data-cf-beacon='{"token": "YOUR_TOKEN_HERE"}'></script>
```

**Benefits:**
- Privacy-friendly (no cookies)
- Free forever
- Real-time analytics
- Core Web Vitals tracking

## Performance Optimization

Cloudflare Pages automatically provides:
- ✅ Global CDN (300+ locations)
- ✅ HTTP/3 support
- ✅ Brotli compression
- ✅ DDoS protection
- ✅ Auto-minification (enable in settings)

### Enable Additional Optimizations

In Cloudflare Dashboard → **Speed** → **Optimization**:
- [x] Auto Minify: HTML, CSS, JavaScript
- [x] Early Hints
- [x] Rocket Loader (optional - may affect simple sites)

## Deployment Workflow

### Automatic (Git-based)

Every time you push to GitHub:
```bash
git add .
git commit -m "Update landing page content"
git push origin main
```

Cloudflare Pages automatically:
1. Detects the push
2. Deploys the new version
3. Updates the live site in ~30 seconds

### Manual (Direct upload)

1. Go to your Pages project
2. Click **Create deployment**
3. Upload updated files
4. Deploy

## Preview Deployments

Cloudflare Pages creates preview URLs for:
- **Every branch** - Test changes before merging
- **Every commit** - Share specific versions

Access previews at:
- `https://[commit-hash].[project].pages.dev`
- Manage in **Deployments** tab

## Rollback

If something breaks:

1. Go to **Deployments** tab
2. Find a previous working deployment
3. Click **⋯** → **Rollback to this deployment**
4. Confirm - site reverts instantly

## Environment Variables (If Needed Later)

For static sites, you typically don't need these. But if you add dynamic features:

1. Go to **Settings** → **Environment variables**
2. Add variables for Production/Preview
3. Access via build process

## Troubleshooting

### Site not updating after push
- Check **Deployments** tab for build status
- Look for failed deployments
- Verify branch is set to `main`

### Custom domain not working
- Check DNS propagation: [whatsmydns.net](https://whatsmydns.net)
- Verify CNAME records point to `.pages.dev` domain
- Wait 5-30 minutes for DNS propagation
- Clear browser cache

### SSL certificate error
- Wait 5-10 minutes after adding custom domain
- Cloudflare auto-provisions certificates
- Check **SSL/TLS** settings (should be "Full")

### 404 errors
- Ensure `index.html` is in root directory
- Check file names are lowercase
- Verify deployment shows correct files

## Cost

**Free tier includes:**
- Unlimited requests
- Unlimited bandwidth
- 500 builds per month
- 1 build at a time
- Unlimited sites

**More than enough for this use case!**

## Support Resources

- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)
- [Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/)
- [Community Forum](https://community.cloudflare.com/c/developers/pages/)

---

**Ready to deploy?**

Choose Git integration if you want automatic updates, or direct upload for quickest deployment.
