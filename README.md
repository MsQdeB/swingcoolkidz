# Swing Cool Kidz — Website

A single-page site for the Swing Cool Kidz (Đà Nẵng swing dance community).

Everything lives in **`index.html`** (self-contained: styles + JavaScript inline). No build step, no dependencies — just host the file.

## Edit the site

Open `index.html` and look for the two clearly-marked blocks near the bottom `<script>`:

1. **`WHATSAPP_INVITE`** — replace `"#"` with your real WhatsApp group invite link
   (e.g. `https://chat.whatsapp.com/XXXXXXXX`).

2. **`EVENTS`** — every calendar date is generated from these rules, so the calendar
   is always correct for any month you browse to (past or future):

   ```js
   blends: { weekday: 4, nth: [1, 3], ... }  // 1st & 3rd Thursday
   hyatt:  { weekday: 3, nth: [2, 4], ... }  // 2nd & 4th Wednesday
   ```

   - `weekday`: 0 = Sunday … 6 = Saturday
   - `nth`: which occurrences in the month (1-based). Change to `[2, 4]`, `[1, 2, 3]`, etc.

Text content (hero, venue info, menus, addresses) is plain HTML further up — edit directly.

## Preview locally

Just open the file:

```sh
open index.html          # macOS
# or
python3 -m http.server   # then visit http://localhost:8000
```

## Deploy (getting "swingcoolkidz" in the URL — no domain purchase)

### Option 1 — GitHub Pages (free)
1. Create a GitHub repo named **`swingcoolkidz`**.
2. Push this folder to it.
3. Repo → **Settings → Pages** → *Source: Deploy from a branch* → branch `main`, folder `/ (root)`.
4. Your site appears at:
   **`https://<your-username>.github.io/swingcoolkidz/`** ← contains "swingcoolkidz"

### Option 2 — Free subdomain containing the name (recommended if you want it as the root URL)
- **Netlify** → drag-and-drop this folder → **`https://swingcoolkidz.netlify.app`**
- **Vercel** → import the repo → **`https://swingcoolkidz.vercel.app`**
- **Cloudflare Pages** → **`https://swingcoolkidz.pages.dev`**

All free, all give you `swingcoolkidz` in the link without buying a domain.
If you later buy `swingcoolkidz.com`, you just point it at the same host.
