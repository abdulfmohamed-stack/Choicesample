# CR Consulting — Command Compliance Intelligence

A browser-based AML/CTF compliance operations suite. Load a transaction workbook (`.xlsx` / `.xlsm`) and the dashboard classifies risk under the CR Consulting policy model, runs behavioral monitoring, and produces alerts, registers and exportable reports.

**All workbook processing happens locally in the browser.** No data is uploaded to any server.

## Run it

- **Locally:** open `index.html` in a modern browser.
- **GitHub Pages:** Settings → Pages → Source: `main` branch, `/ (root)`. Live at `https://<username>.github.io/<repo>/`.

Plotly and JSZip load from the jsDelivr CDN. If the CDN can't be reached, the page falls back to the copies in `js/vendor/`. Add `?demo=1` to the URL to load `sample/HTML.xlsx` if you add an anonymized sample there.

## Structure

```
index.html              page markup
css/styles.css          styles
js/engine.js            XLSX parser + risk analytics engine
js/workbook-writer.js   writes compliance worksheets back to Excel
js/insights.js          forecasting, correlation, narratives
js/app.js               UI and app logic
js/vendor/              offline fallback copies of Plotly and JSZip
sample/                 optional anonymized demo workbook
```

## Data privacy

`.gitignore` blocks `.xlsx`, `.xlsm`, `.xls` and `.csv` files so real customer data isn't committed. Only files in `sample/` are allowed — keep those synthetic.
