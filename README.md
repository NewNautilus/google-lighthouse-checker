[Google Lighthouse Checker](https://apify.com/hi_world/google-lighthouse-checker?fpr=data)

# Google Lighthouse Checker - SEO-Focused Website Auditor

## What does Google Lighthouse Checker do?

This powerful SEO-focused website auditor runs comprehensive Google Lighthouse audits and delivers **actionable, agency-ready insights** for digital marketing agencies, SEO professionals, and web developers. With Google Lighthouse Checker, you can get:

- **Indexability snapshots** with instant "Can Google index this page?" answers
- **Core Web Vitals** with clear pass/fail status for LCP, CLS, TBT, and FCP
- **On-page SEO analysis** including title tags, meta descriptions, and canonical URLs
- **Normalized issues** categorized by severity (high/medium/low) and category
- **SEO agency summaries** with executive headlines and ready-to-use tickets for project management
- **Beautiful HTML reports** perfect for client presentations
- **Structured JSON data** optimized for batch analysis and integrations

## How to audit websites with Google Lighthouse Checker?

Google Lighthouse Checker is user-friendly, offering a smooth start even for those who have never run website audits before. Here's how to audit websites in 5 steps:

1. **Create a free Apify account** using your email.
2. **Open Google Lighthouse Checker.**
3. **Add the URL** you want to audit.
4. **Click the "Start" button** and wait 30-90 seconds for the audit to complete.
5. **View your reports** - Get beautiful HTML reports or download data in JSON, CSV, Excel, or HTML.

For more detailed instructions, see the Input and Output sections below.

---

## Input

To start your website audit, simply fill in the input form with your target URL and preferences:

**Required:**

- **URL** - The full website URL to audit (must include https://)

**Optional:**

- **Categories** - Choose which Lighthouse categories to test: Performance, Accessibility, SEO, Best Practices (default: all)
- **Device** - Select device emulation: desktop or mobile (default: desktop)
- **Throttling** - Enable network/CPU throttling for more realistic results (default: false)

Here's what the filled-out input looks like:

```
{
  "url": "https://example.com",
  "categories": ["performance", "accessibility", "seo"],
  "device": "desktop",
  "throttling": false
}
```

### Input Examples

**Basic audit (all categories, desktop):**

```
{
  "url": "https://example.com"
}
```

**Mobile SEO audit:**

```
{
  "url": "https://example.com",
  "categories": ["seo", "performance"],
  "device": "mobile"
}
```

**Fast SEO-only audit:**

```
{
  "url": "https://example.com",
  "categories": ["seo"],
  "throttling": false
}
```

---

## Output

After the Actor finishes its run, you'll get **three types of output**:

### 1. Beautiful HTML Report (Client-Ready)

**How to access:**

- Go to the **Storage** tab → **Key-value store** → Click **"View"** on `report.html`
- Or get the direct URL from the Dataset → `reports.htmlReport` field

**What's included:**

- 🎨 Professional, client-ready design
- 📊 SEO Agency Summary with health indicators
- ⚡ Core Web Vitals with color-coded pass/fail badges
- 🚨 Top 5 SEO Risks highlighted
- 🎫 Suggested Tickets ready for Jira/Asana/Monday
- 📈 Performance metrics and detailed recommendations

### 2. Structured Dataset (For Analysis)

**How to access:**

- Click the **Dataset** tab
- Choose your format: Table, JSON, CSV, Excel, or HTML

**Perfect for:**

- Filtering issues by severity
- Comparing multiple URLs
- Building dashboards
- Automating workflows
- Bulk analysis in Excel/Google Sheets

### 3. SEO-Focused JSON (Lightweight)

**How to access:**

- Go to **Storage** tab → **Key-value store** → Click **"View"** on `SEO_REPORT`

**Contains:**

- Scores (Performance, SEO, Accessibility, Best Practices)
- Indexability data
- On-page SEO metrics
- Core Web Vitals status
- Issues array
- SEO agency summary

Here's an example of the main dataset output:

```
{
  "url": "https://example.com",
  "fetchTime": "2024-11-29T08:00:00.000Z",
  "scores": {
    "performance": 0.89,
    "accessibility": 0.95,
    "seo": 0.92,
    "bestPractices": 0.87,
    "overall": 0.91
  },
  "coreWebVitalsLab": {
    "lcp": 1850,
    "lcpStatus": "pass",
    "cls": 0.05,
    "clsStatus": "pass",
    "tbt": 180,
    "tbtStatus": "pass",
    "fcp": 1200,
    "fcpStatus": "pass"
  },
  "indexability": {
    "isIndexable": true,
    "httpStatus": 200,
    "robotsTxtStatus": "valid",
    "hasCanonical": true,
    "canonicalUrl": "https://example.com/"
  },
  "onPage": {
    "title": "Example Website - Best Products",
    "hasMetaDescription": true,
    "metaDescription": "Shop the best products online...",
    "hasH1": true
  },
  "issues": [
    {
      "id": "meta-description",
      "title": "Document does not have a meta description",
      "description": "Meta descriptions help search engines understand your page content",
      "severity": "high",
      "category": "seo",
      "score": 0
    }
  ],
  "seoAgencySummary": {
    "overallHealth": "good",
    "coreWebVitalsPass": true,
    "criticalIssuesCount": 2,
    "readyForIndexing": true,
    "suggestedTickets": [
      {
        "priority": "High",
        "title": "Add meta description",
        "description": "Create compelling meta description (150-160 characters)"
      }
    ]
  },
  "reports": {
    "htmlReport": "https://api.apify.com/v2/key-value-stores/ABC123/records/report.html",
    "seoReport": "https://api.apify.com/v2/key-value-stores/ABC123/records/SEO_REPORT"
  }
}
```

---

## How can I use the data from Google Lighthouse Checker?

✨ **Monitor and track** website performance over time and identify optimization opportunities.

📋 **Create client reports** with professional, actionable insights ready to present.

🎯 **Prioritize fixes** using severity levels and impact assessments.

🔍 **Batch audit** multiple client websites and export to CSV for analysis.

📊 **Build dashboards** using structured JSON data for real-time monitoring.

🎫 **Generate project tickets** with ready-to-copy tasks for Jira, Asana, or Monday.

🚀 **Track Core Web Vitals** and ensure compliance with Google's performance standards.

✅ **Verify indexability** before launching new pages or making SEO changes.

📈 **Compare scores** across different time periods or competitor websites.

🛡️ **Identify accessibility issues** to ensure WCAG compliance.

---

## Integrate Google Lighthouse Checker with any app

Google Lighthouse Checker can be connected with almost any cloud service or web app thanks to integrations on the Apify platform:

- **Make**
- **Zapier**
- **Slack**
- **Airbyte**
- **GitHub**
- **Google Sheets**
- **Google Drive**
- and much more

Alternatively, you can use **webhooks** to trigger actions whenever an event occurs, e.g., get a Slack notification whenever an audit successfully completes.

---

## Understanding the Output

### Core Web Vitals Thresholds

| Metric | Good (Pass) | Needs Improvement | Poor (Fail) |
| --- | --- | --- | --- |
| **LCP** (Largest Contentful Paint) | < 2.5s | 2.5s - 4.0s | > 4.0s |
| **CLS** (Cumulative Layout Shift) | < 0.1 | 0.1 - 0.25 | > 0.25 |
| **TBT** (Total Blocking Time) | < 200ms | 200ms - 600ms | > 600ms |
| **FCP** (First Contentful Paint) | < 1.8s | 1.8s - 3.0s | > 3.0s |

### Score Interpretation

**Performance/SEO Score (0-100):**

- **90-100**: Excellent - Best practices followed
- **50-89**: Good - Minor improvements needed
- **0-49**: Poor - Significant issues to fix

**Issue Severity:**

- **High**: Critical issues affecting SEO/performance - fix immediately
- **Medium**: Important issues - should be fixed soon
- **Low**: Minor optimizations - fix when possible

---

## Use Cases & Examples

### Use Case 1: Client Audit Report

**Workflow:**

1. Run actor with client's URL
2. Get the HTML report URL from Dataset → `reports.htmlReport`
3. Send URL to client: "View your audit: [link]"
4. Client sees beautiful, professional report

### Use Case 2: Batch Website Audits

**Workflow:**

1. Run actor multiple times with different URLs
2. Go to Dataset → Export to CSV
3. Open in Excel/Google Sheets
4. Filter by indexability or severity

### Use Case 3: Weekly Monitoring

**Workflow:**

1. Schedule actor to run weekly (Apify Schedules)
2. Set up webhook to notify your team
3. Compare scores over time
4. Track improvements

### Use Case 4: Integration with Project Management

**Workflow:**

1. Run audit
2. Extract `seoAgencySummary.suggestedTickets`
3. Automatically create tickets in Jira/Asana
4. Assign to development team

---

## API Usage

### Using the Apify API with Node.js

```
const { ApifyClient } = require('apify-client');

const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });

// Run the actor
const run = await client.actor('YOUR_ACTOR_ID').call({
    url: 'https://example.com',
    categories: ['performance', 'seo'],
    device: 'desktop'
});

// Get the dataset
const { items } = await client.dataset(run.defaultDatasetId).listItems();
const result = items[0];

// Access data
console.log('SEO Score:', result.scores.seo * 100);
console.log('Indexable:', result.indexability.isIndexable);
console.log('HTML Report:', result.reports.htmlReport);

// Get critical issues
const critical = result.issues.filter(i => i.severity === 'high');
console.log(`${critical.length} critical issues found`);
```

### Using the Apify API with Python

```
from apify_client import ApifyClient

client = ApifyClient('YOUR_API_TOKEN')

# Run the actor
run = client.actor('YOUR_ACTOR_ID').call(run_input={
    'url': 'https://example.com',
    'categories': ['performance', 'seo'],
    'device': 'desktop'
})

# Get dataset items
items = client.dataset(run['defaultDatasetId']).list_items().items
result = items[0]

# Access data
print(f"SEO Score: {result['scores']['seo'] * 100}")
print(f"Indexable: {result['indexability']['isIndexable']}")
print(f"HTML Report: {result['reports']['htmlReport']}")

# Get critical issues
critical = [i for i in result['issues'] if i['severity'] == 'high']
print(f"{len(critical)} critical issues found")
```

Check out the [Apify API reference docs](https://docs.apify.com/api/v2) for full details or click on the API tab for more code examples.

---

## FAQ

### How much does it cost to use Google Lighthouse Checker?

Google Lighthouse Checker uses Apify's standard compute pricing. Costs depend on:

- **Run time**: Most audits complete in 30-90 seconds
- **Compute units**: Each audit uses approximately $0.10 worth of compute
- **Storage**: Reports stored in Key-value store (free for 7 days)

**Typical costs:**

- Single audit: ~$0.10
- 10 audits: ~$1.00
- 100 audits: ~$10.00

**Free tier includes:**

- $5 of free credits per month
- **~50 free audits per month**
- 7-day report retention

**💡 Tip:** The free tier is perfect for occasional audits or trying out the Actor. For agencies running 100+ audits/month, consider Apify's paid plans for better value.

### How can I access the HTML report?

There are two ways:

**Method 1 (Direct view):**

1. Go to the completed run
2. Click **Storage** tab → **Key-value store**
3. Click **"View"** on `report.html`

**Method 2 (Shareable link):**

1. Go to **Dataset** tab
2. Find the `reports.htmlReport` field
3. Copy the URL (e.g., `https://api.apify.com/v2/key-value-stores/ABC123/records/report.html`)
4. Share this URL with anyone

### How long are reports stored?

- **Free tier**: 7 days
- **Paid tier**: Indefinite retention available

**Tip**: Download important reports within 7 days on the free tier!

### Can I audit password-protected pages?

Not currently. The actor can only audit publicly accessible pages. For authenticated pages, you would need a custom solution.

### Why does my audit timeout?

Very slow websites (>2 minutes to load) may timeout. Solutions:

1. Set `throttling: false` for faster audits
2. Audit only specific categories: `["seo"]`
3. Try during off-peak hours when the site is faster

### Can I audit multiple URLs at once?

Yes! Use one of these methods:

1. **Run multiple times**: Call the actor separately for each URL
2. **Apify Batch**: Use Apify's batch running feature
3. **API loop**: Programmatically run the actor for each URL

Then export all results to CSV for analysis.

### Is it legal to audit websites with Google Lighthouse Checker?

Yes. Google Lighthouse Checker only accesses publicly available data that anyone can see in a browser. It does not:

- Bypass authentication
- Extract private data
- Violate terms of service
- Scrape personal information

However, be mindful of:

- Rate limiting (don't audit the same site hundreds of times per hour)
- Terms of service of the website being audited
- Privacy laws if reports contain any personal data

This tool is designed for legitimate SEO and performance auditing purposes.

---

## Troubleshooting

### "Cannot find HTML report"

**Solution:**

1. Check that the actor run completed successfully (look for ✅ in logs)
2. Go to **Storage** → **Key-value store** → Look for `report.html`
3. Or find the URL in Dataset → `reports.htmlReport` field

### "Report URL returns 404"

**Cause:** Key-value store data expired (7-day limit on free tier)

**Solution:**

- Upgrade to paid tier for longer retention
- Download important reports before they expire
- Re-run the audit to generate a new report

### "Audit is very slow or times out"

**Solution:**

```
{
  "url": "https://slow-website.com",
  "throttling": false,
  "categories": ["seo"]
}
```

Use `throttling: false` and audit only essential categories.

### "Missing some data in output"

**Note:** The actor provides what Google Lighthouse exposes. Some custom metrics (like word count, H1 analysis beyond presence) require additional crawling not included in Lighthouse.

---

## What makes Google Lighthouse Checker different?

| Feature | Standard Lighthouse | Google Lighthouse Checker |
| --- | --- | --- |
| Performance Score | ✅ | ✅ |
| SEO Score | ✅ | ✅ |
| Indexability Check | ❌ | ✅ Complete analysis |
| Core Web Vitals Pass/Fail | ⚠️ Just numbers | ✅ Clear pass/fail/needs-improvement |
| Issue Severity | ❌ | ✅ High/Medium/Low |
| Recommended Actions | ⚠️ Generic | ✅ Specific, actionable |
| Executive Summary | ❌ | ✅ SEO-focused |
| Ready-to-Use Tickets | ❌ | ✅ For Jira/Asana/Monday |
| Beautiful HTML Report | ⚠️ Technical | ✅ Client-ready |
| Batch Analysis | ❌ | ✅ CSV export |
| Agency Workflow | ❌ | ✅ Optimized |

---

## Your feedback

We're always working on improving the Actor's performance. If you have any technical feedback or found a bug, please create an issue on the Actor's Issues tab in Apify Console.

---

## Summary

Google Lighthouse Checker gives you:

✅ **Beautiful, client-ready HTML reports**

✅ **Clear pass/fail status for Core Web Vitals**

✅ **Instant indexability checks**

✅ **Severity-based issue prioritization**

✅ **Ready-to-use project tickets**

✅ **Batch-friendly CSV exports**

✅ **API integration ready**

**Start auditing smarter today!** 🚀