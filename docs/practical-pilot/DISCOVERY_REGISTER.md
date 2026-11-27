# Agricultural Pilot Discovery Register

**Version:** 0.1  
**Status:** Template — no candidate source or user problem has yet been validated  
**Related charter:** [Agricultural Pilot Charter](AGRICULTURAL_PILOT_CHARTER.md)

## 1. Purpose

Use this register to collect and assess evidence about:
- Real problems experienced by potential users.
- Existing information sources and their coverage.
- Existing tools, platforms, services and human processes.
- Whether an initial end-to-end pilot can be performed with available, permitted evidence.

The register is a discovery record, not a list of endorsements or confirmed facts. A source being listed does not mean that its information is accurate, complete, current, representative or legally reusable.

## 2. Status vocabulary

Use a consistent status for every entry:

- **Not assessed:** recorded for future investigation; no substantive review yet.
- **Under review:** relevant details are being checked.
- **Partially supported:** some claims are supported, but important gaps remain.
- **Verified for stated scope:** the stated claim has been checked against adequate evidence for the specific scope described. This does not imply universal reliability.
- **Not suitable:** does not meet the current requirement, with reasons recorded.
- **Blocked:** assessment cannot proceed because access, permission, evidence or another dependency is unavailable.
- **Superseded:** an earlier record or source has been replaced; preserve the reason and date.

Do not use a single status to hide different kinds of uncertainty. Record source reliability, evidence quality, freshness, representativeness, access rights and suitability separately.

## 3. User-problem discovery register

Record the problem and workflow, not unnecessary personal details about the person who describes it. Obtain permission before recording identifiable quotations or sensitive information.

| Field | What to record |
|---|---|
| Problem ID | Stable identifier such as PROB-001 |
| Date recorded | Date of the observation or discussion |
| Geography | Location at the precision actually supported |
| User category | Producer, trader, processor, buyer, analyst, institution, etc. |
| Task or decision | What the person is trying to accomplish |
| Current process | How the task is performed today |
| Reported difficulty | The specific friction, delay, uncertainty or cost |
| Consequence | What happens when the difficulty occurs |
| Existing workaround | Tools, services, contacts or manual processes already used |
| Evidence basis | Direct observation, permissioned discussion, document, public statement, etc. |
| Evidence note | Concise summary; distinguish direct evidence from interpretation |
| Frequency and timing | How often and when the issue occurs, if known |
| Importance | Why the problem matters to the affected person |
| Existing alternatives | Products, services or processes already addressing it |
| Permission and privacy | Whether recording or follow-up is authorised and appropriate |
| Limitations | What is not known or cannot yet be concluded |
| Status | Use the status vocabulary above |
| Next action | Specific verification or follow-up needed |

### Problem entries

_No user problem has yet been validated. Add entries as evidence is gathered._

| Problem ID | Date | User category | Geography | Task or decision | Evidence basis | Status | Next action |
|---|---|---|---|---|---|---|---|
| — | — | — | — | — | — | Not assessed | Begin discovery |

## 4. Candidate information-source register

| Field | What to record |
|---|---|
| Source ID | Stable identifier such as SRC-001 |
| Source/platform | Name of the institution, platform, publication, market or source |
| Source type | Official, commercial, community, social media, research, direct observation, etc. |
| Original URL/reference | Exact source address or recoverable reference |
| Information type | Prices, transactions, production, producer details, logistics, policy, weather, etc. |
| Product coverage | Commodity, processed form or by-product actually covered |
| Geographic coverage | Actual documented coverage, not presumed reach |
| Market level | Farmgate, wholesale, retail or not applicable |
| Observation granularity | Product form, grade, unit, date, location and other available detail |
| Access method | Public page, downloadable dataset, API, permissioned access, manual contact, etc. |
| Access conditions | Terms, login, rate limits, permissions and restrictions |
| Data rights | Licence, reuse conditions, attribution and redistribution restrictions |
| Date checked | When this source was last inspected |
| Freshness | Publication/update cadence or observed data age, if established |
| Provenance | Original publisher and any known upstream source |
| Independence | Whether this is an independent observation or reproduces another source |
| Evidence examples | Exact examples inspected and what they support |
| Reliability limitations | Known gaps, methods, incentives, inconsistencies or uncertainty |
| Privacy and safety | Personal-data, confidentiality or contact considerations |
| Cost and dependencies | Free, paid, conditional, technical or operational requirements |
| Status | Use the status vocabulary above |
| Next action | What must be checked next |

