# Publishing to GitHub — Step-by-Step Guide

## 1. Create a GitHub Account (if you don't have one)
Go to https://github.com and sign up.

## 2. Create a New Repository
1. Click the **+** button (top right) → **New repository**
2. Name it: `titan-customs`
3. Set to **Public** (required for free GitHub Pages hosting)
4. Click **Create repository**

## 3. Upload the Files
On the new repo page, click **uploading an existing file** and upload:
- `index.html`
- `logo.jpg`
- `README.md`

Click **Commit changes**.

## 4. Enable GitHub Pages
1. Go to **Settings** (tab at top of your repo)
2. Scroll to **Pages** in the left sidebar
3. Under **Source**, select `Deploy from a branch`
4. Choose `main` branch, `/ (root)` folder
5. Click **Save**

## 5. Your App is Live!
After ~60 seconds, your calculator will be live at:
```
https://YOUR_GITHUB_USERNAME.github.io/titan-customs/
```

---

## Alternative: Using Git Command Line

```bash
cd titan-customs
git init
git add .
git commit -m "Initial: Titan Customs for Titan Tides Logistics"
git remote add origin https://github.com/YOUR_USERNAME/titan-customs.git
git branch -M main
git push -u origin main
```

Then enable GitHub Pages as in Step 4 above.
