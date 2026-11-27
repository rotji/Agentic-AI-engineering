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

These entries reflect published descriptions and catalogue metadata inspected on 2026-11-27. They are not the same as validating individual observations, downloading and testing every raw dataset, conducting interviews or establishing data-use rights. Provider statements are identified as provider claims.

#### SRC-001 — National Bureau of Statistics (NBS), Selected Food Price Watch

- **Source:** [NBS Microdata Catalog — Selected Food Price Watch](https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials)
- **Source type:** Official national statistical source.
- **Published collection description:** NBS states that over 700 NBS staff collect prices across all 774 LGAs from 10,000 respondents and locations, with supervisory monitoring and random audit verification.
- **Published output description:** The catalogue says averages of the collected prices are reported for each state and the national average. Therefore, collection across all LGAs should not be confused with a public record of each individual market or each LGA observation.
- **Latest catalogue resource located in this review:** Selected Food Price Watch May 2026, dated 2026-06-25. The catalogue preview identifies a report PDF and an XLSX file inside a ZIP. The same page surfaces April, March, February and January 2026 releases as earlier items.
- **Coverage and limits:** Useful official benchmark for selected food items and state/national price comparisons. It is monthly and selected-food focused. Its published description does not establish that every commodity, product form, grade or market level is represented.
- **Raw-file inspection:** The catalogue page was inspected, but an attempt to retrieve the May 2026 ZIP in this session failed. The XLSX column names, sheet structure, exact product coverage and detailed price definitions therefore remain uninspected.
- **Rights/access:** Public download is linked in the catalogue. The licence and conditions for redistribution or commercial reuse still need to be checked.
- **Status:** **Partially supported** — NBS publisher identity, collection description, state/national aggregation description and May 2026 file listing confirmed from catalogue metadata; underlying workbook not inspected.
- **Next action:** Obtain the May 2026 ZIP through an accessible route; inspect the report methodology and XLSX sheets/columns; record product names, units, price definitions, state detail and any geographic granularity beyond state averages.

#### SRC-002 — World Bank, Monthly Food Price Estimates by Product and Market (Nigeria)

