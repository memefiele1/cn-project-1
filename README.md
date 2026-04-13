# Computer Networking Project 2 — Secure, Optimize, and Monitor Your Website
 
**Course:** Computer Networking (CSC 4220) | Spring 2026  
**Student:** Miracle Emefiele  
**Instructor:** Roya Hosseini  
**Live Website:** https://memefiele1.github.io/cn-project-1/
 
---
 
## Project Overview
 
This project enhances the Project 1 website by adding real-world **security**, **performance**, and **monitoring** features.
 
---
 
## Security Enhancements (Mandatory)
 
### 1. HTTPS via GitHub Pages ✅
- All traffic served over TLS on port 443
- Certificate provided automatically by GitHub Pages / Fastly CDN
- HTTP requests automatically redirect to HTTPS
 
### 2. XSS Protection with DOMPurify ✅
- DOMPurify v3.1.6 loaded via CDN with subresource integrity (SRI) hash
- All dynamic user input sanitized before being rendered to the DOM
- Demo on index.html shows malicious input being stripped in real time
 
### 3. Security Headers ✅
Applied via `<meta>` tags on every page:
| Header | Value |
|---|---|
| Content-Security-Policy | `default-src 'self'` |
| X-Frame-Options | `DENY` |
| X-Content-Type-Options | `nosniff` |
| Referrer-Policy | `strict-origin-when-cross-origin` |
 
---
 
## Additional Enhancement B — Performance Optimization ✅
 
- **Lazy loading images** — `loading="lazy"` + IntersectionObserver API, images only load when scrolled into view
- **Minified CSS** — styles inlined and compressed, eliminates separate CSS HTTP request
- **Cache-Control headers** — `max-age=86400` caches assets for 24 hours on repeat visits
- **CDN delivery** — GitHub Pages uses Fastly global CDN for edge-cached asset delivery
 
---
 
## Additional Enhancement C — Deployment & Infrastructure ✅
 
- **GitHub Pages hosting** — static site served globally via Fastly CDN
- **GitHub Actions CI/CD** — automated deployment pipeline triggers on every push to `main`
- **IPv6 support** — site resolves to both A (IPv4) and AAAA (IPv6) DNS records
 
---
 
## Bonus Challenge — Automated Deployment ✅
 
GitHub Actions workflow file: `.github/workflows/deploy.yml`
 
Every push to `main` automatically:
1. Checks out the repository
2. Validates that HTML files exist
3. Uploads site artifact
4. Deploys to GitHub Pages
 
---
 
## Network Monitoring
 
Google Analytics (G-XXXXXXXXXX) is embedded on both pages to track:
- Page views and unique visitors
- Traffic sources
- Session duration and bounce rate
 
---
 
## Running Locally
 
```bash
git clone https://github.com/memefiele1/cn-project-1.git
cd cn-project-1
# Open with any local server, e.g.:
python3 -m http.server 8000
# Then visit http://localhost:8000
```
 
---
 
## File Structure
 
```
cn-project-1/
├── index.html           # Home page with XSS demo + security features
├── networking.html      # Networking concepts with lazy loading + tables
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml   # GitHub Actions auto-deploy pipeline
```
 
