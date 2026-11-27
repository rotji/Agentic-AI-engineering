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

### Source entries

_No source has yet been assessed under this register._

| Source ID | Source/platform | Source type | Geography | Information type | Date checked | Status | Next action |
|---|---|---|---|---|---|---|---|
| — | — | — | — | — | — | Not assessed | Identify and inspect candidate sources |

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

**Current discovery state:** register created; entries remain unassessed. No user problem, source, product scope or solution has been validated by this template alone.
