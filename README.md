# DIYgenii Landing Page

Static landing page for diygenii.com, hosted on GitHub Pages.

## Setup

### 1. Create GitHub Repository

```bash
# From this directory
git add .
git commit -m "Initial landing page"
git remote add origin https://github.com/kdurotoye/diygenii-landing.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to: https://github.com/kdurotoye/diygenii-landing/settings/pages
2. Source: Deploy from branch
3. Branch: `main` → `/root`
4. Save

### 3. Configure Custom Domain

**In GitHub**:
1. Settings → Pages → Custom domain
2. Enter: `diygenii.com`
3. Save
4. Wait for DNS check
5. Enable "Enforce HTTPS"

**In IONOS DNS**:

Add these A records:
```
Type: A
Host: @
Points to: 185.199.108.153

Type: A
Host: @
Points to: 185.199.109.153

Type: A
Host: @
Points to: 185.199.110.153

Type: A
Host: @
Points to: 185.199.111.153
```

Add CNAME record:
```
Type: CNAME
Host: www
Points to: kdurotoye.github.io
```

### 4. Add CNAME File

GitHub Pages needs a CNAME file:
```bash
echo "diygenii.com" > CNAME
git add CNAME
git commit -m "Add CNAME for custom domain"
git push
```

## DNS Propagation

- Takes 10-60 minutes
- Check status: https://www.whatsmydns.net/#A/diygenii.com

## Local Testing

Open `index.html` in browser to preview.

## Future

When ready to deploy full application:
- Landing content moves to app marketing pages
- Or keep at `about.diygenii.com` subdomain
- Main domain points to production app
