# Lakes Region Community Guides: Flipbook Website

A small website that shows Tanner McKim's 20 Lakes Region community guides as page-turning digital booklets. It's built to be published free on GitHub Pages and linked from tannermckim.verani.com.

## What's in this folder

| File / folder | What it is |
|---|---|
| `index.html` | The guide library: a cover grid of all 20 towns, with search |
| `guide.html` | The flipbook viewer (opens as `guide.html?town=belmont`, etc.) |
| `styles.css` | Shared look and feel |
| `guides.js` | The list of towns. Edit this to add or remove a town |
| `guides/<town>/` | Each guide's pages as images (`1.webp` cover through `4.webp` back cover) plus `thumb.webp` |
| `pdf/` | The original print-quality PDFs, for the "Download PDF" button |

No outside code libraries are used, so nothing can break when someone else's code changes.

## Publish it on GitHub Pages (one time, about 15 minutes)

1. Sign in at github.com and create a **new repository** named `lakes-region-guides`. Set it to **Public** (required for free GitHub Pages).
2. Upload the contents of this folder (not the folder itself) to the repository:
   - **With VS Code / git (easiest for this many files):** clone the empty repo, copy everything from this folder into it, then commit and push.
   - **In the browser:** click "uploading an existing file." GitHub's web uploader takes about 100 files per upload, so do it in two rounds: first drag in `index.html`, `guide.html`, `styles.css`, `guides.js`, `README.md`, and the `pdf` folder; commit; then drag in the `guides` folder and commit again. Keep the folder structure exactly as it is.
3. In the repository, go to **Settings → Pages**. Under "Build and deployment," choose **Deploy from a branch**, pick **main** and **/ (root)**, and save.
4. Wait a minute or two. Your site will be live at:
   `https://YOUR-GITHUB-USERNAME.github.io/lakes-region-guides/`
5. Open it and click through a couple of guides on your phone and computer to confirm everything loads.

## Put it on your BoldTrail website

1. Open `lakes-region-community-guides-hub.html` (saved next to this folder).
2. Use **Find & Replace** to change `https://YOUR-GITHUB-USERNAME.github.io/lakes-region-guides` to your real GitHub Pages address from step 4 (no trailing slash).
3. In BoldTrail's Page Editor, create a new page, add a **Custom HTML** block, and paste everything between `<!-- START -->` and `<!-- END -->`.
4. Set the title tag, meta description, and URL slug suggested at the top of that file.

To send someone straight to one town, link to `.../guide.html?town=gilford` (use the town's lowercase name, with dashes for spaces, like `center-harbor` or `new-durham`).

## Updating or adding a guide

**Replace a guide** (for example, a new Belmont version):
- Swap in the new PDF at `pdf/belmont-community-guide.pdf`.
- Replace the page images in `guides/belmont/` (`1.webp` = front cover, `2.webp` = inside left, `3.webp` = inside right, `4.webp` = back cover, `thumb.webp` = small cover). Claude can regenerate these from a new PDF in a minute.

**Add a new town:**
- Add its folder under `guides/`, its PDF under `pdf/`, and one line to `guides.js`.

Then commit and push (or upload) the changes. GitHub Pages updates within a minute or two.

## Notes

- Page images are about 100–170 KB each, so a whole guide loads in roughly half a megabyte, even on a phone.
- On computers the guide opens as a two-page book with a page-turn animation. On phones it shows one page at a time; readers tap or swipe to turn, and "Full size" lets them zoom in.
- Before publishing, confirm with Verani that posting the community guides publicly is fine.
