# Unsplash Scraper: Unsplash Scraper API for Python & Node.js (2026)

Scrape Unsplash photos by keyword, collection, topic or profile: image URLs, photographer, likes, EXIF, location, views, downloads. No login needed. JSON, CSV.

**[▶ Try the Unsplash Scraper free on Scrapely](https://scrape.ly/store/echofield/unsplash-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Unsplash data with the [Unsplash Scraper](https://scrape.ly/store/echofield/unsplash-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the unsplash scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Unsplash scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/unsplash-scraper) or from your code with the SDK.
- **Structured unsplash data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $1.50 per 1,000 photo results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Unsplash changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Unsplash data can you extract?

Scrape Unsplash photos by keyword, collection, topic or profile: image URLs, photographer, likes, EXIF, location, views, downloads. No login needed. JSON, CSV.

| Output field |
|---|
| `urls.thumb` |
| `altDescription` |
| `photographer.name` |
| `photographer.profileUrl` |
| `likes` |
| `width` |
| `height` |
| `color` |
| `premium` |
| `views` |
| `downloads` |
| `createdAt` |
| `photoUrl` |
| `urls.full` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/unsplash-scraper').call({"queries": ["nature"], "maxItems": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/unsplash-scraper').call(run_input={ "queries": [ "nature" ], "maxItems": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~unsplash-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "queries": [
    "nature"
  ],
  "maxItems": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Unsplash Scraper page](https://scrape.ly/store/echofield/unsplash-scraper).

## Pricing

**$1.50 per 1,000 photo results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/unsplash-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Unsplash with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Unsplash with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a unsplash scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~unsplash-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Unsplash legal?** This scraper collects publicly available data. Check Unsplash's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** unsplash scraper, unsplash scraper, unsplash scraper api, unsplash scraper python, unsplash scraper node.js,
scrape unsplash, unsplash data extraction, unsplash crawler, unsplash api, export unsplash data to csv, unsplash-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/unsplash-scraper).
