# Agricultural Pilot Charter

**Version:** 0.1  
**Status:** Working discovery charter — provisional, not yet an approved product specification  
**Project:** Agentic AI Engineering  
**Pilot domain:** Agriculture  
**First candidate capability:** Agricultural market observation intelligence and evidence handling

## 1. Why this charter exists

This charter gives the agricultural practical work a concrete starting point while protecting the wider programme from premature narrowing.

It is a discovery and validation charter, not a declaration that a final product, architecture, dataset or market opportunity has already been established.

The pilot will help us determine:
- Which real agricultural information problem is important enough to address first.
- Which people need the information and what decisions it should support.
- What evidence and data are actually accessible.
- Which existing services, datasets, tools and human processes can provide the required capabilities.
- What can be assembled and tested before considering custom software.
- What measurable and qualitative conditions would demonstrate that the pilot is useful.

## 2. Connection to the wider programme

The wider agricultural intelligence ambition remains broad. It includes discovering, organising, assessing and connecting information about:
- Raw agricultural products, processed products and commercially relevant by-products.
- Producers, farms, cooperatives, production clusters and agricultural facilities.
- Production locations across villages, LGAs, states and other relevant geographies.
- Processing, storage, aggregation, transport, distribution and market destinations.
- Farmgate, wholesale and retail markets.
- Prices, quotations, transactions, supply conditions and other market signals.
- Domestic and international developments that may affect Nigerian agriculture.
- Commercial opportunities and decision-support questions.

The wider programme is not restricted to one commodity, one LGA, one state or one market level. Plateau State's 17 LGAs are an important part of the intended coverage, alongside other Nigerian states, major markets and relevant international developments.

The first pilot will test a bounded slice of this wider ambition. A bounded test scope is a starting point for learning, not a permanent limit on the programme.

## 3. Provisional first-pilot hypothesis

**Working hypothesis — not yet verified:** useful agricultural market information can be difficult to compare and assess because observations may be scattered across different sources, locations, product forms, market levels, units and observation periods, with inconsistent evidence quality.

This may make it harder for a user to understand:
- What was actually observed.
- Where and when it was observed.
- Whether the information is a completed transaction, a quotation, an unverified claim or an indirect market signal.
- Whether two observations are genuinely comparable.
- Which claims require additional verification.
- Which apparent patterns are supported by enough evidence to be worth investigating.

The first discovery task is to test whether this is a real and sufficiently important problem for identifiable users. Do not present this hypothesis as an established finding until evidence supports it.

## 4. Provisional pilot candidate

Subject to discovery, the current candidate is an **agricultural market observation intelligence workflow**.

A first version could take a small, agreed set of observations from permitted sources and move them through these stages:

1. Capture the original observation and its source.
2. Preserve what the source actually says, including date, location, product form, unit, price and market level where available.
3. Normalise fields where comparison is justified, while retaining original values.
4. Classify the evidence status.
5. Detect missing details, duplicates, inconsistencies and incompatible observations.
6. Compare observations only when the relevant dimensions are sufficiently compatible.
7. Identify patterns and unresolved questions without overstating conclusions.
8. Produce a concise, traceable intelligence output for review.

This is a candidate workflow, not a committed architecture. It may use existing platforms, manual review, spreadsheets, APIs, automation, AI assistance or custom components. The combination must be selected only after the actual requirements and available solutions are understood.

## 5. Initial evidence vocabulary

The pilot should preserve the project's four working evidence levels:

| Evidence level | Meaning for the pilot |
|---|---|
| **Verified transaction** | Evidence supports that a transaction was completed. |
| **Verified quotation** | Evidence supports that a price was quoted; it does not establish a completed transaction. |
| **Unverified information** | A relevant claim has been encountered but has not met the required verification standard. |
| **Market signal** | An indirect indication that may point to a development worth investigating. |

These are working categories, not a complete verification policy. The exact evidence required for each category must be defined, tested and documented. A source's existence, popularity or repetition does not by itself make a claim verified.

