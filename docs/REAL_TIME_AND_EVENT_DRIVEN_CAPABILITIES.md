# Real-Time and Event-Driven Capabilities

**Status:** Active, conditional architecture principle  
**Decision:** [D-016](DECISIONS.md#d-016-enable-real-time-capabilities-only-when-justified)  
**Scope:** Cross-cutting; applies to the agricultural pilot and any later sector or system

## 1. Principle

Design systems so that selected information sources, events and operational workflows **can support real-time or near-real-time updates when a demonstrated business or operational requirement justifies the added complexity, cost, infrastructure and operational responsibility**.

Real-time capability is an option to be earned by requirements and evidence, not a default design target. The project does not need every source, dataset, agent or workflow to operate continuously.

## 2. Choose freshness according to the decision

Different information has different time sensitivity. Select the least complex update mode that keeps the information sufficiently fresh for the decision being made.

| Update mode | Meaning | Suitable situations (illustrative) |
|---|---|---|
| On-demand | Retrieve or refresh when a person or process requests it | Investigating a particular supplier, buyer, market or policy question |
| Scheduled/batch | Collect at defined intervals | Daily market summaries, periodic registry refreshes and routine reports |
| Near-real-time | Detect and process changes shortly after they occur, subject to source and system delays | New buyer requests, important listing changes or time-sensitive alerts |
| Real-time/streaming | Process events continuously or with very low latency | A genuinely time-critical operational process where delay materially affects the outcome |

These labels are relative to the use case and source. Do not promise a latency target until it has been defined, measured and shown to be achievable.

## 3. Requirements test before introducing continuous updates

For each candidate source or workflow, establish:

1. **Decision:** Which specific decision or action depends on this information?
2. **Freshness need:** How old can the information be before it becomes materially less useful or unsafe?
3. **Change pattern:** How often does relevant information change, and how quickly must the change be noticed?
4. **Source capability:** Does the source provide an authorised API, webhook, event feed, export or other reliable change signal?
5. **Access and rights:** Are automated access, storage, reuse and redistribution permitted for the intended purpose?
6. **Reliability:** How will duplicates, missing events, delayed events, outages, corrections and conflicting updates be handled?
7. **Economics:** Does the value of faster information justify provider fees, infrastructure, monitoring and maintenance?
8. **Fallback:** What happens when the source or update pipeline is unavailable? Can a scheduled or on-demand process safely substitute?
9. **Human authority:** Which notifications or actions require review or approval before external consequences occur?
10. **Measurement:** What freshness, completeness, accuracy, availability and cost measures will establish whether the design works?

If the decision does not materially benefit from faster updates, retain a scheduled or on-demand approach.

## 4. Candidate engineering mechanisms

Depending on the source and requirement, possible mechanisms include:

- Webhooks and provider event notifications.
- Event feeds, streaming APIs and message brokers.
- Scheduled polling and incremental synchronisation.
- Change detection, version checks and reconciliation.
- Queues, retries, idempotency and dead-letter handling.
- Event timestamps, ordering, deduplication and late-arriving data.
- Monitoring, alerting, back-pressure and recovery procedures.

These are candidate mechanisms to study and assess, not a required technology stack. Prefer source-supported mechanisms and existing managed services when they satisfy the need. Do not introduce a message broker, streaming platform or always-on infrastructure merely because it is associated with real-time architecture.

## 5. Agricultural intelligence examples

Possible future candidates include:

- Buyer requirements or supplier availability where a delay could cause a missed transaction.
- Material changes to a market listing or quotation that require prompt revalidation.
- Weather, transport disruption or policy events when a specific operational decision is time-sensitive.
- Incoming authorised email or platform notifications that should enter a review queue.

These examples do not establish that continuous monitoring is currently needed, that the relevant sources support it, or that any integration has been approved. Daily market research and summary reporting may remain scheduled; some investigations may remain on-demand.

## 6. Governance and evidence safeguards

- Preserve source identity, event time, observation time, retrieval time and processing time where available.
- Distinguish a source event from the system's observation of that event; delivery time is not necessarily occurrence time.
- Treat notifications and posts as claims or signals until checked against the applicable evidence standard.
- Design for duplicate, delayed, missing, reordered, corrected and contradictory events.
- Respect source terms, privacy, consent, licensing, quotas, security and retention requirements.
- Apply least privilege and keep external actions within explicitly authorised boundaries.
- Use human approval for consequential actions where required; faster processing must not silently expand agent authority.
- Maintain a safe fallback and make stale or unavailable data visible rather than presenting it as current.

## 7. Maturity boundary and current position

This principle records a future design direction. It does **not** mean that real-time monitoring, event streaming, webhooks, continuous ingestion or an always-on agentic system has been implemented or selected.

The current agricultural daily brief remains a scheduled, human-supervised workflow. Future work should first validate the use case, source access, freshness requirement, operational value and cheapest reliable test. Only then should the architecture be extended.

## 8. Relationship to the curriculum

The principle connects to several disciplines without creating a new discipline:

- Reasoning and Planning: time constraints, deadlines, dependencies and replanning.
- Information acquisition: source access, polling, event feeds and incremental retrieval.
- Context, Memory and Knowledge: temporal validity, state updates and event history.
- Tools and Environment Engineering: authorised interfaces and provider capabilities.
- Execution and Loop Engineering: event handling, retries, idempotency and recovery.
- Orchestration: triggers, queues, coordination and workload control.
- Governance and Evaluation: authority, privacy, reliability, freshness and measurable service levels.

Study each mechanism in depth when the curriculum or a validated practical requirement reaches it.
