# Host Overflow - Landing Page

Professional, conversion-focused landing page for Host Overflow AI Restaurant Concierge.

## Quick Start

This is a static single-page website. No build process required.

### Local Development

Simply open `index.html` in your browser:

```bash
# Option 1: Direct open
open index.html

# Option 2: Use a local server (recommended)
python3 -m http.server 8000
# Then visit: http://localhost:8000

# Option 3: Use npx serve
npx serve .
```

## Deployment

### Cloudflare Pages (Recommended)

**Quick Deploy:**
1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → Pages
2. Click **Create a project** → **Upload assets**
3. Drag and drop the entire folder
4. Deploy!

**Or via Git:**
- Push to GitHub, connect repository in Cloudflare Pages
- Auto-deploys on every push

**See `DEPLOY_CLOUDFLARE.md` for detailed instructions.**

### Alternative Options

- **Vercel**: `npm i -g vercel && vercel`
- **Netlify**: Drag/drop to [Netlify Drop](https://app.netlify.com/drop)
- **GitHub Pages**: Push to GitHub, enable in Settings → Pages
- **Any static host**: Upload `index.html` (self-contained)

## Configuration

### Update Calendly Link

Replace the placeholder Calendly URL in `index.html`:

```html
<!-- Line 563 - Update this URL -->
<a href="https://calendly.com/your-calendly-link" class="cta-secondary" target="_blank" rel="noopener">Book a Demo</a>
```

### Custom Domain

For `hostoverflow.com`:

1. Deploy to your preferred host (Vercel/Netlify recommended)
2. Add custom domain in hosting provider settings
3. Update DNS records:
   - For Vercel: Add CNAME pointing to `cname.vercel-dns.com`
   - For Netlify: Add CNAME pointing to your Netlify subdomain

## Features

- ✅ Fully responsive (mobile, tablet, desktop)
- ✅ Clean, modern design
- ✅ Fast load times (no frameworks, minimal dependencies)
- ✅ SEO optimized with meta tags
- ✅ Smooth scroll and animations
- ✅ Professional color scheme and typography
- ✅ Conversion-focused copy
- ✅ Clear call-to-action (Book a Demo)

## Design Details

- **Font**: Inter (Google Fonts)
- **Color Palette**:
  - Navy: #0F172A (primary text)
  - Teal: #06B6D4 (brand accent)
  - Orange: #F97316 (highlights)
  - Gray: #64748B (secondary text)
- **Layout**: Maximum width 1200px, centered
- **Mobile breakpoint**: 768px

## Page Sections

1. **Hero** - Value proposition + key stats
2. **Problem** - Pain points (missed calls, lost revenue)
3. **Solution** - Overflow-first positioning
4. **Features** - 6 key features with icons
5. **How It Works** - 3-step process
6. **CTA** - Book a demo
7. **Footer** - Contact info

## Maintenance

This is an MVP landing page. Future enhancements could include:

- Analytics integration (Google Analytics, Plausible)
- Email capture form
- Customer testimonials section
- Pricing page
- Blog/resources section
- Video demo embed

## Support

For questions or issues, contact: hello@hostoverflow.com