Evidence status must be kept separate from source reliability, sample representativeness, freshness, comparability and the strength of a conclusion drawn from it.

## 6. Candidate observation record

For each observation, investigate whether the workflow can preserve the following information where available:

- Commodity or product identity.
- Product form, variety, grade or quality description where relevant.
- Market level: farmgate, wholesale or retail.
- Price and original unit.
- Any justified standardised unit, stored alongside—not instead of—the original.
- Market name and geographic location at the precision supported by the source.
- Observation date or period, distinct from the date the information was collected.
- Source name, original URL or reference, and source type.
- Evidence level and the basis for that classification.
- Quantity, packaging, delivery or transaction context when relevant.
- Missing fields, conflicts, duplicates and verification notes.
- Date of last review and any change in status.

Do not invent missing values. Do not imply village-level or farm-level precision when the source only identifies a broader location. Do not merge observations that differ materially in product form, grade, unit, market level or time period.

The final record schema remains to be tested against real source examples.

## 7. Intended users and decisions — unresolved

The first intended users have not yet been confirmed. Discovery should examine possible needs among:
- Producers and cooperatives.
- Traders, aggregators and processors.
- Buyers and other market participants.
- Researchers, analysts and agricultural organisations.
- Other people or institutions making sourcing, market or planning decisions.

These are discovery candidates, not confirmed customers or users.

We must identify who has the problem, what they currently do, what it costs them in time, money or missed information, what evidence they trust and what output would genuinely help them.

Do not assume that a useful dataset automatically creates a paying market or that every potential user wants the same product.

## 8. First practical milestone: prove one complete evidence path

Before building a broad platform, demonstrate one complete and reviewable path:

**Source → observation capture → original evidence preservation → classification → quality checks → comparison where justified → reviewed output.**

The first test scope should be chosen after source discovery. It may use a small sample of products, locations, sources and observation periods, but the selection must be explained and recorded.

A manual or spreadsheet-based test is acceptable at the beginning. Automation is not an objective in itself. The first priority is to establish whether the information can be captured, assessed and turned into a useful, traceable result.

## 9. Provisional acceptance conditions

The first test should not be declared successful merely because it produces a dashboard, report or large number of records.

At minimum, the test should establish whether:

1. Every included observation can be traced to its original source or an explicit explanation of why the source cannot be recovered.
2. The original wording and values can be retained separately from any normalised representation.
3. Observation date and collection date are not confused.
4. Product form, unit, grade and market level remain distinguishable.
5. Evidence categories are applied consistently against documented rules.
6. Unknown or missing information is labelled rather than invented.
7. Duplicate and conflicting observations can be identified and handled.
8. Comparisons are made only when the relevant dimensions are sufficiently compatible.
9. Conclusions identify their geographic, product and time coverage.
10. A reviewer can understand what is observed, what is inferred and what remains unresolved.

Numeric targets, error tolerances, freshness thresholds, update frequency and sample sizes must be set after the initial source and workflow assessment. They should not be invented in advance.

## 10. Boundaries and safeguards

The first pilot will not:
- Guarantee that prices or other market information are complete or representative.
- Treat a quotation as proof of a completed transaction.
- Present an unverified claim or market signal as a confirmed fact.
- Claim a statewide or national trend from a narrow or biased sample.
- Infer causation from correlation or repeated observations alone.
- Conduct transactions, broker deals or make commitments on behalf of users.
- Contact producers, traders, institutions or other external parties without an explicit authorised process.
- Collect private, confidential or personal information without a lawful basis, appropriate permission and a defined need.
- Adopt a paid platform, incur a subscription or commit to a provider before fit, rights, cost and alternatives are assessed.

Use public or otherwise properly authorised sources and respect applicable access conditions, terms, privacy requirements and data rights. Human review must remain available for uncertain or consequential conclusions.

## 11. Discovery and execution sequence

### Stage A — Confirm the problem

