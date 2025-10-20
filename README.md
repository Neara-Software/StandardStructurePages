# Standard Structure Pages

Small interactive demos explaining orientation/rotation concepts. Deployed via **GitHub Pages**.

---

## Run locally (Python)

From the repo root:

```bash
python3 -m http.server 8080
```

Open:

- Hub: `http://localhost:8080/`
- Library Orientation: `http://localhost:8080/pages/library-orientation.html`

> Prefer Node?
>
> ```bash
> npx serve . -l 8080
> ```
> Then open the same URLs above.

---

## Add a new page

1) Copy an existing page:

```bash
cp pages/library-orientation.html pages/<your-new-page>.html
```

2) Edit the new file (title/content/script). Keep the shared stylesheet link near the top:

```html
<link rel="stylesheet" href="../assets/style.css">
```

3) Link it from the landing page (`index.html`):

```html
<!-- Add to the nav -->
<a href="pages/<your-new-page>.html">Your New Page</a>

<!-- Add to the list -->
<li><a href="pages/<your-new-page>.html">Your New Page</a></li>
```

4) Commit & push:

```bash
git add pages/<your-new-page>.html index.html
git commit -m "feat: add <your-new-page> demo"
git push
```

---

## Deploy to GitHub Pages

1) In GitHub: **Settings → Pages**
- **Source:** *Deploy from a branch*
- **Branch:** `main` and **/ (root)**

2) Your site URL:

```
https://neara-software.github.io/StandardStructurePages/
```

Pages live under `/pages/...`, e.g.:

```
https://neara-software.github.io/StandardStructurePages/pages/library-orientation.html
```

**Embedding in Fibery:** use the public page URL. Ensure HTTPS. If an embed is blank, the host may block iframes—GitHub Pages is fine.

---

## Repo layout (suggested)

```
StandardStructurePages/
├─ index.html                # Hub / landing
├─ pages/
│  ├─ library-orientation.html
│  └─ <your-new-page>.html
├─ assets/
│  ├─ style.css             # shared styles
│  └─ app.js                # shared helpers (optional)
└─ README.md
```

