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

### Source entries — desk research updated 2026-11-27

These entries reflect published descriptions and catalogue metadata inspected on 2026-11-27. They are not the same as validating every raw observation, downloading and testing every dataset, conducting user interviews or establishing permission for commercial reuse. Provider statements are identified as provider claims.

#### SRC-001 — National Bureau of Statistics (NBS), Selected Food Price Watch

- **Source:** [NBS Microdata Catalog — Selected Food Price Watch](https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials)
- **Source type:** Official national statistical source.
- **Published collection description:** NBS states that over 700 NBS staff collect prices across all 774 LGAs from 10,000 respondents and locations, with supervisory monitoring and random audit verification.
- **Published output description:** The catalogue says the weighted average of collected prices is reported for each state, with the national average calculated from the state averages. Collection across all LGAs must therefore not be mistaken for a publicly available individual record for every LGA or market.
- **Latest catalogue resource located:** Selected Food Price Watch May 2026, dated 2026-06-25. The catalogue lists a 5.05 MB ZIP containing a PDF report and an XLSX selected-food table. April 2026 (released 2026-06-01) is also listed.
- **Raw-file inspection:** The official May 2026 ZIP link was opened, but retrieval timed out. The XLSX workbook, actual sheet names, column fields and exact product/unit coverage have not been inspected. The official page confirms a ZIP preview containing `Selected_Food_Report_May 26.pdf` and `selected food table May 26.xlsx`.
- **Coverage and limits:** Potentially useful as an official monthly benchmark for selected foods and state/national comparisons. It does not establish daily market prices or comprehensive coverage of every agricultural product, product form, market level or LGA.
- **Rights/access:** Public download is linked in the catalogue. Licence and conditions for redistribution or commercial reuse still require checking.
- **Status:** **Partially supported** — publisher, monthly series description, collection methodology and May 2026 resource listing confirmed from catalogue metadata; underlying workbook not inspected.
- **Next action:** Obtain the May 2026 ZIP through an accessible route; inspect the methodology and XLSX sheets/columns; record products, units, price definitions, state detail and any geographic granularity beyond state averages.

#### SRC-002 — World Bank, Monthly Food Price Estimates by Product and Market (Nigeria)

