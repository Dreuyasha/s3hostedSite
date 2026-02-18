# s3hostedSite
Hosting a website using AWS s3

# Dre's Simple Project Showcase

A clean, modern single-page static website hosted securely on AWS S3 + CloudFront (HTTPS enforced). Built as a quick demo to practice AWS static hosting and add a live link to my GitHub projects.

🔗 **Live Demo:** https://d32f0rld80mxig.cloudfront.net

## ✨ Features
- Responsive one-page design with gradient background, fade-in animation, and button hover effects
- Fully static (pure HTML + inline CSS — no build tools or server needed)
- Private S3 bucket (Block Public Access enabled) for better security
- HTTPS with automatic HTTP → HTTPS redirect via CloudFront
- Global CDN caching for fast worldwide access
- Zero-cost/low-cost for low traffic

## 🛠️ Tech Stack
- Frontend: HTML5 + CSS3 (inline)
- Hosting & CDN: Amazon S3 + Amazon CloudFront
- Security: Origin Access Control (OAC) + S3 Bucket Policy
- Domain: Default CloudFront domain (`.cloudfront.net`)


## 🚀 Deployment Steps (How I Set It Up)
1. Created S3 bucket `dre-simple-proj` with Block all public access enabled.
2. Uploaded `index.html` to the bucket root.
3. Created CloudFront distribution:
   - Origin: S3 bucket (REST endpoint: `dre-simple-proj.s3.amazonaws.com`)
   - Origin Access: Origin Access Control (OAC) with signing
   - Viewer Protocol Policy: Redirect HTTP to HTTPS
   - Default root object: `index.html`
4. Added bucket policy to allow only CloudFront (using distribution ARN)
   
