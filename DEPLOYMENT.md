# Deployment Guide

## GitHub Pages (Recommended)

### Quick Deploy
1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under "Source", select branch: `main`, folder: `/ (root)`
4. Click **Save**
5. Wait 1-2 minutes for deployment
6. Access at: `https://YOUR_USERNAME.github.io/gold-silver-tracker/`

### Custom Domain (Optional)
1. Add a `CNAME` file with your domain name
2. Configure DNS records with your domain provider
3. Update GitHub Pages settings with custom domain

## Other Deployment Options

### Netlify
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod
```

### Vercel
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod
```

### Traditional Web Hosting
1. Upload `index.html` to your web server
2. Ensure file permissions are correct (644)
3. Access via your domain/subdomain

## Environment Variables

Currently not required. Future API integration may need:
- `API_KEY` - Commodity price API key
- `API_ENDPOINT` - Data source URL

## Update Frequency

For daily updates:
1. Manual: Edit `index.html` daily with new prices
2. Automated: Set up GitHub Actions (see `docs/automation.md`)

## Monitoring

- Use Google Analytics (add tracking code to `index.html`)
- Monitor GitHub Pages deployment status
- Check browser console for errors

## Troubleshooting

### Charts not loading
- Check Chart.js CDN is accessible
- Verify JavaScript console for errors
- Ensure data format is correct

### GitHub Pages not deploying
- Verify branch and folder settings
- Check repository visibility (public)
- Wait a few minutes and hard refresh browser

### Performance issues
- Consider pagination for large datasets
- Implement lazy loading for historical data
- Optimize Chart.js settings