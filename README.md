# Rebuild with Rucha

Static one-page site for **rebuildwithrucha.com**. No build step, no dependencies, no framework. One HTML file plus a few assets.

## Files

| File | What it is |
|---|---|
| `index.html` | The entire site. HTML, CSS and JS inline. Edit this to change anything. |
| `favicon.svg` | Browser tab icon. Placeholder — replace with a real mark. |
| `og-image.png` | 1200x630 image shown when the link is shared on WhatsApp, LinkedIn, X. Placeholder — replace with a designed one. |
| `robots.txt` | Lets search engines index the site. |
| `sitemap.xml` | Submitted to Google Search Console. |
| `vercel.json` | Security headers and asset caching. |

## Deploy — first time

### 1. Create the GitHub repo

On github.com, click **New repository**. Name it `rebuildwithrucha`. Public or private both work. Do **not** tick "Add a README", since this folder already has one.

### 2. Push these files

From this folder on your machine:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/rebuildwithrucha.git
git push -u origin main
```

If you would rather avoid the terminal: on the empty repo page click **uploading an existing file**, drag all the files in, and commit.

### 3. Connect Vercel

1. vercel.com → **Add New** → **Project**
2. **Import** the `rebuildwithrucha` repo
3. Framework Preset: **Other**
4. Build Command: leave empty
5. Output Directory: leave empty
6. **Deploy**

Live in about 30 seconds on a `.vercel.app` URL.

### 4. Point the domain

1. In Vercel: **Project → Settings → Domains → Add** → `rebuildwithrucha.com`
2. Also add `www.rebuildwithrucha.com` and set it to redirect to the apex
3. Vercel shows the DNS records to create. At your registrar, add them:
   - `A` record, host `@`, value `76.76.21.21`
   - `CNAME` record, host `www`, value `cname.vercel-dns.com`
4. Wait for propagation, usually minutes, occasionally a few hours. SSL is issued automatically.

**Always use the records Vercel actually shows you** — the values above are the current defaults and can change.

## Making changes

Edit `index.html`, then:

```bash
git add .
git commit -m "what changed"
git push
```

Vercel redeploys automatically. Every push is a new deployment and you can roll back to any previous one from the Vercel dashboard.

## Before this is really "launched"

Placeholders still in the file:

- [ ] Hero portrait — `.pframe` block, currently a coloured panel
- [ ] About portrait — `.aframe` block
- [ ] About write-up — dashed placeholder, needs Rucha's own words
- [ ] Credentials table — six empty rows (Education, Certification, Further training, Practice, Scope, Disclosure)
- [ ] Testimonials — the three quotes are invented. Replace with real ones, with written permission.
- [ ] Footer still reads "Sample site for illustration" — remove when the content is real
- [ ] Every button is `href="#"` — wire to Cal.com (booking) and Razorpay (payments)
- [ ] Email form is not connected — wire to MailerLite or similar
- [ ] No privacy policy, terms or refund policy pages. Razorpay will require the refund policy before approving the account.
- [ ] `og-image.png` and `favicon.svg` are placeholders

## Adding more pages later

Drop `privacy.html` in this folder and it is live at `/privacy` (clean URLs are on). Add each new page to `sitemap.xml`.
