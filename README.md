# CaughtLiveGG — Public Site

Static landing page + privacy policy + terms of service for CaughtLiveGG.
Hosted on GitHub Pages so we have URLs we can give to TikTok / YouTube /
other API reviewers.

## Final URLs after setup

- Landing:  https://gamerhacker137.github.io/caughtlivegg/
- Privacy:  https://gamerhacker137.github.io/caughtlivegg/privacy.html
- Terms:    https://gamerhacker137.github.io/caughtlivegg/terms.html

## One-time setup (do this once)

### 1. Edit your email into both files
Open `privacy.html` and `terms.html`. Find the line `[YOUR EMAIL HERE]` in
each (near the bottom in "Contact Us") and replace with a clean email like
`caughtlivegg@gmail.com`. **Do not use Coolshitforu1@gmail.com** — it
contains profanity and TikTok reviewers will reject the app.

### 2. Create the repo on GitHub
Go to https://github.com/new and create a public repo:
- Name:  `caughtlivegg`
- Visibility: **Public** (required for GitHub Pages free tier)
- Don't initialize with README (this folder already has one)

### 3. Push this folder
Open a terminal in this folder (`caughtlivegg-site`) and run:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/gamerhacker137/caughtlivegg.git
git push -u origin main
```

GitHub will ask you to log in or use a personal access token. If you don't
have git installed: download from https://git-scm.com/download/win

### 4. Enable GitHub Pages
In the repo on github.com:
- Settings → Pages
- Source: **Deploy from a branch**
- Branch: **main** / folder: **/ (root)**
- Save

Wait ~2 minutes. The site will be live at:
**https://gamerhacker137.github.io/caughtlivegg/**

### 5. Verify on TikTok
Back in the TikTok developer portal:
- Pick **URL prefix** verification method
- Enter prefix: `https://gamerhacker137.github.io/caughtlivegg/`
- TikTok will give you a signature file (e.g. `tiktok-developers-site-verification.txt`)
- Download it
- Place it in this folder (next to `index.html`)
- Commit and push:
  ```bash
  git add tiktok-developers-site-verification.txt
  git commit -m "Add TikTok verification"
  git push
  ```
- Wait ~30 seconds for GitHub Pages to redeploy
- Click **Verify** in TikTok

Verification should pass instantly because TikTok will fetch
`https://gamerhacker137.github.io/caughtlivegg/tiktok-developers-site-verification.txt`
and find the signature.

## Updating the site later

Edit any file, then:
```bash
git add .
git commit -m "what you changed"
git push
```
GitHub Pages auto-redeploys within ~1 minute.
