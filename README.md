# PageSage marketing site + privacy policy

Static two-page site for the PageSage Play Store listing. Zero-budget hosting via GitHub Pages.

- **`index.html`** — landing page (linked from Play Console "Website" field)
- **`privacy.html`** — privacy policy (linked from Play Console "Privacy policy" field AND from the Data Safety form)

Both files are single-page, self-contained HTML with embedded CSS. No build step, no external dependencies, no JavaScript. Match PageSage's Forest theme aesthetic so users clicking through from the app or Play Store land somewhere visually consistent.

## Deploy to GitHub Pages (free, ~10 minutes)

### One-time setup

1. **GitHub account** — already exists with username `lexioreader`. ⚠️ This username is now permanent for your public URLs; renaming later breaks every link in Play Console.

2. **Create a new public repository** named `pagesage-site` (project repo style — gives the URL `https://lexioreader.github.io/pagesage-site/`). Make the repo **public**. Don't initialize with a README, .gitignore, or license — we'll upload our own files.

   *(Alternative: name the repo `lexioreader.github.io` for a cleaner URL `https://lexioreader.github.io/` with no path. Either works — `pagesage-site` is fine and easier to organize alongside other projects later.)*

3. **Upload the two HTML files** via the GitHub web UI:
   - Click "Add file" → "Upload files" on the new repo's main page
   - Drag `index.html` and `privacy.html` (from this `lexio/docs/site/` folder)
   - Commit directly to `main`

4. **Enable GitHub Pages**:
   - Repo Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: `main`, folder `/ (root)`
   - Save

5. **Wait 1–2 minutes** for GitHub to build and deploy. The Pages settings page will show the live URL once ready:
   - Landing: `https://lexioreader.github.io/pagesage-site/`
   - Privacy: `https://lexioreader.github.io/pagesage-site/privacy.html`

### Use these URLs in Play Console

| Play Console field | URL |
|---|---|
| Store settings → Website | `https://lexioreader.github.io/pagesage-site/` |
| App Content → Privacy policy URL | `https://lexioreader.github.io/pagesage-site/privacy.html` |
| Data Safety form → Privacy policy link (if requested) | `https://lexioreader.github.io/pagesage-site/privacy.html` |

## Updating later

When you change something — adding a new SDK, enabling analytics, etc. — you must update the privacy policy:

1. Edit `privacy.html` (or this file in your repo via GitHub web UI)
2. Update the `Last updated: YYYY-MM-DD` line near the top
3. Commit. GitHub Pages auto-redeploys in ~1 minute.

The privacy policy URL stays the same forever, so the link in Play Console never needs to change.

## Future enhancements (not required for V1 launch)

- **Custom domain** (`pagesage.app` or similar): buy a domain (~$10–15/year on Namecheap), point a CNAME record at `lexioreader.github.io` (or set up GitHub Pages on a separate clean repo), add the domain in repo Settings → Pages → Custom domain. URLs become `pagesage.app` and `pagesage.app/privacy.html` — hides the `lexioreader` username completely and matches the brand. Better trust signal but not free.
- **Screenshots in the landing page** — once you have polished Play Store screenshots, drop them in alongside the feature cards.
- **Real Play Store badge** — replace "Coming soon on Google Play" with the official badge once the app is live. Get the SVG from https://play.google.com/intl/en_us/badges/.

## What's in each file

### `privacy.html`
- Compliant with COPPA (US), GDPR + Article 8 (EU under-16), UK Age Appropriate Design Code, CCPA/CPRA
- Discloses RevenueCat + Google Play Billing as the only third-party services in V1
- Documents the on-device data (vocab, highlights, notes, etc.) explicitly so users know what stays local
- Lists explicit "what we do NOT collect" — preempts the most common user concerns
- Email contact: `pagesage007@gmail.com`

### `index.html`
- Hero, six feature cards, privacy band, footer
- Forest theme palette (matches the app default)
- Mobile-responsive
- Privacy policy link surfaced in three places (top nav, privacy band, footer)
