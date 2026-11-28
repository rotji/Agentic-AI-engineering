# Web Data Acquisition and Scraping

**Status:** Project reference and engineering guidance  
**Implementation status:** No scraper, crawler or scraping platform has been selected or deployed  
**Applies to:** Agricultural intelligence pilot, other sector pilots and relevant data-acquisition work

## 1. Purpose

The project needs reliable ways to discover, retrieve and preserve information from public institutions, market platforms, company websites, data providers, research sources and other relevant online channels.

**Web scraping is one possible data-acquisition technique.** It is not the mission itself, and it should not be the default method for every source. The project should first identify what information is needed, where it is published, what access method is supported, whether its collection and use are permitted, and what level of evidence the resulting records can support.

The working principle is:

**Find the best permitted source interface first; scrape web pages only when a suitable structured or authorised route is unavailable and the need justifies it.**

## 2. Important terms

These activities are related, but are not identical.

- **Web crawling:** automatically discovers or visits web pages, often by following links and collecting URLs.
- **Web scraping:** extracts selected information from web pages or rendered page content and converts it into records or another usable form.
- **Browser automation:** controls a browser to navigate, click, scroll, enter permitted inputs or render dynamic pages. It may help acquire information from a page, but is not itself the same thing as scraping.
- **API integration:** retrieves or submits structured information through an interface intentionally exposed by a service.
- **Data ingestion:** the wider process of bringing information from one or more sources into a system, preserving its origin and preparing it for use.

A crawler may discover pages for a scraper to process. A scraper may retrieve a known page without broad crawling. Browser automation may be needed for a dynamically rendered page, but should not be used to evade access restrictions.

## 3. Where scraping fits in the project architecture

Scraping is primarily a **data-acquisition method implemented through a tool or connector**. It normally belongs most directly to Discipline 4, Tools and Environment Engineering. It also connects to:

| Discipline | Relevance |
|---|---|
| 1. Agent Architecture and Design | Decide whether a scraper is needed at all and whether acquisition should be a standalone service, a tool used by an agent or part of a larger pipeline. |
| 2. Reasoning and Planning | Select sources, define collection scope, plan retrieval order, schedule and stop conditions, and respond to unavailable sources. |
| 3. Context, Memory and Knowledge | Preserve source documents, extracted records, metadata, provenance, reference knowledge and information history. |
| 4. Tools and Environment Engineering | Build or integrate HTTP clients, APIs, crawlers, parsers, browser automation and other source connectors. |
| 5. Execution and Loop Engineering | Execute collection, handle timeouts, retries, partial results, rate limits, duplicate prevention and result verification. |
| 6. Orchestration and Multi-Agent Systems | Coordinate many source collectors and downstream processing stages where the scale justifies it. |
| 7. Security, Safety and Governance | Enforce access boundaries, privacy, data-use conditions, security controls and permitted collection scope. |
| 8. Agentic Governance and Self-Governing Systems | Govern who can add sources, change collection rules, approve sensitive use and respond to publisher requests or policy changes. |
| 9. Evaluation and Testing | Measure extraction accuracy, completeness, freshness, coverage, resilience and parser quality. |
| 10. Human-Agent Interaction | Provide review and correction paths for ambiguous or consequential extracted information. |
| 11. Observability and Reliability | Monitor source availability, page changes, extraction failures, error rates, freshness and collection history. |
| 12. Performance and Infrastructure | Manage request volume, concurrency, storage, browser sessions, bandwidth, latency and cost. |
| 13. Evolution and Continuous Improvement | Maintain source connectors and parsers as websites, formats and source policies change. |

Scraping is therefore not a new discipline, a Skill, an agent or an automation platform. It is one possible capability within a wider acquisition and ingestion process.

## 4. Choose the acquisition method before choosing a scraping tool

Use this order as a practical default, not as an inflexible rule:

