# Chapter 6 — Agent Identity, Roles and Responsibilities

**Status:** In progress

## Chapter scope

This chapter introduces the elements needed to distinguish and organise agents within a larger system:

1. **Agent identity:** what distinguishes one agent from another.
2. **Agent role:** the function it performs.
3. **Agent responsibilities:** what it is expected to accomplish.
4. **Agent authority:** which decisions and actions it is allowed to perform.
5. **Agent boundaries:** what it must not do.
6. **Agent relationships:** which other agents it can communicate or collaborate with.
7. **Agent accountability:** how actions and decisions can be traced and assessed.

## 6.1 Agent Identity

### Core question

How does a system recognise an individual agent and distinguish it from every other agent?

In a system containing many agents, each should have a distinguishable identity. This allows the system to establish which agent is performing a task, its assigned role, responsibilities, permissions, communication relationships and activity history.

### Identity is separate from the underlying model

An agent's identity is not the same as the AI model powering it.

- Multiple agents can use the same AI model while having different identities.
- Those agents can have different roles, configurations, permissions and memory.
- An agent's underlying model may change without necessarily changing its identity.

This separation allows agents to be managed as distinct system components even when they share a model.

### Principle established

**Every agent should have a clearly identifiable identity independent of the model powering it.**

### Illustrative example

A learning example uses separate identifiers for:
- A market data collection agent.
- An information verification agent.
- A market analysis agent.

The identifiers and names are illustrative. This chapter has not yet selected a technical identity standard or implementation mechanism.

## 6.2 Agent Roles

### Core question

What function is an individual agent assigned to perform within a larger system?

An agent role defines the function an agent performs within a system. It establishes the general purpose for which the agent exists and the kind of work it is expected to handle.

### Identity and role are different

In the agricultural intelligence example:

| Agent identity | Assigned role |
|---|---|
| AGENT-001 | Market Data Collector |
| AGENT-002 | Information Verification |
| AGENT-003 | Market Analyst |
| AGENT-004 | Opportunity Discovery |
| AGENT-005 | Reporting and Notifications |

The identity distinguishes the agent; the role explains its function.

### Role, responsibility, task and authority

These concepts are related but not interchangeable.

- **Identity:** Who is the agent?
- **Role:** What function does it perform?
- **Responsibility:** What is it expected to accomplish?
- **Task:** What specific piece of work must it carry out?
- **Authority:** What decisions and actions is it permitted to make?

For example, AGENT-001 may have the role Market Data Collector, the responsibility to maintain accurate and traceable market price information, and the task of collecting potato prices from designated markets today.

### Multiple roles and shared roles

One agent can perform multiple roles, but combining roles should be deliberate. Unnecessary role accumulation can make responsibilities, permissions and performance difficult to distinguish.

Multiple agents can also share the same role. For example, several market data collectors can cover different LGAs. They share a function but have different operational assignments.

Do not create separate agents merely to increase the number of agents. Separation should be justified by the work, risk, permissions, scale or need for independent handling.

### Elements of a well-defined role

A role definition should eventually establish:
1. Role name.
2. Purpose.
3. Scope of work.
4. Expected outputs.
5. Responsibilities.
6. Authority and permissions.
7. Boundaries and restrictions.
8. Relationships with other agents.

### Principles established

- Every agent should have a clearly defined role within its system.
- Roles, responsibilities, tasks and identity must not be confused.
- Multiple agents may share a role, and one agent may perform multiple roles, provided the resulting complexity and authority are justified.

## 6.3 Agent Responsibilities

### Core question

Once an agent has a defined role, what is it actually expected to accomplish and consistently handle?

An agent's responsibilities describe the duties and expected outcomes assigned to it within the scope of its role. They make the role operational by explaining what the agent is expected to take care of.

### Responsibility versus role, task and authority

- **Role:** Market Investigation Analyst — the general function.
- **Responsibility:** investigate unusual price movements, compare evidence across markets and report findings with their limitations.
- **Task:** compare this week's tomato prices in Jos, Lagos and Kano with the previous week's observations.
- **Authority:** access approved market datasets and prepare an internal report; it may not publish a public alert or commit funds without the required approval.

A responsibility is broader and more enduring than an individual task. Tasks are particular units of work performed in order to fulfil responsibilities.

Authority is different again: being responsible for an outcome does not automatically give an agent permission to take every action that might help achieve it.

### Illustrative example: investigating a tomato price increase

Suppose the system detects a sudden increase in tomato prices across several Nigerian markets.

An agent assigned the role **Market Investigation Analyst** could have these responsibilities:

1. Investigate and describe the observed price movement.
2. Compare prices across relevant locations and time periods.
3. Examine available information that could explain the movement.
4. Distinguish verified evidence from unverified reports and hypotheses.
5. Identify missing, conflicting or outdated information.
6. Present findings, evidence sources and uncertainty clearly.
7. Escalate cases where the evidence is insufficient or the issue exceeds its assigned scope.

Specific tasks might include collecting recent quotations, comparing historical observations, checking transport or supply reports, and preparing an investigation summary.

