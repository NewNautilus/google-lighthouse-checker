[Google Lighthouse Checker](https://apify.com/alizarin_refrigerator-owner/google-lighthouse-checker?fpr=data)

# Google Lighthouse Checker

Run Google Lighthouse audits at scale. Get Core Web Vitals, performance, accessibility, SEO, and best practices scores for any URL or batch of URLs.

---

## Quick Start

### Test with Demo Mode (free, no API key needed)

```
{
  "demoMode": true,
  "urls": [
    "https://example.com"
  ],
  "url": "https://example.com"
}
```

### Run with real data

```
{
  "demoMode": false,
  "urls": [
    "https://example.com"
  ],
  "url": "https://example.com",
  "device": "mobile",
  "categories": [
    "performance",
    "accessibility",
    "best-practices",
    "seo"
  ],
  "throttling": "mobile4G",
  "includeFullReport": false,
  "includeScreenshots": true,
  "maxConcurrency": 1
}
```

---

## Input Parameters

| Parameter | Type | Default | Required | Description |
| --- | --- | --- | --- | --- |
| `urls` | array | - | No | List of URLs to run Lighthouse audits on |
| `url` | string | - | No | Single URL to audit (alternative to urls array) |
| `device` | string | `"mobile"` | No | Device to emulate for the audit |
| `categories` | array | `["performance","accessibility","best-practices","seo"]` | No | Which Lighthouse categories to run |
| `throttling` | string | `"mobile4G"` | No | Network throttling preset |
| `includeFullReport` | boolean | `false` | No | Include the full Lighthouse JSON report (larger output) |
| `includeScreenshots` | boolean | `true` | No | Include screenshots of the page (final screenshot and thumbnails) |
| `maxConcurrency` | integer | `1` | No | Maximum number of concurrent audits |
| `webhookUrl` | string | - | No | URL to POST results to when complete (Zapier, Make, n8n) |
| `demoMode` | boolean | `true` | No | Run in demo mode with sample data (no actual audits) |

---

## Pricing

This actor uses **pay-per-event** billing:

| Event | Description | Price |
| --- | --- | --- |
| Audit Run | Per Lighthouse audit | $0.08 |

**Demo mode is free** -- no charges for sample data.

---

## Troubleshooting

### "API error 429" or "Rate limit"

Too many requests. Wait a minute and try again, or reduce the number of items per run.

### No results or empty dataset

Check the run log for error messages. Common causes:

- Invalid input format (check the examples above)
- The target data doesn't exist or is too small to track

### How do I test without an API key?

Enable **Demo Mode** in the input. This returns realistic sample data so you can verify the output format works for your workflow.

---

**Built by John Rippy | [Actor Arsenal](https://actorarsenal.com)**