- **Source:** [World Bank Microdata Library — Nigeria, Study 4503](https://microdata.worldbank.org/catalog/4503)
- **Source type:** Public analytical dataset of modeled monthly market/commodity price estimates.
- **Latest version surfaced by the current indexed catalogue:** Version dated 2026-11-17; listed coverage 2007-01-01 to 2026-11-01 and 73 Nigerian markets. The indexed data dictionary lists the current file as `NGA_RTFP_mkt_2007_2026-11-17.csv`, with 17,686 cases and 137 variables.
- **Important version caveat:** Directly opening the detailed catalogue and API pages in this review returned older cached metadata (version 2026-08-03 or 2026-07-06). The newest indexed result and the readable cached page therefore differ. The 2026-11-17 metadata is the latest listing located, but the raw current file has not yet been retrieved and checked.
- **Method:** The catalogue describes Real Time Food Prices as a weekly updated dataset combining direct price measurements with machine-learning estimates for missing data. It uses WFP, FAO and selected national statistical office information, may revise observations, adjusts some outliers and generates estimates for missing market/product entries. It is not a pure set of independently observed transactions.
- **Geographic coverage:** The current indexed scope notes list selected sub-national areas including Abia, Borno, Yobe, Katsina, Kano, Kaduna, Gombe, Adamawa, Jigawa, Kebbi, Oyo, Sokoto, Zamfara and Lagos, along with aggregate categories. Plateau is not listed in those published geographic coverage notes. The exact 73-market list in the newest raw file still needs confirmation.
- **Product coverage:** The indexed scope lists selected foods such as beans, eggs, fish, gari, groundnuts, maize, maize flour, beef, goat meat, milk, millet, onions, rice, sorghum and yam. It does not list tomatoes in that scope, so it is not a complete agricultural commodity source.
- **Data structure/API:** The catalogue data dictionary describes market-level rows with fields for administrative areas, market name, coordinates, date, currency, data coverage and other series details. The Microdata Library describes an API with field selection, filters and pagination (up to 1,000 rows per page). Exact current-version fields and observed-versus-estimated flags require checking in the raw file.
- **Rights/access:** The catalogue describes the estimates as open data and specifies attribution. It also warns that some underlying third-party materials may have separate restrictions; check the restricted-data list and the applicable dataset terms before redistribution.
- **Status:** **Partially supported** — latest indexed release metadata, market count, methodology, product scope, selected geographic coverage and API description located; the raw November 17 file and actual market rows have not been validated.
- **Next action:** Retrieve the 2026-11-17 CSV/API data and inspect its actual market names, admin areas, Plateau presence, product variables and observed/model-estimated indicators. Preserve the dataset version and attribution.

#### SRC-003 — FAO GIEWS Food Price Monitoring and Analysis (FPMA) Tool

- **Source:** [FAO FPMA Tool](https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic), [FAO FPMA overview](https://www.fao.org/giews/food-prices/en/), and [About the FPMA Tool](https://www.fao.org/giews/food-prices/price-tool/en/)
- **Source type:** Official international food-price monitoring and analysis resource.
- **Published dataset description:** FAO describes its domestic dataset as average monthly retail and wholesale prices for basic food commodities, updated monthly with latest available data. It says the series are drawn predominantly from primary country sources and sometimes secondary sources. The tool's information panel identifies the source for a selected series.
- **Broader coverage:** FAO describes the tool as containing recent consumer food-price information for almost 100 countries and more than 80 international benchmark commodity price series.
- **Potential platform capability:** FAO says the FPMA Tool is available to countries and regional organisations and can be linked to existing national price-data systems. An optional mobile data collection component can collect primary prices, which can then be validated and pushed into the analysis/dissemination platform. This does not establish that an individual developer can use the tool as a public API or upload data independently.
- **Limits:** Monthly average retail/wholesale series are not daily farmgate records or individual verified transactions. Country, commodity and market coverage must be checked series by series. The interactive tool did not render its data grid in this review, so Nigeria series, exact markets, latest observation dates and downloads have not yet been checked.
- **Rights/access:** The global tool is public, but the reuse rights for a particular downloaded series and its underlying source need to be checked.
- **Status:** **Partially supported** — official description, monthly frequency, broad country coverage, source transparency at series level and national/regional tool capability confirmed from FAO's published description; Nigeria-specific series remain uninspected.
- **Next action:** Access the interactive data grid through a working browser; filter for Nigeria; record actual commodities, markets, units, retail/wholesale definitions, last observation date and original source. Check reuse conditions for each series.

#### SRC-004 — Plateau Commodity Marketing Company Limited (PLACOM)

- **Source:** [PLACOM market prices](https://www.placommarkets.com/market-prices), [PLACOM institutional website](https://www.placommarkets.com/about), [PLACOM what-we-do](https://placommarkets.com/what-we-do.html), [PLACOM insights](https://www.placommarkets.com/insights), and [Plateau State Government statement](https://www.plateaustate.gov.ng/news/one/?id=677bdaf0756ad8d3db233c07).
- **Source type:** Plateau State commodity-marketing institution and potential local source/stakeholder.
- **Institutional context:** PLACOM's public description presents it as a Plateau State commodity-marketing organisation. The Plateau State Government has also publicly referred to the Plateau State Commodity Marketing Company and its role in commodity trading, warehousing and market information.
- **Market-price page claim:** PLACOM labels its price page “Live Commodity & Mineral Prices” and says it tracks indicative prices for leading Plateau agricultural, livestock and mineral commodities across major local markets. It explicitly warns that values are indicative and may vary by location and trader, and should be confirmed before transacting.
- **Service claims:** PLACOM's “what we do” page describes market information services, real-time commodity market intelligence, price discovery tools and data analytics. These are provider claims about its services; they are not independent validation of its data collection, coverage or operational performance.
- **Limits:** The material reviewed does not disclose enough to establish a repeatable price-collection method, the exact named markets and products, grades/units, sample coverage, observation timestamps, update frequency, source provenance, verification procedure, downloadable data/API, or rights for external reuse.
- **Potential role:** Potentially the most directly relevant local institutional source and a possible stakeholder or partner to investigate. No contact has been made, no data access has been granted and no partnership exists.
- **Status:** **Under review** — relevant local service and indicative price-board claims located; data methodology, current board contents, coverage and access terms remain unverified.
- **Next action:** Inspect the live board and any detailed price pages or downloadable material; document visible commodity/market/unit/date fields; establish how observations are collected and verified, update frequency, data access and reuse rights. Prepare a focused inquiry only after these checks; do not send it without separate authorisation.

#### SRC-005 — Agromate Intelligence

- **Source:** [Agromate dataset downloads](https://www.agromate.ng/intelligence/data), [Agromate Plateau intelligence](https://www.agromate.ng/intelligence/state/plateau), and [Agromate intelligence overview](https://www.agromate.ng/intelligence).
- **Source type:** Independent commercial/technology platform and data aggregator with its own pilot estimates and analytical outputs.
- **Published dataset claims:** Agromate advertises downloadable CSVs. Its current data page describes local market prices in nine states, using FEWS NET data through August 2026 and WFP data through October 2026. It also lists food-security data, world commodity prices and six-month price forecasts for 265 market series. The forecast description says it provides 80% ranges, seasonal peak/low months and backtest errors.
- **Method description:** Agromate describes its price-forecast method as moving the last price along its seasonal pattern and backtesting against a no-change forecast. This is a publisher description, not an independently verified forecast-performance result. The actual backtest values, forecast errors and calibration of the 80% ranges need inspection.
- **Plateau-specific statement:** The Plateau page says FEWS NET and WFP do not survey a market in Plateau and therefore displays the nearest surveyed markets. It names markets in Jigawa and Kano as examples. It separately labels an Agromate Plateau price board as pilot estimates, converted from per-tonne pilot prices to per-100-kg figures, with percentage movements compared with the national average.
- **Important distinction:** A nearby surveyed market is not a Plateau market observation. A converted pilot estimate is not a directly observed Plateau transaction or quotation. These categories must remain separate in any comparison.
- **Limits:** CSV content and row-level lineage, update operation, source licence, commercial reuse, API availability and forecast method/backtest have not yet been independently inspected.
- **Potential role:** Useful existing platform and dataset to assess before building any similar price board, comparison or forecast capability.
- **Status:** **Partially supported** — published dataset coverage claims, upstream source descriptions, forecast method description and Plateau page caveat located; raw CSV and forecast performance not tested.
- **Next action:** Obtain the downloadable CSVs; inspect their fields, source IDs, dates, units and market rows; verify whether records are direct upstream observations or derived outputs; inspect backtest values and forecast errors; assess data reuse terms and integration options.

### Preliminary cross-source assessment — a hypothesis, not a validated market gap

The five candidates suggest different capabilities and different limitations:

| Candidate | What it appears to offer | What remains important for our pilot |
|---|---|---|
| NBS | Official monthly selected-food prices and state/national average reporting, with field collection across LGAs. | Obtain and inspect the May 2026 workbook; determine exact product, price and location detail. |
| World Bank RTFP | Modeled monthly prices for selected products and 73 markets, combining source data and model estimates. | Verify the current version's actual market rows; Plateau is absent from indexed geographic notes; not a complete commodity list. |
| FAO FPMA | Monthly average retail/wholesale series with source information shown for each series; potential national data-collection platform. | Determine which Nigeria series and markets are present and whether a national-tool collaboration is relevant. |
| PLACOM | Plateau-focused indicative commodity and mineral prices across major local markets, according to its website. | Verify the underlying observations, named markets, dates, methodology, access and reuse conditions. |
| Agromate | Downloadable source-attributed datasets and analytics; its Plateau page distinguishes nearest external surveyed markets from its own pilot estimates. | Test the CSV and forecast details; do not mistake nearest markets or pilot estimates for local observations. |

**Working abductive hypothesis:** there may be value in connecting local Plateau market observations to transparent source provenance, dates, product definitions, units, evidence status and comparable market-level records.

The current research does **not** prove that Plateau has no market-price information. PLACOM explicitly advertises local indicative prices, and there may be institutional, trader, cooperative or offline channels that are not publicly indexed. The stronger question is whether the information is sufficiently detailed, timely, accessible, comparable and trusted for a specific user's decision—and whether any unmet need remains after existing services are assessed.

No user problem has yet been independently validated. No data has been integrated. No source has been approved for commercial redistribution.

### Next verification sequence

1. Inspect the NBS May 2026 XLSX and methodology report when the ZIP can be retrieved.
2. Retrieve the World Bank 2026-11-17 CSV/API version and check actual market rows, Plateau coverage and modeled/observed fields.
3. Identify Nigeria series in the FAO FPMA data grid and record their markets, units, dates and source institutions.
4. Verify the actual PLACOM price board details and collection method; decide whether a focused institutional inquiry is warranted.
5. Inspect Agromate CSVs and forecast backtests; separate upstream observations from its own estimates.
6. Validate user problems and current workarounds separately from source coverage.
7. Only then define a bounded pilot sample and compare solution options.

### Research trail and references

- NBS catalogue and May 2026 file listing: https://microdata.nigerianstat.gov.ng/index.php/catalog/162/related-materials
- World Bank Nigeria RTFP catalogue: https://microdata.worldbank.org/catalog/4503
- World Bank data API page: https://microdata.worldbank.org/index.php/catalog/4503/data-api
- FAO FPMA overview: https://www.fao.org/giews/food-prices/en/
- FAO FPMA tool: https://fpma.fao.org/giews/fpmat4/#/dashboard/tool/domestic
- FAO FPMA national tool capability: https://www.fao.org/giews/food-prices/price-tool/en/
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

**Current discovery state (2026-11-27):** five candidate sources/platforms have received further desk assessment. NBS collection and aggregation metadata are partially supported, but its workbook could not be retrieved for inspection in this session. The latest indexed World Bank version is 2026-11-17, while detailed pages still show older cached versions; its published selected geographic coverage does not list Plateau. FAO's monthly series and source-transparency capability are described, but Nigeria series remain uninspected. PLACOM advertises local indicative prices, but the collection methodology remains unknown. Agromate explicitly distinguishes nearby surveyed markets from its own Plateau pilot estimates; its CSVs and model backtests remain uninspected. The possible Plateau traceability/coverage opportunity remains a hypothesis. No raw data integration, full rights review or user problem validation has been completed.
