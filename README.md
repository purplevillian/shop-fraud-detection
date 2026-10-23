# Shop Fraud Checker

A simple, friendly web tool that helps people spot common warning signs before buying from a social media shop (Instagram, Facebook, TikTok, and similar).

It runs entirely in the browser. No data is collected or sent anywhere.

## Features

- Risk score from 0 to 100 with a Low, Medium, or High rating
- Checks for account age, follower count, unusually low prices, and risky payment methods
- Checklist of common red flags, such as pressure tactics or moving to a private chat
- Text scanner for listing or chat messages with known scam phrases
- Practical tips for safer buying

## Project structure

```
shop-fraud-checker/
├── index.html   # The entire site (HTML, CSS, and JavaScript)
└── README.md
```

## No seller contact needed

The checker is designed to work from information that is already public, so users never have to message the seller first:

- The checklist asks about what users can see on the profile, listing, or website, such as account age, reviews, and contact details.
- The **Research** section opens public tools in a new tab (search results, Trustpilot, Better Business Bureau, reverse image search, and domain registration lookup). The seller is never notified.

The site does not pull data from Instagram, Facebook, or TikTok automatically. Those platforms restrict automated access, so users read the profile themselves and answer the checklist.

## User customization

Visitors can click **Settings** (top right) to personalize the site:

- **Dark mode** on or off
- **Text size**: small, medium, large, or extra large
- **Accent color**: choose a preset or pick any color
- **Layout**: show or hide the tips, the safer habits section, and platform-specific tips
- **Custom warning phrases**: add your own words or phrases for the text scanner, with a weight from 1 to 30 that sets how much they raise the score
- **Reset**: restore all defaults

Settings and custom phrases are saved in the visitor's own browser using `localStorage`. Nothing is sent to a server, and each visitor's choices stay on their device.

## Run locally

Open `index.html` in any modern web browser. No build step or installation is needed.

## Host on GitHub Pages

1. Create a new repository on GitHub, for example `shop-fraud-checker`. Make it public.
2. Upload `index.html` and `README.md` to the repository, either through the web interface ("Add file" → "Upload files") or with Git:

   ```bash
   cd shop-fraud-checker
   git init
   git add .
   git commit -m "Add shop fraud checker"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/shop-fraud-checker.git
   git push -u origin main
   ```

3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
5. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
6. After a minute or two, your site will be live at:

   `https://YOUR-USERNAME.github.io/shop-fraud-checker/`

## Customizing

- To add or adjust warning phrases, edit the `RED_PHRASES` list in the `<script>` section.
- To change how strongly a checkbox affects the score, edit the `weight` values in the `checklist` array.
- To change the rating thresholds, edit the `levelFor` function.

## Disclaimer

This tool offers general guidance based on common warning signs. It cannot confirm whether a seller is legitimate, and it is not a substitute for independent research or professional advice. If you think you have been scammed, contact your bank or card provider right away and report the account to the platform and to your local consumer protection or fraud reporting agency.
