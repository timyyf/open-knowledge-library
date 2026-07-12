# Open Knowledge Library · Multilingual Archive

A visual, multilingual layer on top of open knowledge. It surfaces free programming
books and courses (from [free-programming-books](https://github.com/EbookFoundation/free-programming-books))
organized into 8 language shelves, while keeping the English original as the source of
authority. Owned & curated by [Thiago Reed](https://open.spotify.com/intl-pt/artist/16h8q9iOGYIibP6pJWQHg3?si=BgfwKM_lR3ySB7csRBiaTQ).

Single self-contained `index.html`. No build step, no dependencies to install. Just open it.

## Features

- 8 language shelves: United Kingdom, Brazil, Spain, Germany, Japan, South Korea, China, Canada
- Switching language rewrites the whole page (hero, filters, footer) and swaps the shelf
- Localized book titles with a "Translated" badge; English link kept as authority
- Live search, level/format filters, category tabs
- Light + dark ("night shelf") mode
- Book detail modal
- Animated dotted-surface wave background in the hero

## Run locally

Just open the file:

```bash
open index.html          # macOS
# or double-click index.html
```

Or serve it (nicer for testing):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Editing the content

Everything lives in `index.html`. Look for these blocks near the bottom `<script>`:

- `languages` — the 8 shelves (flag, country, language label)
- `i18n` — all UI strings per locale
- `categoryDefs` — categories and their translated labels
- `pool` — the book database. To add a book, copy one entry and edit:
  - `langs`: which shelves show it
  - `tl`: localized titles per locale
  - `dl`: localized descriptions per locale
  - `url`: link to the original resource

## Publish free on GitHub Pages

1. Create a repo on GitHub (e.g. `open-knowledge-library`).
2. Put `index.html`, `README.md` and `.gitignore` in a folder, then:

```bash
git init
git add .
git commit -m "Initial commit: Open Knowledge Library"
git branch -M main
git remote add origin https://github.com/YOUR_USER/open-knowledge-library.git
git push -u origin main
```

3. On GitHub: **Settings → Pages → Source: `main` / root**. Your site goes live at
   `https://YOUR_USER.github.io/open-knowledge-library/`.

Future updates are just `git add . && git commit -m "..." && git push`.

## Credits

- Content: [EbookFoundation/free-programming-books](https://github.com/EbookFoundation/free-programming-books)
- Fonts: Fraunces, Inter, IBM Plex Mono, Noto Sans JP/KR/SC (Google Fonts)
- Icons: [Lucide](https://lucide.dev)

## License

MIT for the site code. Linked resources keep their own licenses.
