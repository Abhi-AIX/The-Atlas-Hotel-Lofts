# The Atlas — Pre-Launch Configuration Checklist
**622 Rivergate Pkwy, Goodletsville, TN 37072**

---

## HOW TO USE THIS FILE
Work through each section top to bottom. Mark items ✅ as you complete them.
Items marked 🔴 are hard blockers — the site should not go live without these.
Items marked 🟡 are important but won't break the site.
Items marked 🟢 are nice-to-have before launch.

---

## SECTION 1 — CODE CONFIGURATION
*Open `index.html`, find the `CONFIG` block near the bottom of the file.*

### 1.1 Booking URL 🔴
```js
BOOKING_URL: 'https://www.yanolja.com/en/',
```
Replace with your exact Yanolja property booking page URL.
Every "Book a Room" and "Book Your Stay" button on the site uses this.

### 1.2 Lofts Website URL 🔴
```js
LOFTS_URL: 'https://theatlaslofts.com',
```
Replace with the real Atlas Lofts website URL.
Every "Explore The Lofts" button links here.

### 1.3 Pricing 🔴
Search the file for `$XXX` and `$X,XXX` — appears in 3 places:
- Hero section (hotel nightly + lofts monthly)
- Hotel section (nightly rate)
- Lofts section (monthly rate)

### 1.4 Domain / Canonical URL 🟡
Search for `theatlasgoodletsville.com` and replace with your actual domain everywhere it appears:
- `<link rel="canonical">` in index.html
- All `og:url` meta tags in index.html and policies.html
- Schema.org `"url"` field in the JSON-LD block

### 1.5 Google Badge 🟡
In the Reviews section, update 3 things:
- `href="https://g.page/r/XXXXXXXXXXXXXXXXXX/review"` → your Google Business review link
  (Find it: Google Business Profile dashboard → "Ask for reviews" → copy the link)
- `X.X` → your real star rating (e.g. `4.8`)
- `XXX Reviews on Google` → your real review count (e.g. `47 Reviews on Google`)

### 1.6 Contact Details 🔴
In the footer of `index.html`, replace:
- `hello@theatlas.com` → your real email address
- `+1 (000) 000-0000` → your real phone number
- Instagram `#` link → your real Instagram URL

Same in `policies.html` sidebar and footer.

### 1.7 Policies.html — Fill in TODOs 🟡
Open `policies.html` and search for `[TODO]`. Items to fill in:
- Front desk / reception hours
- Pet weight limit per animal
- Max number of pets per room
- Nightly pet fee amount
- Atlas Lofts minimum stay duration
- Breakfast availability (yes / no / coming soon)
- Elevator availability on property
- Hearing / visual accommodation options

---

## SECTION 2 — CONTENT & MEDIA

### 2.1 Hero Image 🔴
The current hero is a stock photo. Replace with a real photo of The Atlas exterior
or your best interior shot before launch. It is the first thing every guest sees.
- Recommended size: 1920×1080px minimum, JPG, under 400KB
- Replace the `src` in the `<section id="hero">` img tag

### 2.2 Hotel Room Image 🟡
Replace the stock room photo in the Hotel section with a real Atlas room photo.
- Find: `photo-1631049307264-da0ec9d70304` in index.html
- Recommended size: 1000×800px, JPG

### 2.3 Story Section Image 🟡
Replace with a real photo of the property exterior or a renovation/transformation shot.
- Find: `photo-1542314831-068cd1dbfeeb` in index.html

### 2.4 Gallery Images 🟡
Replace all 6 gallery images with real Atlas photos.
Each image is labeled g1–g6 in the gallery grid.
- Recommended: mix of rooms, common areas, exterior, detail shots
- Minimum 6 photos total

