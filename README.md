# Toolbay — 15 free browser tools (ready to deploy)

Ye ek **100% static website** hai. Koi backend nahi, koi database nahi, koi API key nahi.
Links relative hain, is liye `website/index.html` ko double-click karke local preview bhi ho jata hai.
Sirf `website/` folder host karo aur site live ho jati hai.

---

## 1. Live karne ka tareeqa (5 minute)

### Option A — Netlify (sabse asaan, free)
1. https://app.netlify.com/drop kholo
2. `website` folder drag & drop kar do
3. Site foran live. Site settings → Domain management se apna domain add karo.

### Option B — Vercel
1. `npm i -g vercel` → `cd website` → `vercel --prod`

### Option C — GitHub Pages
1. Naya repo banao, `website` ka **andar ka saara content** root me push karo
2. Settings → Pages → Branch: `main` / root → Save

### Option D — cPanel / Hostinger shared hosting
`website` folder ka content `public_html` me upload kar do. Bas.

---

## 2. Live karne se PEHLE ye 3 cheezein change karo (zaroori)

1. **Domain** — saari files me `https://example.com` ko apne domain se replace karo:
   ```bash
   cd website
   grep -rl "https://example.com" . | xargs sed -i 's|https://example.com|https://yourdomain.com|g'
   ```
   (Windows par VS Code me Ctrl+Shift+H se "Replace in Files" kar lo.)
2. **Email** — `contact.html` me `hello@example.com` apna email daal do.
3. **Brand name** — agar naam badalna hai to `source/build.py` ki top pe `SITE_NAME` change karke `python build.py` chala do.

---

## 3. SEO setup — pehle 48 ghante

| Step | Kaam | Kahan |
|---|---|---|
| 1 | HTTPS on karo (Netlify/Vercel par automatic) | Host panel |
| 2 | Google Search Console me domain verify karo | search.google.com/search-console |
| 3 | `sitemap.xml` submit karo | Search Console → Sitemaps |
| 4 | Har tool page ko "URL Inspection → Request Indexing" | Search Console |
| 5 | Bing Webmaster Tools me bhi same karo (Bing se GSC import ho jata hai) | bing.com/webmasters |
| 6 | Google Analytics 4 property banao, gtag snippet har page ke `<head>` me paste karo — jagah pehle se comment me marked hai | `source/build.py` line ~55 |
| 7 | PageSpeed Insights par test karo, 95+ aana chahiye | pagespeed.web.dev |

**Site me pehle se jo SEO built-in hai:** unique title + meta description har page par, canonical tags, Open Graph + Twitter cards, JSON-LD schema (WebSite, SoftwareApplication, FAQPage, BreadcrumbList, ItemList), clean URL structure, breadcrumbs, internal linking, mobile-first responsive, dark mode, lazy-free light CSS (~8 KB), sitemap.xml, robots.txt, 404 page, PWA manifest.

---

## 4. Traffic plan — realistic timeline

Tool sites ka traffic **long-tail keywords** se aata hai. Ek page = ek keyword cluster.

- **Month 1–2:** Google indexing + 0–500 visits. Is dauran 10–15 naye tool pages add karo.
- **Month 3–6:** 2k–20k visits/month, jab pages "age calculator", "compress jpg" jaise queries par page 2–3 tak aate hain.
- **Month 6–12:** 50k–300k+ visits/month, agar tools 60–100 tak pohanch jayen.

**Traffic tez karne ke 5 kaam:**
1. **Zyada tools = zyada pages.** Har tool apna keyword laata hai. Target: 100 tools.
2. **Har page par 500+ words ka useful content** (abhi ~250 hai — expand karo, FAQs barhao).
3. **Backlinks:** Reddit (r/InternetIsBeautiful), Product Hunt, Hacker News, Quora answers, Facebook groups, LinkedIn post.
4. **Pinterest + YouTube Shorts:** "How to compress image without losing quality" type short videos, description me link.
5. **Language versions:** Urdu/Hindi/Arabic pages banao — competition bohat kam, traffic bohat.

**Next 20 tool ideas (high volume, easy):** image resizer, image to PDF, PDF merge, PDF split, background remover, GPA calculator, salary/tax calculator, currency converter, time zone converter, typing speed test, random number picker, lorem ipsum, base64 encoder, URL encoder, MD5/SHA hash, text diff, invoice generator, barcode generator, screen resolution test, countdown timer.

---

## 5. Kamai (monetization)

1. **Google AdSense** — approval ke liye chahiye: apna domain, 20+ quality pages, About/Contact/Privacy (teenon pehle se maujood hain), aur thora organic traffic. Approve hone ke baad script `<head>` me paste karo (comment marked hai) aur ads article ke darmiyan lagao — kabhi result ke ooper nahi.
2. **Ezoic / Monumetric** — 10k visits/month ke baad AdSense se 2–3x zyada RPM.
3. **Affiliate** — EMI/loan pages par finance offers, image tools par design software.
4. **Pro version** — bulk processing ya no-ads $3/month.

---

## 6. Naya tool add karna

`source/tools_data.py` kholo, kisi bhi existing `T(...)` block ko copy karo, ye fields bharo:
`slug, cat, name, title, desc, kw, blurb, body (HTML), js (JavaScript), article (HTML), faqs (list)`

Phir:
```bash
cd source && python build.py
```
Naya page, sitemap entry, footer link, related links — sab khud generate ho jayenge.

---

## 7. Folder structure

```
website/            <- ye upload karna hai
  index.html
  tools/*.html      (15 tool pages)
  about.html  contact.html  privacy.html  404.html
  assets/style.css  favicon.svg  cover.png
  sitemap.xml  robots.txt  manifest.json  _redirects
source/
  build.py          <- generator (settings top par)
  tools_data.py     <- saare tools ka data
  assets/style.css  <- design tokens yahan
```

Sab tools browser me chalte hain — koi file server par upload nahi hoti, isliye privacy strong hai aur hosting cost ~$0 rehta hai.
