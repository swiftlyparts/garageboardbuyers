# Garage Board Buyers — Site

Static one-page site for garageboardbuyers.com. Board #357 (parent project #351). Single `index.html`, no build step, no JS frameworks.

## What this is

A landing page for the Garage Board Buyers program: garage door shops/techs ship us used logic boards and select parts, we pay them. Buying side only — never links to garagedoorinfospot.com, the eBay store, Swiftly Garage Doors, or any resale price. Brand is "Garage Board Buyers" only.

## How to swap in the VSL video

This is a VSL (video sales letter) page — the video is the main sell, the copy is secondary. Justin is shooting it. Once it's ready, open `index.html` and find `<div class="video-slot">` near the top of the hero section (there's an HTML comment right above it with both options spelled out):

- **Self-hosted file:** replace the placeholder div with
  ```html
  <video controls poster="thumbnail.jpg">
    <source src="video.mp4" type="video/mp4">
  </video>
  ```
  Drop `video.mp4` (and an optional `thumbnail.jpg`) in the same folder as `index.html`.
- **Hosted embed (YouTube/Vimeo/Wistia):** replace the placeholder div with
  ```html
  <iframe src="VIDEO_EMBED_URL" allowfullscreen></iframe>
  ```

## How to update the buy list

Open `index.html`, find the `<section class="alt" id="buylist">` block. The `$10` logic board row is live. The misc items ($3 each) go in the `.placeholder-block` div currently marked `LIST PENDING — JUSTIN` — replace that div's contents with a `.price-row` per item (copy the logic-board row's markup, drop the `.brands` div if not needed).

## How to swap the sign-up form URL

The sign-up section (`id="signup"`) has a placeholder div and an HTML comment right above it explaining the swap:

1. Get the published Airtable form URL from the `BBB Suppliers` table (Swiftly Ops Bus base `app2G2VCUpbvsmz9L`, table `tblOipSx6039YCHPE`) — Justin builds this in the Airtable UI.
2. Replace the `<div class="form-shell">...</div>` placeholder with:
   ```html
   <iframe src="FORM_EMBED_URL" width="100%" height="800" frameborder="0"></iframe>
   ```
3. Swap `FORM_EMBED_URL` for the real URL.

## Other placeholders still open (see also the wrap report)

- VSL video (Justin shooting this weekend) — the main sell for the page
- Misc buy-list items (Justin supplies)
- Sign-up form embed URL (Justin builds the form, gives URL)
- Contact email in the footer (currently `PLACEHOLDER@garageboardbuyers.com`)
- "Paid within X days" in the FAQ
- Minimum shipment answer in the FAQ

## DNS instructions (GitHub Pages custom domain)

Domain: `garageboardbuyers.com`, registered by Justin 9/12/26.

At your domain registrar, set:

**Apex domain (`garageboardbuyers.com`) — four A records:**
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**www subdomain — one CNAME record:**
```
www.garageboardbuyers.com  →  swiftlyparts.github.io
```

Then in the repo: Settings → Pages → Custom domain → enter `garageboardbuyers.com` → Save. The `CNAME` file in this repo already contains `garageboardbuyers.com`, so GitHub Pages should pick it up automatically once DNS resolves. Check "Enforce HTTPS" once the certificate provisions (can take a few minutes to a few hours after DNS propagates).

## Repo / Pages

- Repo: `swiftlyparts/garageboardbuyers` (public)
- Pages source: `main` branch, `/` (root)
- Live URL: see the wrap report on Return Reports row `recXprDiNX39ooosh` for the current Pages URL and commit hash.
