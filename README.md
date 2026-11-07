# PyScrape Studio

A single-file, browser-based **web scraping script generator**. Fill in a form, get a ready-to-run Python scraper. No install, no backend, just open `index.html`.

screenshot = <img width="1852" height="918" alt="image" src="https://github.com/user-attachments/assets/8afd1669-89e5-42d5-b8d9-1dd96ad7cd08" />


## What it does

Pick a framework, describe the page you want to scrape, and PyScrape Studio writes the Python script for you.

- **3 frameworks:** BeautifulSoup4 (static pages), Selenium (JavaScript pages), Playwright (modern / async)
- **Target config:** URL, container selector, request delay, any number of field selectors
- **Pagination:** follow a "Next" link or button up to N pages
- **Reliability:** automatic retries with exponential backoff, logging to `scraper.log`
- **Politeness:** optional `robots.txt` check, configurable delay, rotating user agents
- **Proxy support** in all three frameworks
- **Export:** CSV, JSON, or both
- **Presets:** e-commerce, news, job listings
- **Save / load config** as JSON
- **Data cleaning preview:** whitespace trim, price normalisation, de-duplication, null removal

## Quick start

1. Open `index.html` in any modern browser (or use the GitHub Pages link above).
2. Choose a framework and fill in the target details.
3. Click **Download Script**.
4. Install what the script needs and run it:

```bash
pip install requests beautifulsoup4     # for BeautifulSoup4 scripts
pip install selenium                    # for Selenium scripts
pip install playwright && playwright install chromium   # for Playwright scripts

python scraper_bs4.py
```

Want to try it safely? Use [books.toscrape.com](https://books.toscrape.com/), a site built for scraping practice:
container `article.product_pod`, fields `h3 a` and `p.price_color`, next link `li.next a`.

## Heads up: what is real and what is a demo

| Tab | Status |
|---|---|
| Script Generator | Real, produces working Python |
| Data Pipelines | Real, runs on sample data in the browser |
| Live Simulator | Demo, uses mock data |
| Rate Limits & Proxies | Demo, mock proxy list |
| Automation Jobs | Demo, UI only, nothing is scheduled |

## Roadmap

- [ ] Python backend (FastAPI) so the Live Simulator scrapes real pages
- [ ] Selector tester: paste HTML, check your selectors
- [ ] Auto-detect selectors from a page
- [ ] Real scheduler with run history
- [ ] Price-change alerts (email / Telegram)

## Responsible scraping

Only scrape sites you have permission to scrape. Check the site's Terms of Service and `robots.txt`, keep delays reasonable, and don't collect personal data.

## Built with

HTML, Tailwind CSS, vanilla JavaScript. Built with AI assistance.

## License

MIT
