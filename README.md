# Tech Startup ATS Jobs, Tech Stack & Hiring Intent Scraper (Greenhouse API)

[![Run on Apify Store](https://img.shields.io/badge/Apify_Store-Run_Actor-00C853?style=for-the-badge&logo=apify)](https://apify.com/willowy_catamaran_fco/startup-ats-jobs-b2b-scraper)
[![MCP Compatible](https://img.shields.io/badge/MCP-AI_Agent_Ready-7C3AED?style=for-the-badge)](https://apify.com/willowy_catamaran_fco/startup-ats-jobs-b2b-scraper/api)
[![n8n & Clay Ready](https://img.shields.io/badge/Integrations-n8n_%7C_Clay_%7C_Make-FF6D5A?style=for-the-badge)](https://apify.com/willowy_catamaran_fco/startup-ats-jobs-b2b-scraper)

Scrape structured engineering and GTM job openings directly from funded tech startups' ATS boards, including department signals, required tech stack, and salary ranges.

---

## Why Growth Teams & AI Agents Use This Actor
- **Flat, Pre-Validated JSON Output:** Zero nested arrays - maps directly into **Clay.com columns**, **n8n HTTP Request nodes**, **Make.com**, **HubSpot**, and **Airtable**.
- **High-Concurrency Async Engine:** Powered by concurrent worker pools and TLS browser impersonation (`curl_cffi`) with low 256MB-512MB RAM footprint.
- **MCP & Autonomous Agent Ready:** Runs under `LIMITED_PERMISSIONS` with predictable Pay-Per-Event pricing so Claude, Cursor, LangChain, and CrewAI agents can call it autonomously.

---

## Quick Start: 1-Click API Call (n8n / Clay / cURL)

Use the synchronous endpoint below in **Clay (HTTP API enrichment)** or **n8n (HTTP Request node)** to run the extraction and receive the JSON array in a single request:

```bash
curl -X POST "https://api.apify.com/v2/acts/willowy_catamaran_fco~startup-ats-jobs-b2b-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
  "companyBoards": [
    "stripe",
    "cloudflare",
    "gitlab",
    "datadog"
  ],
  "keywordFilter": "Engineer",
  "maxItems": 50
}'
```

---

## Sample Input
```json
{
  "companyBoards": [
    "stripe",
    "cloudflare",
    "gitlab",
    "datadog"
  ],
  "keywordFilter": "Engineer",
  "maxItems": 50
}
```

## Real Output Sample
```json
{
  "companySlug": "stripe",
  "companyDomain": "stripe.com",
  "jobTitle": "AI Engineer",
  "departmentCsv": "1155 SA Transformation",
  "requiredTechCsv": "Python, Next.js, Node.js, AWS, GCP, LLM",
  "location": "Chicago"
}
```

---

## Connect to Claude Desktop / Cursor via Apify MCP
Add this Actor to your AI agent toolset using the official Apify MCP Server:
```json
{
  "mcpServers": {
    "apify-b2b-tools": {
      "command": "npx",
      "args": [
        "-y",
        "@apify/actors-mcp-server",
        "--actors",
        "willowy_catamaran_fco/startup-ats-jobs-b2b-scraper"
      ],
      "env": {
        "APIFY_TOKEN": "YOUR_APIFY_TOKEN"
      }
    }
  }
}
```

## Keywords & Integrations
`greenhouse-scraper, ats-jobs-api, hiring-signals, startup-jobs, b2b-sales-intelligence, n8n, apify-actor`
