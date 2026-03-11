# Company Jobs Tracker

Track new and removed job listings per company across 18 StepStone Group portals. Structured change detection output — know when companies are hiring before your competitors.

Powered by the Apify actor:
https://apify.com/blackfalcondata/company-jobs-tracker

## What it does

Input a list of companies. On each run, get a structured diff: which jobs are new, which were removed, and how many are unchanged. Built for recruitment pipelines, sales intelligence, and investor due diligence.

## Example input
```json
{
  "companies": [
    { "name": "SAP", "geo": "DE" },
    { "name": "Unilever", "geo": "TOTALJOBS" },
    { "name": "Sasol", "geo": "PNET" }
  ],
  "maxResultsPerCompany": 50
}
```

## Example output
```json
{
  "company": "SAP",
  "geo": "DE",
  "scrapeOutcome": "success",
  "counts": {
    "new": 3,
    "removed": 1,
    "unchanged": 42,
    "total": 45
  },
  "newJobs": [
    {
      "title": "Senior Java Developer",
      "company": "SAP SE",
      "url": "https://www.stepstone.de/stellenangebote--Senior-Java-Developer-..."
    }
  ]
}
```

## Key features

- Company-level change detection across 18 StepStone Group portals
- Exact company targeting via \`companyId\` server-side filter
- Two-run removal confirmation prevents false removals
- Calibration mode to validate company name matching before tracking
- One record per company per run — predictable, pipeline-ready output
- $0.05 per company per run

## Supported portals

- stepstone.de (Germany)
- stepstone.at (Austria)
- stepstone.be (Belgium)
- stepstone.nl (Netherlands)
- totaljobs.com (United Kingdom)
- cwjobs.co.uk (United Kingdom)
- caterer.com (United Kingdom)
- nijobs.com (Ireland)
- jobs.ie (Ireland)
- pnet.co.za (South Africa)
- and 8 more UK vertical portals

## Use cases

- **Recruitment** — monitor client companies for new openings
- **Sales intelligence** — track hiring as a buying signal
- **Investor due diligence** — monitor portfolio company hiring velocity
- **Competitor intelligence** — detect strategic pivots from job mix changes
- **Market research** — quantify hiring trends across an industry

## Documentation

Full documentation, input/output reference, and onboarding guide:
https://apify.com/blackfalcondata/company-jobs-tracker

## Related

- [StepStone Jobs API](https://github.com/BlackFalconData/stepstone-jobs-api) — search and extract job listings from StepStone portals
