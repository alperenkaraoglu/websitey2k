# Personal Portfolio Website

A high-performance, security-hardened personal portfolio website built with a Y2K aesthetic, hosted on GitHub Pages, and protected via Cloudflare Edge Network.

![Security Headers Grade](https://img.shields.io/badge/Security_Headers-A%2B-brightgreen)
![SSL/TLS](https://img.shields.io/badge/SSL%2FTLS-Full_(Strict)-blue)
![Platform](https://img.shields.io/badge/Hosted_on-GitHub_Pages-black)
![CDN/WAF](https://img.shields.io/badge/Protected_by-Cloudflare-orange)

## Live Demo
- **Primary Domain:** [alperenk.com](https://alperenk.com)

---

## Tech Stack & Infrastructure

- **Frontend:** HTML5, CSS3, JavaScript (Three.js / WebGL for 3D graphics)
- **Hosting:** GitHub Pages (Static site deployment)
- **Edge Network & DNS:** Cloudflare (Proxied DNS, Global CDN)
- **Security Rating:** **A+** on [SecurityHeaders.com](https://securityheaders.com)

---

## Security Architecture & Hardening

Static websites lack server-side runtime protections. To overcome this, the site leverages **Cloudflare Transform Rules** and **WAF Custom Rules** to inject security headers and enforce traffic policies at the edge:

### 1. HTTP Response Security Headers
- **Content Security Policy (CSP):** Configured with explicit `script-src-elem`, `blob:`, and `data:` directives to allow WebGL/Three.js dynamic 3D rendering while maintaining robust anti-XSS protection.
- **Strict Transport Security (HSTS):** Enforced via `max-age=31536000; includeSubDomains; preload` to eliminate SSL stripping risks.
- **X-Frame-Options:** `DENY` (Protects against Clickjacking attacks).
- **X-Content-Type-Options:** `nosniff` (Prevents MIME-type sniffing).
- **Referrer-Policy:** `strict-origin-when-cross-origin` (Prevents referrer leakage).
- **Permissions-Policy:** Restricts camera, microphone, and geolocation API usage.

### 2. Edge & WAF Mitigations
- **DoS / Rate Limiting:** Global rate limiting enforced via Cloudflare WAF to prevent resource exhaustion attacks.
- **Sensitive Path Protection:** Automated URI path blocking for sensitive structures (`/.git`, `/.env`, `/package.json`).
- **Hotlink Protection:** Restricts unauthorized third-party bandwidth leeching of static assets and 3D models.
- **TLS Hardening:** Enforced HTTPS redirection with strict minimum TLS standard.

---

## Local Development

Clone the repository and run locally using any standard static file server:

```bash
git clone [https://github.com/alperenkaraoglu/websitey2k.git](https://github.com/alperenkaraoglu/websitey2k.git)
cd websitey2k

# Option 1: Python HTTP Server
python3 -m http.server 8000

# Option 2: Live Server (VS Code Extension)
---

## Credits & Acknowledgments
- Original Y2K design and concept by [shutterkif-oss](https://github.com/shutterkif-oss/shutterkif-oss.github.io).
- Security architecture, WAF rulesets, CSP optimization, and deployment hardening by **Alperen Karaoğlu**.
