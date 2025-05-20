# IP Hub – Initial Deployment Documentation

**Live Site:** [https://iphub.exchange](https://iphub.exchange)

---

## 🔑 SSH Access Setup
- SSH key generated locally using `ssh-keygen`
- Public key added to `/root/.ssh/authorized_keys` on DigitalOcean droplet
- SSH config set up for simplified access:
  ```ini
  Host iphub
    HostName 143.110.151.0
    User root
    IdentityFile "C:/Users/Chris Fitzgerald/.ssh/id_rsa_iphub"


🌐 DNS and Hosting
Domain registered and DNS managed via Cloudflare

A record for iphub.exchange → 143.110.151.0 (proxied)

🔧 Web Server (Nginx)
Static site served via /var/www/html/index.html

Nginx installed with:

sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d iphub.exchange

Certbot SSL added with:
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d iphub.exchange

🔒 SSL and Security
Cloudflare SSL set to Full (Strict)

HTTPS redirection enabled via Cloudflare ("Always Use HTTPS")

🎨 Frontend Assets
index.html created manually (no frontend framework)

iphub-logo-v2.png used as branding logo

Responsive layout with inline CSS

✉️ Email Signup Form (Guestbook)
Handled by Formspree

Live form endpoint: https://formspree.io/f/mdkgjdwp (replace with actual)

Posts email to Formspree backend for notification + tracking
https://formspree.io/f/mdkgjdwp

📌 Next Steps
Add favicon

Add analytics (Plausible or GA)

Begin version control with Git

Optimize mobile layout and add success message inline

📅 Deployment Date
Initial live version deployed: May 19–20, 2025

---

## ✅ Git Setup

If you haven’t yet:
```bash
cd /var/www/html/
git init
git add index.html iphub-logo-v2.png README.md
git commit -m "Initial IP Hub landing page with logo, form, and HTTPS"
