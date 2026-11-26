# Chapter 5 — Autonomy Levels and the Autonomy Spectrum

## Central question

How much freedom should an agent have to make decisions and take actions without human approval?

Not every agent needs the same degree of independence. The appropriate level depends on its responsibilities, permissions, reliability and the consequences of its actions.

## Five-level teaching framework

The following five levels are an illustrative framework used in this project. They are not presented as a universally adopted industry standard.

| Level | Name | Description |
|---:|---|---|
| 1 | Advisory | Analyses information and recommends actions; a human decides what happens. |
| 2 | Assisted execution | Prepares actions but requires human approval before execution. |
| 3 | Conditional autonomy | Executes approved categories of work within limits and escalates unusual or high-risk cases. |
| 4 | High autonomy | Plans, executes, monitors and adjusts activities independently within established policies. |
| 5 | Full operational autonomy | Manages complex, ongoing objectives with minimal routine human intervention. |

## What shapes autonomy?

1. **Decision authority:** which decisions the agent may make.
2. **Execution authority:** which actions it may perform.
3. **Permission boundaries:** what it can access and what it is prohibited from doing.
4. **Resource authority:** which data, money, infrastructure or other resources it can use.
5. **Approval requirements:** which actions need human authorisation.
6. **Escalation mechanisms:** when the agent must stop and request intervention.
7. **Recovery authority:** whether and how the agent can correct, reverse or recover from an action.

An agent's intelligence does not by itself determine its autonomy. Permissions, controls and operating conditions are also decisive.

## Autonomy is not unrestricted freedom

For example, an agricultural market agent may be allowed to collect public prices, compare markets, detect unusual movements and prepare reports. It need not have permission to transfer money, purchase produce, publish unverified allegations or delete historical records.

**Principle:** An agent's authority must be deliberately designed, not accidentally granted.

## Human oversight vocabulary

- **Human-in-the-loop:** a human participates in the decision or execution process.
- **Human-on-the-loop:** a human supervises an operating system and can intervene.
- **Human-out-of-the-loop:** the system operates without routine human intervention.

These terms describe different relationships between people and automated activity. They do not, by themselves, specify the full permission or risk model.

## Differentiated autonomy across agents

The agricultural intelligence example contains specialised agents with different responsibilities:

| Illustrative agent | Responsibility | Proposed starting level |
|---|---|---:|
| Market data collector | Collects market prices | 4 |
| Information verification agent | Verifies collected information | 3 |
| Market analysis agent | Analyses movements and patterns | 4 |
| Opportunity discovery agent | Identifies and proposes opportunities | 2–3 |
| Reporting agent | Sends reports and notifications | 3 |

These are discussion examples, not approved production settings. Actual autonomy should be based on the real operating environment, demonstrated reliability, authorisations and consequences.

## Key concepts introduced

- Bounded autonomy
- Human-in-the-loop
- Human-on-the-loop
- Human-out-of-the-loop
- Escalation
- Permission architecture
- Autonomy scaling
- Reversibility

## Principle established

**Different agents should have different autonomy levels according to their responsibilities and potential consequences.** Equal autonomy is not a design requirement.
