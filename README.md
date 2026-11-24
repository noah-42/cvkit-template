# My CV

Built with [cvkit](https://github.com/noah-42/cvkit): one data file, `cv.json`, becomes a designed page, a plain
ATS page (`/ats/`) and a PDF (`/cv.pdf`), published on GitHub Pages.

## Set up (once)

1. Name this repository `<your-username>.github.io` (or any name; then the site is at `<you>.github.io/<name>/`).
2. In the repository settings, under Pages, set Source to **GitHub Actions**.
3. Edit `cv.json` and push. The Action checks the data, builds the pages and the PDF, and publishes them.
   (The run started when the repository was created ends with "Almost there": Pages was not on yet. That is fine.)

## Work on it locally

```bash
uvx --from git+https://github.com/noah-42/cvkit cvkit serve
```

```bash
uvx --from git+https://github.com/noah-42/cvkit cvkit check --job job-ad.txt
```

Personal details you want only in your own PDF (phone, address) go in `private.json`, which is never committed:

```json
{"contact_line": ["+49 000 0000000"], "contact_list": ["Phone: +49 000 0000000"]}
```

```bash
uvx --from git+https://github.com/noah-42/cvkit cvkit pdf --private
```

Change the look in `css/style.css`. To change the layout, copy a template from cvkit's `cvkit/templates/` into a
`templates/` folder here; your copy wins.