- **Source:** [World Bank Microdata Library — Nigeria, Study 4503](https://microdata.worldbank.org/catalog/4503)
- **Source type:** Public analytical dataset of modeled monthly market/commodity price estimates.
- **Latest version surfaced in the current indexed catalogue:** Version date 2026-11-17; indexed coverage 2007-01-01 to 2026-11-01; 73 markets. The indexed data dictionary lists `NGA_RTFP_mkt_2007_2026-11-17.csv`, 17,686 cases and 137 variables.
- **Version discrepancy:** The detailed catalogue and data-dictionary pages that could be opened still show a cached version dated 2026-07-06, with 73 markets, coverage through 2026-07-01, and a 17,390-case/137-variable CSV. A separate opened Get Microdata page showed an August 2026 version. Therefore, the November 17 version is the latest indexed listing located, but the currently accessible detailed file pages remain stale. The November CSV itself has not been retrieved and verified.
- **Method and data nature:** The dataset is described as a real-time food-price estimate series combining direct price measurements with machine-learning estimates for missing market/product observations. It uses source information including WFP, FAO and selected national statistical offices. It is not a pure collection of independent, directly observed transactions. Modelled or spatially interpolated records must remain distinguishable from direct observations.
- **Current indexed data dictionary:** the November 17 file is listed as 17,686 cases and 137 variables. Its variable list includes `ISO3`, `country`, `adm1_name`, `adm2_name`, `mkt_name`, `lat`, `lon`, `geo_id`, `price_date`, `year`, `month`, `currency`, `components`, `start_dense_data`, `last_survey_point`, `data_coverage`, `data_coverage_recent`, `index_confidence_score`, `spatially_interpolated` and product-specific estimate fields. The market-name description warns that names may change or be shared; `geo_id` is provided to help distinguish market locations. These are indexed metadata; the November file itself has not been downloaded or row-inspected.
- **Geographic/product coverage:** The current indexed scope notes list selected states and markets, but Plateau's presence in the latest 73-market file has not been confirmed by inspecting actual rows. The indexed product list is selected rather than comprehensive; tomatoes were not listed in the surfaced variable list. Do not treat this as a complete agricultural commodity catalogue.
- **API/access:** The catalogue describes an API supporting selected fields, filters, JSON/CSV output and pagination up to 1,000 rows. The current indexed listing also identifies the November 17 CSV. A direct API request could not be inspected through the available browser route in this review.
- **Rights/access:** The World Bank terms page says the data may generally be copied, distributed, adapted and used in commercial or noncommercial products with required attribution and without implying World Bank endorsement. It also warns that third-party restricted materials may be included and must be checked separately. Apply the actual dataset terms and restricted-data list before reuse.
- **Status:** **Partially supported** — latest indexed release metadata, dataset API description, older detailed variable dictionary and general reuse terms located; current November file and actual current market rows remain unverified.
- **Next action:** Retrieve the November 17 CSV/API response through a working route; inspect actual market names, administrative areas, Plateau representation, products, date coverage and the `spatially_interpolated`/coverage fields. Do not equate a non-interpolated estimate with a verified transaction; trace its source. Save the exact data version and source attribution.

#### SRC-003 — FAO GIEWS Food Price Monitoring and Analysis (FPMA) Tool

- **Source:** [FAO FPMA overview](https://www.fao.org/giews/food-prices/en/), [About FPMA Tool](https://www.fao.org/giews/food-prices/price-tool/en/), and [FAO FPMA Tool](https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic)
- **Source type:** Official international food-price monitoring and analysis resource.
- **Published capability description:** FAO describes the FPMA Tool as containing over 2,000 domestic and international food-price series. It allows users to scan current and past prices, calculate basic statistics such as percentage changes, and compare markets, commodities and seasons. FAO says source information can be found for each series and that data used in FPMA analysis is available through the tool.
- **Documented API capability:** FAO's API documentation describes a `FpmaSerie` endpoint that can list series and filter by ISO3 country code (Nigeria: `NGA`). A separate `FpmaSerieDomestic` endpoint lists domestic wholesale/retail series. Each returned series has a UUID, which is used with `FpmaSeriePrice` to retrieve price data at an available daily, weekly or monthly periodicity. Series metadata includes country, market, commodity, source, price type, currency, measure unit and periodicity; price points include dates and original, real and USD-converted values where available.
- **Update and source context:** FAO describes the domestic price information as a resource for monitoring basic food prices, with series sourced from national institutions and international organisations. The global tool's data is not a direct FAO observation in every location; provenance must be examined per series.
- **Potential institutional integration:** FAO states that the FPMA Tool is available to countries and regional organisations, can be linked to existing national food-price collection systems and tailored to needs. An optional mobile data-collection component can collect primary price data, which can then be validated and sent to the analysis/dissemination platform. This is a national/regional capability description, not evidence that an individual developer can upload data or use an unrestricted public API.
- **Limits:** Global availability does not establish that Nigeria has a series for every commodity or market. Monthly averages and selected basic-food series are not equivalent to daily farmgate observations or individual verified transactions. The API documentation was accessible, but the live Nigeria series endpoint and Nigeria data grid could not be retrieved in this review; no actual Nigerian series UUID, market or commodity coverage has been confirmed.
- **Rights/access:** The tool is public; redistribution and reuse rights need checking for each selected series and the underlying source.
- **Status:** **Partially supported** — FAO's published tool capabilities, broad series count, source-transparency features and national/regional integration model confirmed; Nigeria-specific market series and raw downloads remain uninspected.
- **Next action:** Use the documented API route to request series filtered by `iso3_country_codes=NGA`; enumerate the returned Nigeria domestic series and capture UUID, market, commodity, source, price type, periodicity, currency, unit and last available date. Then retrieve selected price records. The API documentation describes price upload as restricted to authenticated users with the necessary permissions; do not assume a public series API grants data-upload rights. Examine whether an existing national price-data system or partnership route is relevant before considering custom collection software.

#### SRC-004 — Plateau Commodity Marketing Company Limited (PLACOM)

- **Source:** [PLACOM market prices](https://www.placommarkets.com/market-prices), [PLACOM institutional website](https://www.placommarkets.com/about), [PLACOM services](https://placommarkets.com/what-we-do.html), [PLACOM insights](https://www.placommarkets.com/insights), and [Plateau State Government statement](https://www.plateaustate.gov.ng/news/one/?id=677bdaf0756ad8d3db233c07).
- **Source type:** Plateau State commodity-marketing institution and potential local source/stakeholder.
- **Published price-board description:** The current indexed price-board page is titled “Live Commodity & Mineral Prices” and says it tracks indicative prices for Plateau State's leading agricultural, livestock and mineral commodities across major local markets. It offers sector filtering and commodity search. It expressly cautions that values are indicative and may vary by location and trader, and should be confirmed before transacting.
- **Institutional context:** PLACOM's public description presents it as a Plateau State commodity-marketing organisation. The Plateau State Government has publicly referred to the Plateau State Commodity Marketing Company and its role in commodity trading, warehousing and market information.
- **Provider capability claims:** PLACOM's published services describe market information and commodity intelligence. These are provider descriptions, not independent validation of the underlying data collection method or operational performance.
- **Limits:** The live price-board content could not be inspected beyond the indexed page description. The pages reviewed do not yet establish the exact named markets and products, grades/units, observation timestamps, sample coverage, update frequency, source provenance, verification procedure, machine-readable data/API or external reuse rights.
- **Potential role:** A highly relevant local institutional source and possible stakeholder/partner to investigate. No contact has been made, no data access has been granted and no partnership exists.
- **Status:** **Under review** — a current indicative local-price service is publicly advertised, but its observation records and methodology remain unverified.
- **Next action:** Inspect live commodity and market details; establish how each price is collected, which markets/products/units it covers, how often it is updated, how it is verified and what access/reuse arrangements apply. Prepare a specific inquiry only when a concrete information gap remains; do not send it without authorisation.

#### SRC-005 — Agromate Intelligence

- **Source:** [Agromate dataset downloads](https://www.agromate.ng/intelligence/data), [Agromate Plateau intelligence](https://www.agromate.ng/intelligence/state/plateau), and [Agromate intelligence overview](https://www.agromate.ng/intelligence)
- **Source type:** Independent commercial/technology platform and data aggregator with its own pilot estimates and analytical outputs.
- **Published dataset claims:** Agromate's download page advertises CSVs for local market prices from nine states, with FEWS NET information through August 2026 and WFP information through October 2026, and wholesale/retail units such as per 100 kg, 50 kg bag, kg and mudu. It separately lists food-security, world commodity-price and forecast datasets.
- **Additional platform overview claim:** Agromate's main intelligence overview says its current pilot has 21 state markets priced, describes one weekly price per state with a source attached, and refers to field-agent quotations and trades recorded on Agromate. It also advertises analysis such as state price benchmarks and production/market intelligence. These are platform claims; the page does not by itself establish that every listed price is an independently verified transaction or that the pilot coverage is complete. The download page and overview use different coverage descriptions (nine-state local market source data versus 21 state-market pilot prices), so the datasets and pilot estimates must be separated and reconciled.
- **Plateau-specific source caveat:** The Plateau page says FEWS NET and WFP do not survey a market in Plateau in the referenced series and therefore shows the nearest surveyed markets. It names Maigatari/Kara market in Jigawa and Dawanau market in Kano as examples, with stated distances of about 213 km and 236 km from Plateau respectively.
- **Separate Plateau estimate:** The page separately labels an “Agromate price board for Plateau (pilot estimates)”. It says those prices are converted from per-tonne pilot estimates to per-100-kg values, with percentage movements compared with the national average. These are not direct observations from a named Plateau market and must not be confused with the external FEWS NET/WFP surveyed market records.
- **Forecast claim:** The platform describes six-month forecasts for market series and references backtesting. The raw backtest values, forecast errors, coverage and calibration of any uncertainty intervals have not been inspected.
- **Limits:** CSV contents and row-level provenance, update operation, model outputs, forecast performance, rights to reuse or redistribute and API availability remain untested.
- **Potential role:** Useful existing product and dataset to evaluate before building similar price boards, comparisons or forecasts. It may also help identify where source coverage ends and local estimates begin.
- **Status:** **Partially supported** — source distinctions, data-download descriptions and pilot coverage claims located; downloadable CSV contents, the relationship between nine-state upstream price data and 21 state-market pilot prices, field-agent/trade evidence rules and model performance not independently tested.
- **Next action:** Obtain and inspect the CSVs and reconcile the coverage statements. For each record, trace whether it is an upstream FEWS NET/WFP value, a field-agent quotation, a platform-recorded trade, a derived state estimate or a forecast; preserve the stated source and evidence type. Examine forecast backtests and the method behind uncertainty intervals; assess licence, commercial access, API and integration options.

### Preliminary cross-source assessment — hypothesis, not a validated market gap

The five candidates offer different capabilities and leave different questions:

| Candidate | What its published material establishes or claims | What remains important for our pilot |
|---|---|---|
| NBS | Monthly selected-food price collection across all LGAs, but state and national weighted averages are the described public output. | Inspect the May 2026 XLSX and determine exactly what geographic and product detail is publicly available. |
| World Bank RTFP | 73-market selected-product estimates with a mix of direct and modelled data, an API and a versioned dataset. | The latest indexed file is newer than the detailed pages available in the browser; confirm current market rows and Plateau representation. |
| FAO FPMA | More than 2,000 domestic/international series; documented API can list country-specific series and retrieve price data by UUID. Upload is permissioned. | Enumerate Nigeria's actual series via API; consider national-system integration/partnership rather than assuming individual upload access. |
| PLACOM | Publicly advertises current indicative Plateau commodity and mineral prices across major local markets. | It may already address part of the apparent local gap; establish the actual data fields, observation sources and methodology. |
| Agromate | Publishes data downloads and distinguishes nearby FEWS NET/WFP surveyed markets from its own Plateau pilot estimates. | Inspect the raw CSVs and estimate methodology; do not label nearest-market values as Plateau observations. |

**Working hypothesis:** there may be value in connecting local Plateau market observations to transparent source provenance, observation dates, product definitions, units, evidence status and comparable market-level records.

The current research does **not** prove that Plateau lacks market-price information. PLACOM explicitly advertises local indicative prices. Agromate has its own Plateau pilot estimates. There may also be institutional, trader, cooperative or offline channels that are not publicly indexed. The stronger question is whether the information is sufficiently detailed, timely, accessible, comparable and trusted for a specific user's decision—and whether any unmet need remains after existing services are assessed.

No user problem has yet been independently validated. No data has been integrated. No source has been approved for commercial redistribution.

### Next verification sequence

1. Obtain and inspect the NBS May 2026 XLSX and methodology report.
2. Retrieve the World Bank 2026-11-17 CSV/API release and check actual market rows, Plateau coverage and `spatially_interpolated`/coverage fields.
3. Use the documented FAO FPMA API to enumerate Nigeria series, record each series UUID, market, commodity, price type, periodicity, unit, dates and source, then retrieve a small selected sample.
4. Inspect PLACOM price-board details and determine whether a specific data-methodology inquiry is warranted.
5. Inspect Agromate CSVs and forecast backtests; distinguish upstream observations from its own estimates.
6. Validate user problems and current workarounds separately from source coverage.
7. Only then define a bounded pilot sample and compare solution options.

### Research trail and references

- NBS catalogue and May 2026 file listing: https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials
- NBS study description/method: https://microdata.nigerianstat.gov.ng/index.php/catalog/162/study-description
- World Bank Nigeria RTFP catalogue: https://microdata.worldbank.org/catalog/4503
- World Bank indexed API/data dictionary: https://microdata.worldbank.org/catalog/4503/data-api
- World Bank terms of use: https://microdata.worldbank.org/catalog/4503/get-microdata
- FAO FPMA overview: https://www.fao.org/giews/food-prices/en/
- FAO FPMA tool description: https://www.fao.org/giews/food-prices/price-tool/en/
- FAO FPMA tool: https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic
- PLACOM price board: https://www.placommarkets.com/market-prices
- PLACOM services: https://placommarkets.com/what-we-do.html
- PLACOM insights: https://www.placommarkets.com/insights
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

**Current discovery state (2026-11-27):** five candidate sources/platforms have received updated desk assessment. NBS's May 2026 ZIP is listed but the retrieval timed out; the catalogue describes collection across 774 LGAs but state/national weighted-average public outputs. The World Bank's 2026-11-17 indexed file lists 73 markets, 17,686 cases and 137 variables, including market, administrative-area, date, coverage and spatial-interpolation fields; the actual latest CSV and Plateau market rows remain uninspected. FAO API documentation describes country-filtered series discovery and retrieval of price records by series UUID; Nigeria series have not yet been enumerated, and uploads require authorised access. PLACOM advertises local indicative Plateau prices, but its price records and methodology remain unverified. Agromate's download page describes local market source data for nine states, while its main overview says 21 state markets are priced in its pilot; it separately distinguishes nearby FEWS NET/WFP survey markets from Plateau pilot estimates. The raw CSVs and forecast backtests remain uninspected. The possible Plateau traceability/coverage opportunity remains a hypothesis. No raw data integration, complete rights review or user problem validation has been completed.
