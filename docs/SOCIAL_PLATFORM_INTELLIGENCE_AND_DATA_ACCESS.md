# Social Platform Intelligence and Data Access

**Status:** Cross-cutting project reference and source-access guidance  
**Research checked:** 28 November 2026  
**Implementation status:** No social listening provider, API connector, collection pipeline or platform-specific integration has been selected or deployed  
**Applies to:** Agricultural intelligence pilot and future sector research

## 1. Purpose

Social platforms are part of the wider information environment that the project may need to understand. They can surface local market signals, product availability, producer activity, buyer requests, supply disruptions, business announcements, events, policy discussions and emerging opportunities.

The project should therefore consider social platforms as potential **information sources and communication channels**, not simply as websites to scrape.

The objective is not to collect as many posts, profiles or messages as possible. It is to identify information relevant to a defined intelligence question, obtain it through an authorised route, assess what it actually supports, preserve provenance and protect the people whose information is processed.

This document applies the source-first principles in [Web Data Acquisition and Scraping](WEB_DATA_ACQUISITION_AND_SCRAPING.md). Platform features, API access and terms change. Recheck official documentation and the specific app's permissions before each implementation decision.

## 2. What social platform information may contribute

For agricultural intelligence, relevant public or properly submitted information may include:

- Producers announcing harvests, expected availability or produce for sale.
- Farmers, cooperatives or aggregators publishing procurement or supply requests.
- Traders and market participants publishing indicative prices, grades, quantities and delivery locations.
- Buyers, processors, retailers or institutions communicating demand or procurement needs.
- Announcements about farm inputs, storage, processing, transport, logistics and market events.
- Reports of weather impacts, road disruptions, local shortages, disease concerns or other supply-chain signals.
- Government, research, company and industry announcements that may affect agricultural markets.
- New businesses, projects, partnerships, tenders, events and investment opportunities.

Potentially useful social information is not automatically reliable. Posts may be promotional, outdated, duplicated, incomplete, exaggerated, mistaken, fraudulent or deliberately misleading. The platform, account and post do not independently prove the underlying claim.

The same methods may support other sectors, but each sector needs its own source, evidence, privacy and risk assessment.

## 3. Social listening is broader than scraping

**Social listening / social intelligence** is the process of discovering, collecting, organising and assessing relevant social-platform information to understand topics, events, public discussion and market signals.

It may use several acquisition methods:

- Official platform APIs and approved developer products.
- Insights and analytics for accounts or Pages that the project or an authorised client owns or manages.
- Approved research access or data libraries.
- Licensed social-listening providers or authorised data partners.
- Webhooks and messages voluntarily sent to an authorised business account.
- Manual research, links, exports or evidence submitted by users with appropriate rights.
- Web scraping only where the platform expressly permits the collection and the intended use.

A social-listening process is therefore not synonymous with a scraper. A supplier's dashboard, API, research programme or permissioned inbox may be the appropriate acquisition route.

A third-party tool or data broker does not automatically make collection permissible. Check how it obtained the information, what the platform permits, what licence or authority applies, and whether downstream use, retention and redistribution are allowed.

## 4. Platform-by-platform access reality

The following is an initial desk assessment of official documentation checked on 28 November 2026. It is not a guarantee that a particular app will be approved or that all endpoints will be available to this project.

### Facebook

Possible intelligence value:
- Public Page announcements and offers.
- Public community or event information where access is permitted.
- Posts from agriculture, trade, market, cooperative and industry organisations.
- Page insights and engagement data for a Page that an authorised user manages.

Access considerations:
- Meta's Graph API provides Page-related endpoints. Reading Page-owned data and reading qualifying public Page data are different permission cases; the Page Public Content Access (PPCA) feature may be required for the latter. Feature approval, tokens, rate limits and endpoint-specific restrictions apply.
- Meta states that automated collection from its products requires prior permission or explicit authorisation. Merely viewing public content in a browser does not itself grant permission to scrape it.
- Meta Content Library is a separate controlled-access research product. Its 16 November 2026 documentation covers qualifying public Facebook and Instagram content, including eligible Pages, groups, events and profiles. Access requires affiliation with a qualified academic or non-academic research institution and approval; individuals may participate through an eligible research programme but should not assume that an unaffiliated personal project qualifies. Its API operates in Meta's Secure Research Environment or an approved cleanroom, and downloading data from the API is not permitted. This is a research route, not a general-purpose public or commercial social-listening API.