### Source entries — initial desk research

**Assessment date:** 2026-11-27. These are preliminary desk assessments of published metadata and website descriptions. Raw files, individual observations, complete licences, operational methods and practical access have not all been tested. "Partially supported" or "Under review" must not be read as approval for production use.

#### SRC-001 — National Bureau of Statistics (NBS), Selected Food Price Watch

- **Source:** [NBS Microdata Catalog — Selected Food Price Watch](https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials)
- **Source type:** Official national statistical source.
- **Information:** Monthly selected food-price reporting for Nigeria.
- **Publisher-described collection method:** NBS states that over 700 staff collect prices across all 774 LGAs, from 10,000 respondents and locations, with internal/external supervisory monitoring and random audit verification.
- **Published aggregation:** The catalogue description says average prices are reported for each state and the national average. This should not be confused with a public, transaction-level feed for each market or each LGA.
- **Latest catalogue item located in this review:** Selected Food Price Watch May 2026, dated 2026-06-25, with a ZIP containing a report PDF and an XLSX table. The catalogue currently surfaces April, March, February and January 2026 as earlier releases.
- **Coverage and limits:** Strong candidate for official national/state benchmark context and selected food categories. It is monthly, selected-food coverage and does not by itself demonstrate live prices for every commodity, product form, market or LGA. Exact columns and granularity in the May 2026 XLSX still need inspection.
- **Rights/access:** Files are publicly linked in the NBS catalogue; exact licence and permitted redistribution conditions need confirmation before republishing.
- **Status:** **Partially supported** — publisher, monthly collection description and report availability confirmed from catalogue metadata; underlying table schema and source-row granularity not yet tested.
- **Next action:** Inspect the May 2026 XLSX and PDF methodology; record exactly which commodities, units, locations and price definitions are published; check whether any detailed LGA or market-level fields are available.

#### SRC-002 — World Bank, Monthly Food Price Estimates by Product and Market (Nigeria)