The agent's responsibility is not to invent an explanation when evidence is unavailable. It should report the gap and uncertainty.

### Characteristics of well-defined responsibilities

A responsibility should make clear:

1. **Scope:** what the agent is expected to handle and what falls outside its remit.
2. **Expected outcome:** what useful result it should produce.
3. **Quality criteria:** required accuracy, completeness, timeliness, provenance or other standards.
4. **Dependencies:** information, access or work from other agents or people on which it depends.
5. **Exceptions and escalation:** what it should do when information is missing, contradictory, unsafe or beyond its authority.
6. **Evidence:** what records or outputs allow the system to assess whether the responsibility was fulfilled.

Responsibilities should be specific enough to assess, but not so fragmented that the system becomes unnecessarily complex.

### Responsibility and accountability

An agent can be assigned operational responsibilities, and its performance can be monitored against them. This does not mean the software itself assumes all organisational, legal or moral accountability.

The people or organisations that design, deploy, operate and authorise a system may retain responsibilities for its use. The exact allocation depends on the context and applicable rules.

### Principles established

- Every role should translate into explicit responsibilities.
- Responsibilities should be clear, bounded, observable and achievable with the agent's assigned authority and available dependencies.
- An agent should report limitations and escalate when it cannot fulfil a responsibility safely or reliably.
- Assigning operational responsibility to an agent does not automatically transfer ultimate organisational or legal accountability to the software.

## 6.4 Agent Authority

### Core question

Which decisions and actions is an agent permitted to make, and under what conditions?

Agent authority defines the scope of decisions, access and actions that the system permits an agent to exercise. It establishes what the agent is authorised to do, rather than merely what it is technically capable of doing.

An agent may be responsible for achieving an outcome without being authorised to take every action that could contribute to that outcome.

### Authority is different from responsibility and capability

- **Responsibility:** what the agent is expected to accomplish.
- **Authority:** what the agent is permitted to decide or do.
- **Capability:** what the agent is technically able to do.

These must be considered separately.

For example, an agent may be technically capable of sending messages because a messaging function is available to it. That does not automatically mean it has permission to contact every person or publish every message.

### Main dimensions of agent authority

A role's authority should make clear:

1. **Decision authority:** which decisions the agent may make independently, such as classifying information, prioritising work or recommending an action.
2. **Data authority:** which information it may read, create, modify, export or delete.
3. **Action authority:** which operations it may perform, such as sending an internal notification, publishing a report or initiating a transaction.
4. **Resource authority:** which resources it may consume or commit, including money, computing capacity, quotas or other assets.
5. **Scope authority:** the permitted subjects, markets, locations, customers or systems within which it may act.
6. **Conditional authority:** the circumstances, thresholds, duration and conditions under which permission applies.
7. **Delegation authority:** whether it may assign work or pass specific permissions to another agent.
8. **Approval and escalation:** which decisions require a human or another authorised entity to approve them.

Not every agent needs every type of authority. Grant only what is relevant to its work.

### Example: authority across agricultural intelligence agents

| Agent | Example of permitted authority | Example of restricted action |
|---|---|---|
| Market Data Collector | Read approved sources and submit collected observations | Delete verified historical records |
| Information Verification Agent | Assess evidence and assign a verification status | Alter the original source or invent missing evidence |
| Market Analyst | Read approved datasets and prepare analysis | Publish a public market warning without approval |
| Opportunity Discovery Agent | Investigate opportunities and prepare recommendations | Commit funds or enter contracts |
| Reporting Agent | Send approved routine internal reports | Issue high-impact public statements without required approval |

These are illustrative allocations, not final production permissions.

### Authority versus autonomy

Authority and autonomy are connected, but they are not the same.

- **Authority** defines the actions and decisions an agent is allowed to perform.
- **Autonomy** describes how independently it can decide and act within the permitted scope.

An agent can have high autonomy within a narrow authority. For example, it might independently collect and organise public price data every day, but have no permission to purchase produce or publish public announcements.

Increasing autonomy should not automatically increase authority.

### The principle of least privilege

Give each agent only the minimum authority necessary to fulfil its assigned responsibilities.

This reduces the consequences of mistakes, compromised access, misunderstood instructions or unexpected behaviour.

Authority should also be:
- Explicit rather than assumed.
- Limited to an appropriate scope.
- Conditional where necessary.
- Revocable when no longer needed.
- Enforced by the surrounding system, not merely requested in an instruction to the AI model.

An agent should not be able to grant itself greater authority simply because it believes doing so would help complete its objective.

### Approval and escalation

Some actions can be permitted automatically, while others should require approval.

For example:
- Reading approved market data may be allowed routinely.
- Preparing an internal report may be allowed independently.
- Publishing a sensitive public alert may require human approval.
- Committing significant funds may require additional authorisation.

The required approval should reflect the action's potential impact, reversibility and risk.

### Principles established

