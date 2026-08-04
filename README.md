# BSOA 1 Class Schedule — GitHub Pages site

Two pages, sharing data through your browser's `localStorage` (same-origin, so
they only talk to each other once both are hosted on the same site):

- `index.html` — the public, view-only schedule
- `admin/index.html` — the admin panel (add / edit / delete classes and subjects)

## Deploy it

1. Create a new GitHub repository (or use an existing one).
2. Add these files to the **root** of the repo, keeping the folder structure:
   ```
   your-repo/
   ├─ index.html
   ├─ admin/
   │  └─ index.html
   └─ .nojekyll
   ```
3. Push to GitHub.
4. In the repo, go to **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to "Deploy from a branch",
   pick the branch (usually `main`), and folder `/ (root)`. Save.
6. GitHub will give you a URL like:
   ```
   https://your-username.github.io/your-repo/
   ```
   That's the view-only schedule. The admin panel is at:
   ```
   https://your-username.github.io/your-repo/admin/
   ```

## Notes

- `.nojekyll` tells GitHub Pages to skip Jekyll processing — not strictly
  required for this site, but it's a safe default for any static site with
  no Jekyll front matter.
- Editing only works on the `admin/` page. The main page is read-only and
  will auto-refresh if you have both pages open in the same browser and make
  a change on the admin side.
- Data is stored in your browser's `localStorage`, tied to the GitHub Pages
  domain. If you want to reset everything, open your browser's dev tools
  (F12) → Application/Storage tab → clear `localStorage` for that site.
- Anyone who can reach `/admin/` can edit the schedule — there's no login.
  If you want to keep it private, consider making the repo private and using
  GitHub Pages with access restrictions (available on GitHub Team/Enterprise),
  or password-protecting the folder via your own hosting instead.
