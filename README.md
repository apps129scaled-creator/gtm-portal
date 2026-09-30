# gtm-portal
All leads live in one Supabase database (about 550,000 people), and GTM engineers reach it only through the GTM API with a personal key. You can add leads and pull lists; you cannot edit or delete anything already stored.

`index.html` is a single-file web tool for the GTM API (plain HTML/CSS/JS, no build step, no external scripts).

## Using it

1. Open the site and paste your personal API key when asked. It is saved in your browser's localStorage only and sent as the `x-api-key` header; it never goes in a URL. Use **Change key** in the header to replace or forget it.
2. Tabs:
   - **Upload**: pick a CSV, a client (or "New client…") and a list name (`audience - source - month`). Files over 25,000 rows are split into 25,000-row parts (header kept on each) and uploaded in sequence; the summary is totalled across parts. If a part fails, **Retry remaining parts** continues from where it stopped.
   - **Pull by client**: download a client's leads (email / linkedin / generic), optionally for one list.
   - **Pull by domains**: upload a CSV of domains or paste them, and download matching people and/or generic emails.
   - **Catalog**: searchable, sortable table of every client list. It takes about 30 seconds to load, is cached for the session, and feeds the client and list dropdowns. Use **Refresh** (or ↻ next to a dropdown) to reload it.

## Hosting on GitHub Pages

1. In the repo on GitHub, go to **Settings > Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose branch **main** and folder **/ (root)**, then **Save**.
4. After a minute the site is live at `https://<org>.github.io/gtm-portal/`.

To run it locally, just open `index.html` in a browser.