- Responsibility does not automatically confer authority.
- Technical capability does not automatically confer permission.
- Authority must be explicit, scoped and proportionate to the agent's duties.
- Apply least privilege: grant only the authority needed.
- Autonomy and authority must be designed separately.
- High-impact or irreversible actions may require additional approval.
- Agents must not be able to unilaterally expand their own authority.

## 6.5 Agent Boundaries

### Core question

What limits must an agent respect, even when it has the technical capability or some permission to take an action?

Agent boundaries define the limits within which an agent must operate. They clarify what is outside its role or scope, what it must not do, and when it must stop, refuse or escalate rather than continue.

Boundaries help prevent an agent from interpreting a broad objective as permission to do anything that might achieve it.

### Authority and boundaries are related but different

- **Authority** identifies the decisions and actions the system permits an agent to perform.
- **Boundaries** define the limits and constraints that the agent must not cross while performing its work.

They work together. An agent may have permission to read approved market data, but its boundaries may prohibit it from accessing personal financial records, changing original source records or using data outside the assigned project.

A tool being available to an agent does not mean every possible use of that tool is within its boundaries.

### Common categories of boundaries

1. **Role and task boundaries:** the topics, objectives and work the agent is assigned to handle. It should not silently take on unrelated objectives.
2. **Data and privacy boundaries:** which information it may access, disclose, retain, combine or modify, including restrictions on sensitive or confidential information.
3. **Action boundaries:** actions it must not perform, such as making an unauthorised purchase, signing an agreement or publishing an unapproved announcement.
4. **Resource boundaries:** limits on spending, compute, storage, message volume, time or other resources.
5. **Operational and environmental boundaries:** systems, accounts, locations, markets or environments within which it may operate.
6. **Safety and policy boundaries:** prohibited conduct, unsafe requests, required safeguards and rules that take precedence over task completion.
7. **Delegation boundaries:** restrictions on transferring tasks, data or permissions to another agent or external party.
8. **Knowledge and evidence boundaries:** limits on what it may claim. It must distinguish verified information from assumptions, estimates and unknowns rather than presenting uncertainty as fact.
9. **Change boundaries:** restrictions on changing its own instructions, permissions, configuration or operating environment.

These categories are a practical design checklist; not every system needs a separate rule for every category.

### Example: boundaries for the Market Analyst

Suppose a Market Analyst is authorised to examine approved agricultural price records and prepare internal analysis.

Its boundaries could include:

- It must not alter the original collected observations.
- It must not access data outside its assigned sources and project scope.
- It must not expose private or confidential information in its report.
- It must not present unverified market rumours as established facts.
- It must not publish a public warning or contact external buyers unless separately authorised.
- It must not commit money or enter commercial agreements.
- It must not change its own access permissions.
- If evidence is contradictory or insufficient, it must state the uncertainty and request further verification rather than inventing a conclusion.

The boundaries help keep the agent's behaviour aligned with its assigned role, responsibility and authority.

### Hard boundaries and behavioural guidance

It is useful to distinguish between two ways of expressing constraints:

- **Enforced boundaries:** restrictions implemented in the surrounding system, such as access controls, spending limits, approval gates, data permissions and blocked operations.
- **Behavioural boundaries:** instructions and policies that guide how the model should behave, such as staying on topic, explaining uncertainty or escalating a difficult case.

Behavioural instructions are useful but should not be treated as a substitute for technical enforcement where the consequences are significant. High-impact restrictions should be enforced outside the model wherever practical.

### What should happen when a boundary is reached?

An agent should not simply continue because it is under pressure to complete its objective.

A suitable response may be to:

1. Stop the restricted action.
2. Preserve the relevant task state and evidence.
3. Explain which boundary or uncertainty prevents it from proceeding.
4. Escalate to the appropriate human or authorised agent when needed.
5. Resume only when the required permission, information or decision is available.

For ambiguous or high-impact cases, the system should be designed to fail safely rather than assume permission.

### Boundaries must be tested

A boundary written in a document is not proof that the system will respect it.

Engineering should test whether an agent can:
- Access information outside its assigned scope.
- Perform an action it is not authorised to perform.
- Reveal information it should protect.
- Continue when required approval is missing.
- Ignore a restriction after receiving conflicting or manipulative instructions.
- Delegate a prohibited action to another agent.
- Modify its own instructions or permissions without authorisation.

The tests should verify the actual system behaviour and enforcement, not merely whether the agent says it understands the rule.

### Principles established

- Every agent should have explicit boundaries appropriate to its role, responsibilities and authority.
- A broad objective does not authorise an agent to cross its boundaries.
- Tool availability is not the same as permission to use every capability.
- Important restrictions should be enforced by the surrounding system, not only by model instructions.
- Agents should stop, explain and escalate when they reach a boundary they cannot safely resolve.
- Boundaries should be tested and reviewed as the system changes.

## Remaining subsections

- **6.5 Agent Boundaries** — what an agent must not do or exceed.
- **6.6 Agent Relationships** — which other agents it can communicate or collaborate with.
- **6.7 Agent Accountability** — how its actions and performance are traced, assessed and governed.

Continue with 6.5 Agent Boundaries. Do not treat the remaining subsection headings as lessons already covered.