### 2.5 Neighborhood Cards 🟢
The 4 neighborhood cards (Grand Ole Opry, Long Hollow Winery, RiverGate Mall,
Mansker's Station) use stock Unsplash photos. These are fine to keep for now
but replace if you have better local shots.

### 2.6 OG / Social Share Image 🟡
Create a 1200×630px image for social sharing previews (iMessage, Instagram, LinkedIn).
- Should show the property name + exterior or best room shot
- Save as `og-image.jpg` in your site root folder
- Update all `og:image` meta tags in both index.html and policies.html

---

## SECTION 3 — BRANDING ASSETS

### 3.1 Favicon 🟡
Currently no favicon is set (commented out in the code).
Create and add:
- `favicon.ico` (32×32)
- `favicon-32x32.png`
- `favicon-16x16.png`
- `apple-touch-icon.png` (180×180) — used when guests save your site to their phone home screen

Then uncomment these lines in the `<head>` of both HTML files:
```html
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
```

Free tool to generate all sizes: https://realfavicongenerator.net

### 3.2 Logo File 🟢
Currently the logo is rendered in pure CSS/typography — this is intentional and
looks correct. If you ever have a proper SVG logo file, it can be swapped in.
Not required for launch.

---

## SECTION 4 — LEGAL

### 4.1 Privacy Policy Review 🟡
The privacy policy in `policies.html` is a working draft based on standard
hospitality practices. Before launch, have it reviewed by a legal professional,
especially if you are:
- Collecting email addresses (you are — email capture form)
- Processing payments through the site
- Using Google Analytics or similar tracking

### 4.2 Terms of Service 🟢
Currently not included. Consider adding if you plan to run direct bookings,
event inquiries, or loft applications through the site.

### 4.3 ADA / Accessibility Compliance 🟡
The site uses semantic HTML and ARIA labels throughout and is reasonably
accessible. Before launch, confirm the accessibility section in policies.html
reflects the actual physical accessibility features of 622 Rivergate Pkwy
(elevator, roll-in showers, accessible parking count, etc.).

---

## SECTION 5 — TECHNICAL / HOSTING

### 5.1 Domain Name 🔴
Purchase and point your domain to your hosting provider.
Recommended domain options (check availability):
- theatlasgoodletsville.com
- stayattheatlas.com
- theatlasnashville.com
- theatlas.tn (if available)

### 5.2 Hosting 🔴
This is a static HTML site — hosting is simple and cheap.
Recommended options:
- **Netlify** (free tier, drag-and-drop deploy, custom domain, SSL) ← easiest
- **Vercel** (free tier, similar to Netlify)
- **Cloudflare Pages** (free tier, extremely fast globally)
- Any basic web host (GoDaddy, Bluehost, etc.) also works

### 5.3 SSL Certificate (HTTPS) 🔴
Required for guest trust and Google ranking.
Netlify / Vercel / Cloudflare provide SSL automatically for free.
If using traditional hosting, enable Let's Encrypt SSL through your host's dashboard.

### 5.4 Email Address Setup 🟡
`hello@theatlas.com` (or your chosen address) should be a real inbox before launch.
Options:
- **Google Workspace** ($6/month) — recommended, works with Gmail
- **Zoho Mail** (free tier available)
- Most domain registrars include basic email forwarding

### 5.5 Google Analytics 🟢
Optional but recommended. Add GA4 tracking to understand where your guests
come from and what they do on the site.
- Create a GA4 property at analytics.google.com
- Add the tracking snippet just before `</head>` in both HTML files

### 5.6 Google Search Console 🟡
Submit your site to Google Search Console after launch so Google indexes it properly.
- Go to search.google.com/search-console
- Add your domain and verify ownership
- Submit your sitemap (or just submit the homepage URL)

---

## SECTION 6 — GOOGLE BUSINESS PROFILE

### 6.1 Claim / Create Your Google Business Profile 🔴
This is one of the highest-ROI things you can do before launch.
A verified Google Business Profile means your property shows up on Google Maps
and in local search results.

Steps:
1. Go to business.google.com
2. Search for "The Atlas" at 622 Rivergate Pkwy, Goodletsville TN
3. Claim the listing if it exists, or create a new one
4. Verify via postcard, phone, or email
5. Add: photos, hours, phone number, website URL, room categories

### 6.2 Get Your Google Review Link 🟡
Once your Business Profile is verified:
- Go to your Business Profile dashboard
- Click "Ask for reviews"
- Copy the short link
- Paste it into the Google badge in the Reviews section of index.html

### 6.3 Connect Website to Business Profile 🟡
In your Google Business Profile, add your website URL once it's live.
This improves local search ranking.

---

## SECTION 7 — EMAIL & MARKETING

### 7.1 Email Capture — Connect to a Real Service 🟡
The email signup form on the homepage currently shows a success message but
doesn't actually save emails anywhere. Before launch, connect it to:
- **Mailchimp** (free up to 500 contacts) ← recommended for simplicity
- **ConvertKit** (better for automation)
- **Klaviyo** (better for hospitality / e-commerce)

Once you pick a service, find the `handleEmailSubmit` function in index.html
and replace the TODO comment with the service's form submission code.

### 7.2 Welcome Email 🟢
Once email capture is wired up, write a simple welcome email for new subscribers.
One sentence about The Atlas, one line about what's coming (café, bar), a link
to book. Keep it short.

---

## SECTION 8 — SOCIAL MEDIA

### 8.1 Instagram 🟡
Instagram is the primary social channel for boutique hospitality.
- Create @theatlasgoodletsville (or closest available handle)
- Add the real URL to the Instagram link in the footer of index.html
- Post at least 6 photos before you start driving traffic to the site

### 8.2 Consistent Handles 🟢
Try to secure the same handle across:
- Instagram
- Facebook
- TikTok (growing channel for hotel discovery)
- Google Business (covered above)

---

## SECTION 9 — BEFORE YOU CLICK PUBLISH

### Final pre-launch checklist — run through this in order:

- [ ] All `[TODO]` items in policies.html are filled in
- [ ] CONFIG block updated with real Yanolja URL and Lofts URL
- [ ] Pricing updated ($XXX replaced with real rates)
- [ ] Contact email and phone number are real and working
- [ ] Hero image is a real photo of The Atlas (or best available)
- [ ] Favicon is in place
- [ ] OG image (og-image.jpg) is in the site root folder
- [ ] Domain is purchased and pointed at hosting
- [ ] SSL is active (URL shows https://)
- [ ] Canonical URL updated to real domain
- [ ] Google Business Profile is claimed and verified
- [ ] Google badge updated with real rating, count, and review link
- [ ] Email capture form is connected to Mailchimp or equivalent
- [ ] Instagram link in footer is real
- [ ] Policies page reviewed by legal professional (or noted as draft)
- [ ] Site tested on iPhone Safari and Android Chrome
- [ ] Both HTML files load without console errors
- [ ] All buttons tested — booking button opens Yanolja, Lofts button opens Lofts site
- [ ] Google Search Console — submit site after launch

---

## QUICK REFERENCE — Key Files

| File | Purpose |
|------|---------|
| `index.html` | Main website — all homepage content |
| `policies.html` | Policies, FAQ, Privacy Policy |
| `og-image.jpg` | Social share preview image (you create this) |
| `favicon.ico` | Browser tab icon (you create this) |

## QUICK REFERENCE — Key Locations in index.html

| What | How to find it |
|------|---------------|
| Booking + Lofts URLs | Search `CONFIG` near bottom of file |
| Pricing | Search `$XXX` |
| Google badge | Search `google-badge` |
| OG image URL | Search `og:image` |
| Canonical URL | Search `canonical` |
| Domain references | Search `theatlasgoodletsville.com` |
| Instagram link | Search `Instagram` in footer |
| Phone number | Search `000-000-0000` |
| Email address | Search `hello@theatlas.com` |

---

*Generated for The Atlas Hotel & Lofts · 622 Rivergate Pkwy, Goodletsville TN*
*Last updated: June 2025*