- **Source:** [World Bank Microdata Library — Nigeria, Study 4503](https://microdata.worldbank.org/catalog/4503)
- **Source type:** Public analytical dataset; compiled and model-estimated market-price series.
- **Information:** Market-level food-price estimates for Nigeria. The current search-indexed catalogue record describes 73 markets, a period from 2007-01-01 to 2026-11-01, and version date 2026-11-17. The same record describes a combination of direct price measurements and machine-learning estimation of missing observations, using source information from WFP, FAO and selected national statistical offices.
- **Important validation issue:** Opening the catalogue page during this review returned a cached record showing an older version (2026-08-03, coverage through 2026-08-01). The search-indexed version and opened page therefore disagree. The version, latest observation period and current coverage must be rechecked through the dataset's API/download before being used.
- **Analytical limitation:** This is not a pure direct-observation dataset. It mixes direct information and model-estimated missing prices; estimates and observations must be distinguishable before use. The catalogue's disclaimer says the series is provided as available and may be revised.
- **Geographic/product coverage:** The current indexed page describes 73 markets and selected food items. The precise current market list, product definitions and Plateau State coverage have not yet been verified from the raw metadata/data. The older opened version did not list Plateau among its stated geographic areas, but that cannot be assumed to describe the newer indexed version.
- **Rights/access:** Catalogue describes the estimates as public/open data and provides access and citation information; exact data licence and API terms should be checked from the selected version.
- **Status:** **Under review** — promising historical and subnational benchmark, but version discrepancy, market coverage, source lineage and observed-versus-imputed flags need direct verification.
- **Next action:** Retrieve the current data/API metadata; confirm the actual release version, market list, Plateau presence, observed/estimated fields, product coverage and relevant terms.

#### SRC-003 — FAO GIEWS Food Price Monitoring and Analysis (FPMA) Tool

- **Source:** [FAO FPMA Tool](https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic) and [FAO FPMA information](https://www.fao.org/giews/food-prices/en/)
- **Source type:** Official international food-price monitoring and analysis resource.
- **Information:** FAO describes the domestic-price dataset as average monthly retail and wholesale prices for basic food commodities. The tool allows users to browse series, compare markets/commodities/seasons and download data, charts and basic statistics. The source for an individual series is displayed in its information panel.
- **Coverage:** FAO's GIEWS information describes a multi-country database. A September 2026 FAO Nigeria country brief references the FPMA tool among the data/tools used in preparing its analysis. This does not yet confirm which Nigerian market series and commodities are available in the current tool.
- **Limits:** Monthly averages and selected basic-food series are not equivalent to daily farmgate observations or verified individual transactions. Country-specific source methods and market coverage must be checked per series.
- **Rights/access:** Public tool and downloads are described by FAO; terms for reuse or redistribution of downloaded series still need confirmation.
- **Status:** **Under review** — useful candidate for international comparison and monthly market context; Nigeria series and downloadable data fields not yet inspected.
- **Next action:** Filter the tool for Nigeria; capture available commodity, market, retail/wholesale, unit, last observation, original data source and any methodological notes.

#### SRC-004 — Plateau Commodity Marketing Company Limited (PLACOM)

- **Source:** [PLACOM market prices page](https://www.placommarkets.com/market-prices), [PLACOM about page](https://www.placommarkets.com/about), and [Plateau State Government statement](https://www.plateaustate.gov.ng/news/one/?id=677bdaf0756ad8d3db233c07).
- **Source type:** Plateau State commodity-marketing institution and potential local data/stakeholder source.
- **Institutional context:** PLACOM's website describes it as a state-owned special-purpose vehicle established in 2024. A Plateau State Government statement also says the administration established the Plateau State Commodity Marketing Company to address commodity trading, warehousing and market information systems.
- **Market-price page claim:** The PLACOM page advertises indicative reference prices for Plateau agricultural, livestock and mineral commodities across local markets, and cautions that prices may vary by location and trader and should be confirmed before transacting.
- **Limits:** The pages reviewed do not yet establish the underlying price collection method, exact named-market coverage, commodities/grades/units, update cadence, source provenance, whether values are quotations or transactions, or whether machine-readable data/API access exists. A page describing indicative figures is not itself verification of those figures.
- **Potential role:** Could be an important local source, institutional stakeholder or partner to investigate; no relationship, agreement or data access has been established.
- **Status:** **Under review** — local relevance is clear from the public description; data methodology and actual operational access remain unverified.
- **Next action:** Inspect the live price board and any available data download; establish which markets and products are covered, how observations are collected, how often they are updated, who verifies them, and what access/reuse arrangements apply. Do not initiate contact until a specific inquiry and authority to send it are agreed.

#### SRC-005 — Agromate Intelligence

- **Source:** [Agromate Intelligence data downloads](https://www.agromate.ng/intelligence/data), [Plateau state intelligence page](https://www.agromate.ng/intelligence/state/plateau), and [Agromate methodology/source overview](https://www.agromate.ng/intelligence).
- **Source type:** Independent commercial/technology platform and data aggregator with its own pilot estimates and analytical models.
- **Published data claims:** Its data page advertises CSV downloads, local market price data from nine states, FEWS NET data through August 2026 and WFP data through October 2026, plus separately identified food-security, forecast and world commodity-price datasets.
- **Plateau-specific statement:** The Plateau page says FEWS NET and WFP do not survey a market in Plateau and that it therefore displays the nearest surveyed markets for those sources. It separately labels an Agromate Plateau price board as pilot estimates, including conversions from per-tonne estimates. This is an important distinction: a nearby external market is not a Plateau market observation, and an Agromate pilot estimate is not an official market quotation.
- **Limits:** Data lineage, CSV contents, update operation, forecast method/backtest, rights to reuse or redistribute and API availability must be tested. Its own estimates should remain separate from upstream observations.
- **Potential role:** Useful existing capability/platform to compare against the pilot requirements; it may help identify source coverage gaps and avoid rebuilding features already available.
- **Status:** **Under review** — substantial public description and source attributions located, but downloadable files, model methods and reuse/integration terms not yet tested.
- **Next action:** Download and inspect the CSV files; trace individual records to FEWS NET/WFP or model outputs; inspect the forecast method and backtest evidence; assess data licence, commercial access, API and provider dependence.

### Preliminary cross-source observation — hypothesis, not a confirmed market gap

The initial desk review suggests a possible coverage and traceability gap for Plateau local market prices:

- NBS describes broad LGA-level price collection but its catalogue explains state and national average reporting.
- The current World Bank catalogue search listing reports market-level estimates, but direct page retrieval returned an older cached version and the current Plateau market coverage remains unconfirmed.
- Agromate explicitly says FEWS NET and WFP do not survey a market in Plateau in the source series it uses; for its Plateau page it shows nearest surveyed markets and separately labels its own Plateau price board as pilot estimates.
- PLACOM advertises local indicative prices, but the reviewed page descriptions do not disclose enough methodology to assess the observations.

**Abductive hypothesis to investigate:** a useful opportunity may exist to connect locally grounded Plateau market observations with clear source provenance, dates, product definitions, evidence status and comparable units.

This is not yet proof that no such source or service exists, nor proof that users experience a problem or would pay for a solution. Competing explanations remain possible: the information may exist through local channels that are not publicly indexed; PLACOM or another institution may already collect and verify it; or the apparent gap may not be important to users. The next checks must distinguish these explanations.

### Research trail and references

- NBS catalogue and May 2026 resource listing: https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials
- World Bank Nigeria price estimates catalogue: https://microdata.worldbank.org/catalog/4503
- FAO FPMA tool: https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic
- FAO Nigeria GIEWS country brief (reference date 2026-09-16): https://cb.apps.fao.org/country.jsp?code=NGA
- PLACOM market prices: https://www.placommarkets.com/market-prices
- PLACOM institutional description: https://www.placommarkets.com/about
- Plateau State Government statement: https://www.plateaustate.gov.ng/news/one/?id=677bdaf0756ad8d3db233c07
- Agromate dataset downloads: https://www.agromate.ng/intelligence/data
- Agromate Plateau page: https://www.agromate.ng/intelligence/state/plateau


## 5. Candidate solution and capability register

Assess existing solutions only against a real requirement discovered through the problem and source registers.

| Field | What to record |
|---|---|
| Solution ID | Stable identifier such as SOL-001 |
| Provider/project | Product, service, open-source project or organisation |
| Capability required | Specific capability being assessed |
| Evidence of capability | Documentation, test, demonstration or observed behaviour |
| Fit to requirement | What is satisfied, partially satisfied or missing |
| Accessibility | Individual access, geographic restrictions, eligibility and onboarding |
| Cost | Pricing, limits, hidden dependencies and operating cost |
| Licence and data rights | Use, modification, redistribution and data conditions |
| Security and privacy | Relevant controls and limitations |
| Interoperability | APIs, exports, formats and integration constraints |
| Reliability and support | Evidence, service limits, maintenance and support |
| Exit and provider dependence | Portability, alternatives and lock-in risk |
| Assessment date | When the solution was checked |
| Status | Use the status vocabulary above |
| Decision | Reuse, integrate, test further, reject or defer |
| Reason and next action | Evidence supporting the decision and follow-up |

## 6. Evidence and test log

For each practical test, record:

- Test ID and date.
- Question or requirement being tested.
- Input sample and how it was selected.
- Source references and permissions.
- Procedure and any transformations.
- Expected result or acceptance condition.
- Actual result.
- Errors, exceptions and missing information.
- Reviewer and review date.
- Conclusion limited to the test scope.
- Follow-up or decision.

Do not invent sample sizes, numeric thresholds or success rates. Define them after understanding the use case, available evidence and consequences of error.

## 7. Working rules

1. Preserve original source values and references.
2. Record observation time separately from collection time.
3. Never convert a quotation into a transaction claim.
4. Do not treat repeated copies of one report as independent corroboration.
5. Keep products, forms, grades, units and market levels distinguishable.
6. Record geographic precision only at the level supported by the evidence.
7. Keep evidence status separate from source reliability and sample representativeness.
8. Record both supporting and contradictory evidence.
9. Respect source access conditions, privacy, data rights and permissions.
10. Do not contact people or organisations, create accounts, incur costs or make commitments without an authorised and appropriate process.
11. Record why a source or solution is rejected or deferred; do not silently discard previous findings.
12. Update the charter when findings materially change the problem, scope or acceptance conditions.

## 8. First actions

1. Identify candidate user groups and the decisions they need to make.
2. Document a small number of concrete current workflows and difficulties, without assuming the provisional problem hypothesis is correct.
3. Identify candidate public or otherwise authorised information sources.
4. Inspect sample records and assess what each source actually establishes.
5. Record access conditions, freshness, data rights and known limitations.
6. Compare available sources and existing services against the pilot requirements.
7. Recommend a bounded test scope only when the evidence supports it.

**Current discovery state (2026-11-27):** five candidate sources/platforms have received initial desk assessment (NBS, World Bank RTFP, FAO FPMA, PLACOM and Agromate). NBS source metadata and reported collection method are partially supported; the other candidates remain under review. No raw data pipeline, complete licence review, source integration or user problem has been validated. The initial Plateau coverage-gap hypothesis remains provisional.