1. **Official API:** use a documented API when it provides the needed data and the intended use is permitted.
2. **Official downloadable dataset:** use public CSV, XLSX, JSON, XML, PDF or bulk files where suitable.
3. **Official feed, export or partner integration:** consider RSS/Atom, data exports, webhooks, provider portals or an agreed data-sharing arrangement.
4. **Permitted HTML scraping:** extract from accessible pages when structured interfaces are unavailable or materially insufficient.
5. **Permitted browser-based acquisition:** consider browser automation when content is rendered dynamically and simpler retrieval methods cannot provide the required information.
6. **Manual collection or direct enquiry:** use a human process or ask the publisher/provider when digital extraction is unavailable, unclear or inappropriate.

Before recommending custom scraping, check whether an existing data provider, connector, open-source tool, commercial service or partner already provides the capability. The project principle remains capability before technology and assemble before building.

## 5. How it works in a practical acquisition pipeline

A scraper should be one component in a controlled pipeline, not the whole intelligence system.

A typical pipeline may be:

1. **Source discovery:** identify the publisher, page, dataset or service and why it matters.
2. **Source review:** assess authority, coverage, methodology, publication frequency, access terms, permitted use and limitations.
3. **Collection planning:** define the exact URLs or datasets, fields, geography, date range, collection frequency and request limits.
4. **Retrieval:** use the approved API, download, feed, scraping or browser method.
5. **Original preservation:** retain the source reference and, where permitted and proportionate, the retrieved file or page evidence.
6. **Extraction:** parse selected fields into a structured record without silently changing their meaning.
7. **Normalisation:** map units, names, dates and categories while preserving original values and transformation history.
8. **Quality assessment:** check missing fields, duplicates, unexpected changes, malformed values, freshness and extraction confidence.
9. **Evidence classification:** determine what the source actually supports; do not upgrade a claim simply because it was automatically collected.
10. **Review and use:** send ambiguous or consequential records for human review before relying on them.
11. **Monitoring:** detect source changes, blocked access, failed runs, stale data and extraction drift.

Collection, extraction, interpretation and verification are separate stages. A successful scrape proves that the system retrieved and extracted content; it does not prove that the content is factually correct.

## 6. Agricultural intelligence examples

Potential sources in our discovery register include NBS, World Bank data, FAO FPMA, PLACOM and Agromate Intelligence. They do not all require scraping:

- FAO's documented price-series API should be explored through the API before considering page scraping.
- NBS and World Bank downloadable data should be retrieved and inspected as files where available.
- A platform such as PLACOM may expose visible indicative price information on a web page. Scraping could be investigated only after checking the underlying source, collection method, access conditions, permitted reuse and whether automated retrieval is appropriate.
- A data platform may publish CSV files or API access that is preferable to scraping its dashboard.
- Public posts or notices on social platforms may generate market signals, but platform rules, privacy and the reliability of the claims need careful assessment. A visible post is not automatically a verified price quotation or transaction.

For example, extracting a displayed tomato price from a market page establishes that the page displayed that value at the recorded retrieval time. It does **not**, by itself, prove that a buyer paid that price, that the price was current at the market, or that the unit, grade and quantity are comparable with another record.

Keep the project's evidence categories distinct:
1. Verified transactions.
2. Verified quotations.
3. Unverified information.
4. Market signals.

The extraction method does not determine the evidence level. The underlying evidence does.

## 7. Provenance and minimum recordkeeping

For every automated collection run, preserve enough information to understand what was retrieved and how it became a record. Depending on the source and risk, useful metadata includes:

- Publisher or source name and the original URL or dataset identifier.
- Retrieval method: API, file download, feed, HTML scrape, browser-based collection or manual capture.
- Retrieval timestamp, including timezone where relevant.
- Source publication/update date and underlying observation/event date, where supplied.
- Dataset or page version, response metadata or file hash where practical.
- Extracted original value and the normalised value, rather than replacing the original silently.
- Parser/extractor version and the transformation applied.
- Collection scope, fields requested, coverage and known omissions.
- Terms, licence, permission and data-protection review status.
- Validation outcome, extraction confidence, errors and review status.

Do not confuse retrieval time with publication time or the time an underlying market observation occurred. Do not turn a missing field into zero, or an unsuccessful collection run into proof that a source has no data.

## 8. Responsible collection and access boundaries

Before collecting from a source, assess:

