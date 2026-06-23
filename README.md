[Google Lighthouse Checker](https://apify.com/gentle_cloud/google-lighthouse-checker?fpr=data)

## 🔍 Google Lighthouse Web Quality Checker

Run full Google Lighthouse audits on any web page using a built-in Lighthouse CLI and headless Chrome — no API key required. Get scores and detailed reports for Performance, Accessibility, SEO, and Best Practices.

## 🔥 How It Works

This Actor runs the Google Lighthouse CLI with headless Chromium inside a Docker container, performing the same audits you'd get from Chrome DevTools — but fully automated and at scale.

**Audit Categories:**

- **Performance**: FCP, LCP, TBT, CLS, Speed Index, TTI
- **Accessibility**: How well the page supports users with disabilities
- **Best Practices**: Adherence to modern web development standards
- **SEO**: Search engine optimization metrics

## 🛫 How to Use

1. **URLs to Audit**: Enter one or more web page URLs, e.g. `https://www.example.com`
2. **Audit Categories**: Choose which categories to audit, separated by commas. Options:

- `performance` - Performance
- `accessibility` - Accessibility
- `best-practices` - Best Practices
- `seo` - Search Engine Optimization
- Leave empty to audit all categories
3. **Device Type**: Choose `mobile` (phone emulation) or `desktop` (desktop emulation)
4. Click `Save & Start` to begin the audit
5. Export results in JSON, XML, CSV, Excel, or HTML format

> **Note**: Lighthouse audits are resource-intensive (approximately 30-60 seconds per URL). We recommend allocating at least 2048 MB of memory for this Actor.

## 📊 Sample JSON Output

```
{
    "url": "https://www.example.com",
    "strategy": "mobile",
    "checked_at": "2026-03-18 10:30:00 UTC",
    "performance_score": 92,
    "accessibility_score": 98,
    "best_practices_score": 100,
    "seo_score": 95,
    "first_contentful_paint": "1.2 s",
    "first_contentful_paint_score": 95,
    "largest_contentful_paint": "2.1 s",
    "largest_contentful_paint_score": 82,
    "total_blocking_time": "120 ms",
    "total_blocking_time_score": 90,
    "cumulative_layout_shift": "0.05",
    "cumulative_layout_shift_score": 96,
    "speed_index": "1.8 s",
    "speed_index_score": 88,
    "time_to_interactive": "3.2 s",
    "time_to_interactive_score": 78,
    "failed_audits_count": 5,
    "failed_audits": [
        {
            "id": "render-blocking-resources",
            "title": "Eliminate render-blocking resources",
            "score": 45,
            "displayValue": "Potential savings of 1,200 ms"
        }
    ],
    "final_url": "https://www.example.com/",
    "lighthouse_version": "12.0.0"
}
```

## 📈 Score Guide

| Score Range | Rating | Description |
| --- | --- | --- |
| 90-100 | 🟢 Good | Excellent web quality |
| 50-89 | 🟡 Needs Improvement | Room for optimization |
| 0-49 | 🔴 Poor | Significant optimization needed |

## 🔧 Maintenance

This Actor is regularly maintained and updated to improve audit accuracy and stability.