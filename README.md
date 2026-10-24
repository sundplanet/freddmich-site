# FREDDMICH INTEGRATED SOLUTIONS — Company Website

Static company website (plain HTML/CSS). No build step required.
Hosted on **Cloudflare Pages** with **auto-publish from GitHub** — every time you
save a change on GitHub, the live site updates automatically in about a minute.

## Files in this repo

| File | Purpose |
|------|---------|
| `index.html` | The whole website (edit text, clients, colors here) |
| `logo.png` | Company logo used in the header, hero and footer |
| `404.html` | Friendly "page not found" page |
| `_headers` | Security headers applied by Cloudflare Pages |
| `.gitignore` | Tells Git which junk files to ignore |

---

## PART A — Put this code on GitHub (one time)

### Option 1: Upload in the browser (easiest, no tools)
1. Create a free account at https://github.com and sign in.
2. Click the **+** (top-right) → **New repository**.
3. Repository name: `freddmich-website`  → keep it **Public** (or Private) → **Create repository**.
4. On the new repo page click **uploading an existing file**.
5. Drag **all the files from this folder** (index.html, logo.png, 404.html, _headers, .gitignore) into the page.
6. Click **Commit changes**.

### Option 2: Using Git on your computer
```bash
cd path/to/this/folder
git init
git add .
git commit -m "Initial FREDDMICH website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/freddmich-website.git
git push -u origin main
```

---

## PART B — Connect GitHub to Cloudflare Pages (one time)

1. Sign in at https://dash.cloudflare.com (free account).
2. Left menu → **Workers & Pages** → **Create** → **Pages** tab → **Connect to Git**.
3. Click **Connect GitHub**, authorise Cloudflare, and pick the
   `freddmich-website` repository.
4. On the build settings screen, leave everything at the defaults — this is a
   plain static site, so:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`  (root)
5. Click **Save and Deploy**.
6. After ~1 minute your site is live at `https://freddmich-website.pages.dev`.

---

## PART C — How to edit from now on (the whole point)

You never re-upload manually again. To change anything:

1. Go to your repo on github.com and open the file (usually `index.html`).
2. Click the **pencil (Edit) icon**.
3. Make your change, scroll down, click **Commit changes**.
4. Cloudflare detects the commit and **automatically rebuilds and republishes**.
   Refresh your live site after ~1 minute — done.

You can also see every past version under the repo's **commit history** and roll
back anytime.

---

## Common edits (all inside `index.html`)

- **Phone number:** find `+234 XXX XXX XXXX`
- **Email:** find `info@freddmich.com`
- **Stat numbers:** find `50+`, `30+`, `24/7`, `100%`
- **Add / change a client:** copy a `<div class="client"> ... </div>` block in the
  "Trusted by" section and edit the name, location, icon and monogram.
- **Replace a client badge with a real logo:** drop the logo file into the repo,
  then replace that client's `<div class="clogo">...</div>` with
  `<img src="client-logo.png" alt="Client Name" style="width:84px;height:84px;object-fit:contain">`.
- **Brand colors:** the `:root { ... }` block at the top of the file
  (gold = `#C5A059` / `#D4AF37`, background black).

---

## PART D — Add your own domain (optional)

1. In your Pages project → **Custom domains** → **Set up a domain**.
2. Enter your domain (e.g. `freddmich.com`).
3. Follow the DNS instructions. If the domain's DNS is already on Cloudflare it
   is automatic; otherwise add the CNAME record Cloudflare shows you.
4. SSL (https) is issued automatically and free.

---

## Notes

- **The contact form is live** and sends submissions to
  `info@freddmichsoluttions.com.ng` using the free **FormSubmit** service (no
  account or server needed). The **first time** someone submits the form,
  FormSubmit emails that address a one-time confirmation link — click it once to
  activate, and all future submissions arrive in the inbox automatically.
  To change the destination address, edit the form's `action="https://formsubmit.co/..."`
  line in `index.html`.
- Keep `index.html` and `logo.png` together — the page links to `logo.png`.
