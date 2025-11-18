# Deployment Instructions

## Cloudflare Pages Deployment

This project is configured to deploy to Cloudflare Pages at `covidtesting.pikemd.com`.

### Automatic Deployment via GitHub

1. **Connect Repository to Cloudflare Pages:**
   - Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Go to Workers & Pages → Create application → Pages → Connect to Git
   - Select your GitHub repository
   - Configure build settings:
     - **Production branch:** `main`
     - **Build command:** (leave empty - this is a static site)
     - **Build output directory:** `/`
     - **Root directory:** `/`

2. **Configure Custom Domain:**
   - In Cloudflare Pages project settings, go to "Custom domains"
   - Add `covidtesting.pikemd.com`
   - Cloudflare will automatically create the necessary DNS records

3. **Verify Deployment:**
   - Push to main branch triggers automatic deployment
   - Site will be available at `covidtesting.pikemd.com`

### Manual Deployment via Wrangler CLI

```bash
# Install Wrangler CLI (if not already installed)
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Deploy to Cloudflare Pages
wrangler pages deploy . --project-name=covid-serology-testing

# To deploy with a specific commit message
wrangler pages deploy . --project-name=covid-serology-testing --commit-message="Deploy update"
```

### Project Structure

```
.
├── index.html              # Main landing page
├── data/                   # All CSV data files (centralized)
│   ├── covid19serology.csv
│   ├── fda_table.csv
│   └── ...
├── D3Visual/               # D3.js visualizations
│   ├── 0-EDA/             # Exploratory Data Analysis
│   ├── 1-FDA/             # FDA Test Analysis
│   ├── 2-Prevalence/      # Cluster & Scatter Analysis
│   └── 3-Clusters_Scatter/ # Prevalence Analysis
├── data documentation/     # Dataset documentation
├── _headers               # Cloudflare Pages headers config
└── wrangler.jsonc         # Wrangler configuration
```

### DNS Configuration

Ensure your DNS is managed by Cloudflare for `pikemd.com`:

1. Add CNAME record: `covidtesting` → `covid-serology-testing.pages.dev`
2. Or let Cloudflare auto-configure when adding custom domain in Pages settings

### Cache Configuration

Headers are configured for optimal caching:
- HTML files: No cache (always fetch fresh)
- CSS/JS files: 24 hours cache
- CSV/PDF files: 24 hours cache
- Security headers enabled (XSS protection, frame options, etc.)

### Troubleshooting

**Issue: CSV files not loading**
- Verify all CSV files are in the `data/` folder
- Check browser console for CORS errors
- Ensure Content-Type headers are set correctly

**Issue: Custom domain not working**
- Verify DNS propagation (can take up to 48 hours)
- Check SSL certificate is active in Cloudflare
- Clear browser cache and try incognito mode

**Issue: 404 errors on subpages**
- Cloudflare Pages automatically handles HTML file routing
- No special configuration needed for clean URLs

### Environment

- **Production URL:** https://covidtesting.pikemd.com
- **Preview URL:** Auto-generated for each commit (non-main branches)
- **Technology:** Static HTML/CSS/JS with D3.js visualizations
- **Hosting:** Cloudflare Pages (CDN-distributed)

### Performance

Cloudflare Pages provides:
- Global CDN distribution
- Automatic HTTPS
- HTTP/2 and HTTP/3 support
- Brotli compression
- Infinite bandwidth (no limits)
- 500 builds per month on free tier
