# Workshop

A business app for a lapidary and silversmithing studio: stock (rough, cut stones, jewellery, metals, equipment), cab and facet designs with diagrams, cutting and repair jobs, sales and invoices, market mode, money and GST, calculators, and a gemstone and supplier guide.

It is a single web page that installs on a phone or computer like an app and works offline. There is no account: **your records are stored on the device you use it on**, and, if you turn on sync, on the family sync server, encrypted on the device with the business’s own sync code.

## Put it on GitHub Pages

1. Sign in at [github.com](https://github.com) and click **New repository**. Name it, for example, `workshop`. Choose **Public** (GitHub Pages on a free account needs a public repository; your *records* are never uploaded, only the app itself). Click **Create repository**.
2. On the new repository page click **uploading an existing file**. Drag in everything from this folder: `index.html`, `manifest.webmanifest`, `sw.js`, `.nojekyll`, `README.md` and the five icon files (`icon.svg`, `icon-192.png`, `icon-512.png`, `maskable-512.png`, `apple-touch-icon.png`). There are no folders, so it works from a phone too. Click **Commit changes**.
   - Phone tip: the GitHub website upload works from Samsung Internet or Chrome too. Unzip the folder first in **My Files**.
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, **Branch** to `main` and folder `/ (root)`, then **Save**.
4. After a minute or two the page shows your address, for example `https://yourname.github.io/workshop/`.

## Install it on your computer

Open your address in **Chrome** or **Edge** and click the **install icon** at the right of the address bar (or the menu → **Install Workshop**). It opens in its own window from the Start menu or Dock, and works offline.

## Install it on your Samsung phone

**Samsung Internet:** open your address, tap the **menu (☰)** → **Add page to** → **Apps screen** (or tap the install icon in the address bar).

**Chrome:** open your address, tap **⋮** → **Add to home screen** → **Install**.

It then opens full screen from its own icon, and works without internet once it has been opened once. Long-press the icon for shortcuts to New sale, Market mode and Rough.

## Move your existing records across

Records in the Claude version stay there; the phone app starts empty.

1. In the Claude version, open **Settings**, scroll to **Backup** and tap **Download backup** (`Workshop backup ….json`).
2. Send the file to your phone (email, Google Drive, USB).
3. In the phone app, open **Settings**, scroll to **Backup**, tap **Restore from file** and pick the backup.

Backups include your photos.

## Keep your records safe

- Records live in the browser storage on the phone. **Clearing Samsung Internet or Chrome site data, or uninstalling the browser, deletes them.**
- Make a backup regularly: **Settings → Backup → Download backup**. The file goes to your **Downloads** folder. Copy it to Google Drive or email it to yourself.
- The app reminds you if you haven't backed up for two weeks.
- Each device keeps its own records. To keep your phone and computer in step: on the device with your records, **Settings → Sync with your other devices → Turn on sync → Start sync on this device**; on the other device, **Join with a code** and scan the QR code it shows. There's nothing else to set up.
- **Sync server (once, for whoever looks after the app):** deploy `workshop-sync-worker.js` as a Cloudflare Worker with a D1 database bound as `DB`, then put the worker's address in `sync-server.txt` in this repository (and in the app's repository).

## Updating the app

Upload the new `index.html` over the old one. In `sw.js`, change `const VERSION = 'v1'` to `'v2'` (and so on) so phones pick up the change. Next time you open the app, it will say an update is ready. Close the app and reopen it.

## Notes

- PDFs (invoices, quotes, labels) need an internet connection the first time, to fetch the PDF tool. After that they work offline.
- Supplier links and prices in the gemstone guide were researched in November 2026. Check them before ordering.