- Website terms of service, acceptable-use and data-use conditions.
- The site's published crawling instructions, including `robots.txt`.
- Copyright, database rights, licences and restrictions on redistribution or commercial use where relevant.
- Whether the material contains personal data and what lawful, fair and secure processing requirements apply.
- Whether the source requires an API key, agreement, subscription, attribution or written permission.
- Whether collection volume, frequency and methods could impose an unreasonable load.
- Whether the source has requested that collection stop or has changed its access conditions.

The Robots Exclusion Protocol is a standard for crawler instructions, but RFC 9309 explicitly states that these rules are **not a form of access authorisation**. A permissive `robots.txt` file does not itself grant permission, a licence or a right to reuse content. Conversely, a crawler should not treat the absence of a file as blanket approval. Review the applicable terms and permissions separately.

Do not bypass logins, paywalls, CAPTCHAs, technical access controls, IP blocks or other restrictions unless the publisher has explicitly authorised the relevant access method. Do not use proxy rotation or browser tricks to disguise prohibited access. Stop or seek permission when the permitted scope is unclear.

Use transparent identification where appropriate, conservative request rates, caching, incremental retrieval and backoff. Handle HTTP 429 and other error responses responsibly; do not keep retrying in a way that increases load or defeats the publisher's limits.

Because the project operates from Nigeria, personal-data collection and use must be assessed against applicable Nigerian data-protection requirements, including the Nigeria Data Protection Act 2023, as well as any other jurisdictional rules that apply to the source or affected people. Public visibility alone does not establish that unrestricted collection or reuse is appropriate. This document is engineering guidance, not legal advice; uncertain or high-risk collection should be reviewed with qualified counsel or the relevant data-protection professional.

References:
- [IETF RFC 9309 — Robots Exclusion Protocol](https://www.rfc-editor.org/rfc/rfc9309)
- [AWS Prescriptive Guidance — Best practices for ethical web crawlers](https://docs.aws.amazon.com/prescriptive-guidance/latest/web-crawling-system-esg-data/best-practices.html)
- [Nigeria Data Protection Act 2023 — Nigeria Data Protection Commission](https://ndpc.gov.ng/wp-content/uploads/2024/03/Nigeria_Data_Protection_Act_2023.pdf)

## 9. Reliability and evaluation

A scraper is software that can break. Pages can move, layouts can change, values can be reformatted, JavaScript can alter the rendered content, and publishers can change access conditions.

A collection system should therefore be evaluated for:
- **Extraction accuracy:** do extracted fields match the source page?
- **Completeness:** are expected records and required fields captured?
- **Coverage:** which pages, locations, products and periods are included or excluded?
- **Freshness:** how old is the source information, and how often is it updated?
- **Consistency:** are units, dates, currencies, language and category mappings handled correctly?
- **Resilience:** are layout changes, network failures, rate limits and empty responses detected?
- **Traceability:** can every record be traced back to its source and extraction run?
- **Cost:** what are the operational, maintenance, bandwidth, browser and provider costs?

Test a sample against the actual source page or source file. Alert on sudden zero-result runs, unexpected record-count changes and missing mandatory fields. Keep parser versions and representative test fixtures where retention is permitted. Use deduplication and safe retries so a repeated run does not silently create duplicate observations.

## 10. When scraping is not the right answer

Do not scrape merely because a page is visible. Prefer another route when:

- An official API or downloadable dataset provides the same or better information.
- The publisher prohibits the intended automated access or reuse.
- The data is behind authentication or a paywall without permission for automated collection.
- The page is unstable and produces unreliable or untestable extraction.
- The data contains personal or sensitive information that has not been appropriately assessed.
- A partnership, licence, data purchase or direct request is more reliable and proportionate.
- The cost of maintaining the scraper exceeds the value of the information.

A smaller set of reliable, permitted sources can be more valuable than a large volume of poorly understood scraped content.

## 11. Project working rule

Web scraping is one instrument in the project's broader information-acquisition capability. Use the most reliable, permitted and economical source interface; collect only what the defined problem requires; preserve provenance; test extraction quality; and keep extracted claims separate from verified facts.

**Scrape to acquire information—not to manufacture evidence.**