Official references:
- [Graph API — Page Published Posts](https://developers.facebook.com/docs/graph-api/reference/page/published_posts/)
- [Graph API — Page reference and permissions](https://developers.facebook.com/docs/graph-api/reference/page/)
- [Meta Automated Data Collection Terms](https://www.facebook.com/legal/automated_data_collection_terms)
- [Meta Content Library and API](https://developers.facebook.com/documentation/meta-content-library)
- [Meta Content Library API overview](https://developers.facebook.com/documentation/meta-content-library/content-library-api/overview)

### Instagram

Possible intelligence value:
- Public business and creator announcements, product posts, harvest or inventory signals and event information.
- Content and engagement analytics for professional accounts that an authorised user manages.
- Reels, posts and comments within the endpoints and permissions available to an approved app.

Access considerations:
- The Instagram APIs support defined use cases for professional accounts and require the relevant login method, tokens and permissions. They should not be treated as unrestricted access to every public Instagram account or all platform content.
- The Instagram APIs primarily support professional Business and Creator accounts and defined account-management, content and insights use cases. They do not provide unrestricted access to every public consumer account.
- Meta Content Library includes qualifying public Instagram content for approved research access, subject to institutional eligibility, inclusion rules and controlled-environment restrictions. It is not a general download service.
- Meta's automated collection rules apply to scraping of Meta products; do not assume public visibility authorises automated extraction.

Official references:
- [Instagram API documentation](https://developers.facebook.com/docs/instagram-platform/)
- [Instagram API with Instagram Login — changelog and permissions](https://developers.facebook.com/docs/instagram/platform/instagram-api/changelog/)
- [Meta Content Library — Instagram coverage](https://developers.facebook.com/documentation/meta-content-library)

### WhatsApp

Possible intelligence value:
- Price lists, stock and availability information voluntarily sent to a participating business account.
- Supplier, buyer or producer quotations submitted directly to an authorised project contact.
- Customer or partner communications managed by an approved business integration.
- Public WhatsApp Channel updates where a suitable authorised source is available.

Access considerations:
- WhatsApp is primarily a private messaging service, not an open public post-search network. The project must not treat private chats, personal contacts or ordinary group conversations as public data to be extracted.
- The WhatsApp Business Platform Cloud API supports sending and receiving messages for a registered business phone number. Webhooks can deliver relevant inbound message notifications and status updates to an authorised business integration. This applies to communications with that business account, not permission to read arbitrary users' private chats.
- Meta also documents a Groups API for businesses to create and manage their own WhatsApp groups. This does not provide general access to read unrelated consumer groups or extract the history of groups that the business does not control. Eligibility, group capabilities and limits must be checked before considering it.
- Meta Content Library's November 2026 documentation includes qualifying public WhatsApp Channels and their recent updates in a controlled research environment. Coverage is limited to eligible public channels (verified or meeting a follower threshold) and updates from the last 30 days. It is not general access to private WhatsApp groups or personal messages.

A safer agricultural collection model may invite producers, traders and cooperatives to submit a price or supply observation to a dedicated project/business contact, explain its intended use, and capture only the information necessary for that purpose.

Official references:
- [WhatsApp Business Platform overview](https://developers.facebook.com/documentation/business-messaging/whatsapp/overview)
- [Meta Content Library API overview — WhatsApp Channels coverage](https://developers.facebook.com/documentation/meta-content-library/content-library-api/overview)

### X (formerly Twitter)

Possible intelligence value:
- Public posts and replies about market conditions, product availability, prices, government announcements, disruptions and emerging topics.
- Posts from selected public accounts or keyword-based public search, within available API endpoints and access limits.
- Direct-message integrations only for accounts and people who have explicitly authorised the relevant application access.

Access considerations:
- X's official API provides programmatic access to public posts and replies, including keyword searches or posts from selected accounts. Direct Message access requires separate permission from the account holder.
- X's Terms of Service effective 9 October 2026 state that scraping the service without express written permission is prohibited and require access through its published interfaces. Non-API scripting of the website should not be treated as an alternative access route.
- At the time checked, X's developer console describes consumption-based, pay-per-use API billing with no fixed monthly cost. Its displayed Posts: Read rate is US$0.005 per resource fetched. This is a live price indication, not a long-term quote; confirm which objects are billable, current rates, endpoint availability, rate limits and data-use restrictions before relying on X. A broad monitoring query could become costly, so begin with a narrow test and estimate cost per useful observation.

Official references:
- [About X's APIs](https://help.x.com/en/rules-and-policies/x-api)
- [X Terms of Service](https://x.com/en/tos)
- [X Automation rules](https://help.x.com/en/rules-and-policies/x-automation)
- [X Developer Platform](https://developer.x.com/)

### LinkedIn

Possible intelligence value:
- Public announcements by companies, industry associations, public institutions and professional organisations.
- Procurement, project, partnership, investment, hiring and sector-development announcements.
- Analytics and community management for an organisation's own LinkedIn Page where authorised API access is granted.

Access considerations:
- LinkedIn's Community Management APIs have a vetted access process. Its current access guidance states that the programme is limited to registered legal organisations for commercial use cases, and applications are reviewed. A personal developer account or personal email should not be assumed to qualify.
- LinkedIn explicitly prohibits third-party scraping software, crawlers, browser extensions and unauthorised automation on its website. Its API terms also restrict access to content obtained outside official APIs.
- For this project, use public company announcements through legitimate links, authorised APIs, licensed providers or direct submissions; do not scrape member profiles or automate personal-account activity.

Official references:
- [LinkedIn Community Management API access review](https://learn.microsoft.com/en-us/linkedin/marketing/community-management-app-review)
- [LinkedIn Community Management API overview](https://learn.microsoft.com/en-us/linkedin/marketing/community-management/community-management-overview)
- [LinkedIn prohibited software and extensions](https://www.linkedin.com/help/linkedin/answer/a1341387/prohibited-software-and-extensions)
- [LinkedIn API Terms of Use](https://developer.linkedin.com/legal)

## 5. Initial platform comparison for this project

| Platform | Potentially useful source material | Initial access posture |
|---|---|---|
| Facebook | Public Page and qualifying public community content; authorised Page insights | Graph API permissions, controlled research access or expressly authorised collection |
| Instagram | Professional account content and qualifying public posts | Professional-account permissions or controlled research access |
| WhatsApp | Voluntary submissions and business conversations; public Channel updates | Business API/webhooks for the connected business; no general private-chat extraction |
| X | Public posts and replies | Official API, registered app, current access plan and usage restrictions |
| LinkedIn | Company and industry announcements; own Page analytics | Vetted official APIs; scraping and unauthorised automation prohibited |

This comparison is about access methods, not a ranking of data value. We should not assume that the platform with the most visible activity has the most representative or useful market information.

### Practical access position for an individual or small project

The access conditions matter to our resource constraints:

- **Meta Content Library:** potentially valuable for broad research on eligible public Facebook and Instagram content, and qualifying WhatsApp Channels, but it is not a simple self-service scraping API. Applicants need affiliation with a qualified academic or non-academic research institution and approval. The API runs in a controlled research environment and does not permit data downloads. This should be treated as a possible research collaboration route, not an assumed available tool.
- **Facebook Page / Instagram professional APIs:** more realistic when an organisation or client authorises access to its own Page or professional account, subject to app review and specific permissions. They should not be mistaken for general public-content search APIs.
- **WhatsApp Business Platform:** potentially useful for collecting voluntary submissions through a dedicated business contact and webhook. It is not an archive or search engine for other people's chats.
- **X API:** the developer console currently advertises pay-per-use billing. Even though there is no fixed monthly charge, per-resource reading can accumulate. Avoid broad collection until a small query proves useful and the cost is measured.
- **LinkedIn Community Management API:** access is currently vetted for registered legal organisations and supported commercial use cases; the requirements include a verified business email, organisation details, privacy policy and a linked Page administrator's verification. This is a significant barrier for an unaffiliated individual project.

For our initial work, manually reviewing a small number of relevant public links and inviting voluntary supplier/market submissions may be more feasible than building a continuous social crawler.

### Other platforms not yet assessed

TikTok, YouTube, Telegram, Reddit, Threads and sector-specific online communities are candidates for later source discovery. Their access methods, restrictions, representativeness and costs have not been assessed in this document. Do not assume they offer equivalent public search APIs or scraping rights.

## 6. How social observations should be classified

Preserve the distinction between the content that was posted and the real-world event it claims to describe.

Examples:

- A public post saying "fresh tomatoes available today at ₦X per basket" is initially an **unverified information item or market signal**. It may become a verified quotation after the seller and the specific terms are independently confirmed.
- A buyer post saying "looking for 100 bags of maize" is a **demand signal**, not proof that a purchase occurred.
- A producer's direct submission to the project can support a **verified quotation** only after the source, terms, date, product, unit, quantity and location have been checked to the required standard.
- A post saying "the market is short of onions" is a **claim or market signal**, not proof of a shortage.
- A post announcing a completed sale does not establish a **verified transaction** without adequate evidence of the actual exchange.

Use the project's four evidence categories:
1. Verified transactions.
2. Verified quotations.
3. Unverified information.
4. Market signals.

Additional source attributes should record whether a post is an offer, request, opinion, announcement, report, rumour, completed-event claim or repost. These are descriptive labels, not substitutes for evidence classification.

Multiple reposts of the same original claim are not independent corroboration. A large volume of posts may reflect coordinated promotion, platform algorithms, a highly active minority or duplicate content rather than the whole market.

Do not infer exact farm locations, identities, quantities, prices or supply-chain relationships that the content does not support.

## 7. Practical social intelligence workflow

A controlled workflow may be:

1. Define an intelligence question, such as whether there are new tomato supply offers in a specified market area.
2. Identify the relevant source communities, public Pages, accounts, channels or approved research datasets.
3. Check what data can lawfully and contractually be accessed, for what purpose and by which method.
4. Collect only the posts or submissions relevant to the question.
5. Preserve the original reference, timestamp, collection time and method.
6. Extract the relevant claim, product, price, unit, quantity, location, time and stated actor role where available.
7. Detect duplicates, reposts, stale claims and obvious inconsistencies.
8. Classify evidence status and confidence; keep unsupported details unresolved.
9. Seek confirmation from the seller, buyer, producer or other source where necessary and authorised.
10. Present useful trends and opportunities with clear limitations and human review where appropriate.

This process may use conventional filtering and deduplication, an agent for bounded interpretation, reusable Skills for assessment procedures, automation for scheduled collection and workflow orchestration for hand-offs. The acquisition method and autonomy level must be selected separately.

## 8. Minimum provenance and recordkeeping

For each collected social observation, retain only what is necessary and permitted. Depending on the use case, fields may include:

- Platform and source type (Page, public account, Channel, post, approved message submission).
- Original post or message reference, URL or platform ID where retention and use are permitted.
- Source account or publisher name when necessary to assess the claim; avoid building unnecessary personal-profile dossiers.
- Content publication time and collection time, with timezone where available.
- Product, form, grade, price, currency, unit, quantity, location and market level as explicitly stated.
- Whether the statement is an offer, request, report, opinion, announcement, repost or claim of completed activity.
- Original wording or a permitted evidence snapshot, plus extracted and normalised values.
- Acquisition method, API/connector and version, permission scope and applicable use conditions.
- Evidence category, review status, limitations, duplicate-group reference and corrections.
- Retention or deletion rule and the applicable lawful basis or consent record where required.

Distinguish the time a post was published from the time the market event occurred. A post can be recent but describe an old price, a future offer or an event in another location.

## 9. Privacy, safety and responsible use

A public post is not a blanket licence to collect, profile, retain, combine, redistribute or sell personal information.

Apply purpose limitation, data minimisation, accuracy, retention limitation, security and accountability. The Nigeria Data Protection Act 2023 applies to personal-data processing in the circumstances described in section 2. Section 24 sets out processing principles, and section 25 requires an appropriate lawful basis. Public availability does not by itself establish that every intended collection or reuse is lawful. The appropriate lawful basis and any additional obligations must be assessed for the actual use case.

For this project:
- Prefer organisation, market, product and event information over personal-profile data.
- Do not attempt to access private accounts, private groups, personal messages or contact lists without a valid authorised route and the required rights and permissions.
- Do not infer or store sensitive personal characteristics from posts.
- Avoid unnecessary collection of phone numbers, exact home addresses, personal images or identifiable details.
- Do not expose a contributor's private message or contact details in a public report without an appropriate basis and authorisation.
- Explain the purpose and handling of data when inviting people to submit observations.
- Provide appropriate correction, withdrawal, deletion and access processes where required.
- Limit access, retention and onward sharing to what is justified.
- Require human review before contacting individuals, publishing allegations or taking consequential actions.

This document is engineering guidance, not legal advice. Uncertain or higher-risk processing should receive qualified data-protection and legal review.

Official references:
- [Nigeria Data Protection Act 2023](https://ndpc.gov.ng/wp-content/uploads/2024/03/Nigeria_Data_Protection_Act_2023.pdf)
- [Meta Content Library access requirements](https://developers.facebook.com/documentation/meta-content-library/get-access)
- [X Developer Platform pricing](https://developer.x.com/)
- [LinkedIn Community Management API access review](https://learn.microsoft.com/en-us/linkedin/marketing/community-management-app-review?view=li-lms-2026-06)
- [Instagram API documentation from Meta](https://www.postman.com/meta/instagram/documentation/6yqw8pt/instagram-api)

## 10. Important limitations and failure modes

Social-platform data is not a census of real-world activity. Important limitations include:

- **Selection bias:** not every producer, trader, buyer or region uses a particular platform.
- **Visibility bias:** platform algorithms and privacy settings determine what can be seen.
- **Geographic ambiguity:** account location, post location and actual transaction location may differ.
- **Time ambiguity:** a newly published post can describe a stale event or an offer that is no longer valid.
- **Identity uncertainty:** account names may not establish a person's or organisation's real-world identity.
- **Duplicate amplification:** copied and reposted content may create false impressions of independent corroboration.
- **Promotion and fraud:** sellers may exaggerate availability, prices, quality or demand.
- **Language and context:** local expressions, slang, abbreviations, dialects, images and voice notes may be misinterpreted.
- **Platform dependence:** API changes, permissions, charges, rate limits and policy changes may disrupt collection.
- **Evidence gaps:** a public statement may not prove that a product exists, is in stock, was delivered or was sold.

These limitations must be reflected in the output rather than hidden behind automated sentiment scores or large post counts.

## 11. How this fits the 13 disciplines

Social-platform intelligence is a cross-cutting capability, not a new discipline.

| Discipline | Relationship |
|---|---|
| 1. Agent Architecture and Design | Decide whether social monitoring needs a connector, workflow, agent or combination. |
| 2. Reasoning and Planning | Define the question, source scope, collection plan and response to uncertain observations. |
| 3. Context, Memory and Knowledge | Preserve source context, claims, provenance, time and evidence history. |
| 4. Tools and Environment Engineering | Integrate official APIs, approved providers, webhooks and permitted collection methods. |
| 5. Execution and Loop Engineering | Run collection, validate payloads, handle failures and avoid duplicate processing. |
| 6. Orchestration and Multi-Agent Systems | Coordinate multiple sources, review steps and downstream analysis where justified. |
| 7. Security, Safety and Governance | Protect access credentials, data and users; enforce privacy and permission boundaries. |
| 8. Agentic Governance and Self-Governing Systems | Govern permitted sources, delegated decisions, retention and changes to collection policy. |
| 9. Evaluation and Testing | Test extraction, classification, duplicate detection, coverage and false-positive rates. |
| 10. Human-Agent Interaction | Enable source confirmation, correction, contributor submissions and review. |
| 11. Observability and Reliability | Monitor data freshness, access failures, policy changes and connector health. |
| 12. Performance and Infrastructure | Manage API quotas, throughput, storage, queues and cost. |
| 13. Evolution and Continuous Improvement | Maintain connectors, procedures, source assessments and tested changes. |

## 12. Initial project position and next research questions

Social platforms are recognised as candidate source classes for the wider intelligence mission. They are not yet approved production inputs.

Before selecting any platform integration, answer:
- Which concrete intelligence question requires the platform?
- Is the relevant information public, private, user-submitted or owned by an organisation we are authorised to manage?
- What official API, research programme, partner or other permitted access method exists?
- Is access available to an individual, or does it require a registered organisation, app review, research affiliation or paid access?
- What are the costs, quotas, permitted purposes, retention rules and redistribution limits?
- Which claims can the data actually support?
- How will identity, time, location, duplication, provenance and corrections be handled?
- Is the information worth collecting compared with more direct sources or submissions?

Start with a small, lawful and testable use case. Expand only when evidence establishes usefulness, representativeness, permitted access and sustainable operating cost.

**Working rule:** use social platforms to discover and assess relevant public signals or receive properly authorised submissions; do not treat the platforms as unrestricted databases or people's private conversations as raw material for extraction.