- Identify people who experience the suspected problem.
- Examine how they currently obtain, compare and verify information.
- Collect concrete examples of useful and unreliable observations.
- Determine what decisions or tasks are affected.
- Record evidence that supports or contradicts the problem hypothesis.

### Stage B — Establish a bounded test scope

- Select a small, defensible sample of products, locations, market levels, sources and periods.
- Explain why the sample was selected and what it cannot represent.
- Define the evidence rules and initial acceptance conditions.
- Identify access, permission, privacy and data-rights constraints.

### Stage C — Discover existing capabilities

- Identify existing datasets, platforms, APIs, open-source tools, spreadsheets, services and human verification processes.
- Compare them against the requirements, not marketing claims.
- Assess accessibility, licensing, data rights, reliability, interoperability, cost and exit options.
- Prefer reuse, integration or partnership where suitable.

### Stage D — Assemble and test

- Begin with the simplest adequate workflow.
- Capture and classify a controlled sample.
- Review traceability, comparability, evidence quality and usefulness.
- Record errors, missing data, failure modes and operating effort.
- Automate only where repeated work or quality requirements justify it.

### Stage E — Decide what happens next

Based on the evidence, choose to:
- Expand the test.
- Change the problem or scope.
- Adopt or integrate an existing solution.
- Build a small missing component.
- Partner with an existing provider.
- Pause or stop if the problem, evidence or value is insufficient.

## 12. Open questions that must be resolved

- Which user group experiences the strongest and most actionable problem?
- Is the initial problem primarily price discovery, source verification, comparison, producer discovery or another need?
- Which products and product forms have adequate source coverage for a first test?
- Which locations and market levels can be observed reliably?
- Which sources provide usable data, under what conditions and with what rights?
- What evidence is sufficient for each of the four working evidence levels?
- What update frequency is useful and realistically achievable?
- What output would help the intended user make a better decision?
- What existing platforms or providers already solve parts of the problem?
- What is the smallest useful test that can be completed with available resources?

These questions are intentionally open. They are not permission to fill gaps with guesses.

## 13. Decision gates

Do not progress to broad implementation until there is evidence that:
- A real user problem exists.
- A bounded test can be performed with accessible and permitted evidence.
- The proposed workflow produces a useful result.
- The chosen solution approach is justified against existing alternatives.
- The test can be evaluated against explicit acceptance conditions.

A successful first test supports further investigation; it does not automatically validate the full agricultural intelligence ambition or establish transferability to other sectors.

## 14. Relationship to Agentic AI Engineering

This pilot is also a practical learning environment for the 13 disciplines:

- Architecture and requirements define the shape and boundaries of the system.
- Reasoning and planning support source assessment, inference and workflow planning.
- Context, memory and knowledge support information organisation and retrieval.
- Tools and environment engineering support authorised data access and interfaces.
- Execution and loop engineering support reliable processing and feedback.
- Orchestration may coordinate tasks when there is a demonstrated need.
- Security, safety and governance establish restrictions and accountability.
- Evaluation and testing establish whether outputs are correct and useful.
- Human-agent interaction supports review and clarification.
- Observability, performance and evolution support dependable operation and improvement.

The pilot may initially use no autonomous agents at all. Conventional software, an existing platform, a human process or a hybrid approach may be more suitable. Agentic components should be introduced only when adaptive reasoning or action is genuinely useful and can be controlled.

## 15. Current status and next action

**Status:** Discovery charter drafted; five candidate sources/platforms have received initial desk assessment in the Discovery Register. The problem hypothesis, intended users, initial sample scope, evidence thresholds and final solution remain unvalidated.

**Next practical action:** Build a source-and-problem discovery register. For each candidate source or user problem, record the claim or need, source/person type, geographic and product coverage, observation type, access conditions, freshness, evidence quality, limitations and what needs to be verified.

The first concrete test scope should be selected from this evidence, not assumed in advance.

This charter must be updated as evidence arrives. Preserve previous decisions and explain material changes rather than silently treating provisional assumptions as facts.
