# Ouszues PC Optimizer Website

This is a public download website for **Ouszues PC Optimizer**.

## Website pages

- `index.html` — homepage
- `features.html` — features page
- `install.html` — install guide page
- `faq.html` — FAQ page
- `safety.html` — safety information page
- `downloads.html` — download information page
- `download.html` — automatic download page
- `thanks.html` — thank-you page after download starts
- `downloads/` — folder for the actual app file

## Easy setup

### 1. Add your real app file

Put your app inside the `downloads` folder and name it exactly:

```text
Ouszues-PC-Optimizer.exe
```

The full path should be:

```text
downloads/Ouszues-PC-Optimizer.exe
```

If your app file has another name, open `download.html` and change:

```js
const installerUrl = "downloads/Ouszues-PC-Optimizer.exe";
const installerName = "Ouszues-PC-Optimizer.exe";
```

Also open `thanks.html` and update the `Download again` button.

### 2. Test the website on your computer

Double-click:

```text
index.html
```

Then press **Download**.

It should go:

```text
index.html → download.html → thanks.html
```

### 3. Make the website public

The easiest way is Netlify Drop:

1. Put all files in one folder.
2. Go to:

```text
https://app.netlify.com/drop
```

3. Drag your whole website folder onto the page.
4. Netlify gives you a public website link.

Make sure you upload all of these:

```text
index.html
features.html
install.html
faq.html
safety.html
download.html
thanks.html
downloads/Ouszues-PC-Optimizer.exe
```

## Important note

A static website cannot know the exact second the download fully finishes. So `download.html` starts the download automatically and then opens `thanks.html` after a short delay.

## Publish with GitHub Pages

### Option A: Upload app directly to the website repo

Use this if your `.exe` is smaller than 100 MB.

1. Create a GitHub account or log in.
2. Click **New repository**.
3. Name it for example:

```text
ouszues-pc-optimizer-site
```

4. Choose **Public**.
5. Upload all website files:

```text
index.html
features.html
install.html
faq.html
safety.html
download.html
thanks.html
README.md
downloads/Ouszues-PC-Optimizer.exe
```

6. Go to repository **Settings**.
7. Open **Pages**.
8. Under **Build and deployment**, choose:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/root**
9. Click **Save**.
10. Wait 1–3 minutes. GitHub will show your public website link.

Your website will look like:

```text
https://YOUR-USERNAME.github.io/ouszues-pc-optimizer-site/
```

### Option B: Use GitHub Releases for the app file

Use this if your `.exe` is large or you want a cleaner download system.

1. Upload the website files to the repo, but do not upload the `.exe` into `downloads`.
2. On GitHub, go to your repo.
3. Click **Releases**.
4. Click **Create a new release**.
5. Upload `Ouszues-PC-Optimizer.exe` as a release asset.
6. Copy the release asset download link.
7. Open `download.html` and replace:

```js
const installerUrl = "downloads/Ouszues-PC-Optimizer.exe";
```

with your GitHub release download link.

8. Also update the `Download again` link in `thanks.html`.
