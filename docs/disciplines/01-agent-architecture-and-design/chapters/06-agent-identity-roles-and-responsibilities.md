# Chapter 6 — Agent Identity, Roles and Responsibilities

**Status:** Covered

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

## 6.6 Agent Relationships

### Core question

How does an agent interact with, depend on and cooperate with other agents inside a larger system?

An agent relationship defines how agents exchange information, request or assign work, coordinate activities, depend on one another and handle shared objectives.

An agent does not need to operate in isolation. Many useful systems consist of specialised agents whose work must be connected.

### Why relationships matter

Consider our agricultural intelligence system. A Market Data Collector gathers observations, an Information Verification Agent checks their quality, a Market Analyst interprets the verified information, an Opportunity Discovery Agent identifies possible commercial opportunities, and a Reporting Agent prepares approved outputs.

Each agent has its own identity, role, responsibilities, authority and boundaries. But the overall system only works when their activities are coordinated.

The relationship design answers questions such as:
- Which agent can send information to which other agent?
- Which agent can request work from another?
- Which agent depends on another agent's output?
- Who coordinates a multi-step task?
- What information may be shared?
- What happens when an agent is unavailable or returns an incomplete result?

### Common types of agent relationships

1. **Peer relationship:** agents cooperate as counterparts. Neither necessarily controls the other. They may exchange findings or coordinate work.
2. **Producer–consumer relationship:** one agent produces information or an output that another agent uses. The receiving agent should know the source and status of that output.
3. **Delegation relationship:** one agent assigns a task to another within the delegating agent's permitted authority. Delegation does not automatically transfer unlimited authority or remove the delegating agent's obligation to check the result.
4. **Coordinator–worker relationship:** a coordinator breaks a larger objective into tasks, distributes them and gathers results from specialised agents. Coordination does not mean the coordinator should have unrestricted authority over every worker.
5. **Supervisory or approval relationship:** one agent or authorised human reviews a proposed action, checks compliance or approves a decision before it proceeds.
6. **Dependency relationship:** one agent's work cannot safely or usefully continue until it receives a required input, decision or result from another agent.

One agent may have several kinds of relationships with different agents. These categories describe interaction patterns, not fixed identities or ranks.

### Example: relationships in the agricultural intelligence system

| From | To | Relationship | Information or work exchanged |
|---|---|---|---|
| Market Data Collector | Information Verification Agent | Producer–consumer | Raw price observations and source details |
| Information Verification Agent | Market Analyst | Producer–consumer | Verified, rejected or uncertain observations |
| Market Analyst | Opportunity Discovery Agent | Peer / producer–consumer | Market analysis and identified trends |
| Opportunity Discovery Agent | Reporting Agent | Producer–consumer | Opportunity assessments and supporting evidence |
| Coordinator | Specialised agents | Coordinator–worker | Task assignments, status requests and collected results |
| Authorised reviewer | Reporting Agent | Supervisory / approval | Approval or rejection of sensitive reports |

This is an illustrative arrangement, not a final implementation architecture. Actual relationships should be determined by the system's objectives, risks, scale and workflow.

### Communication is not the same as authority

An agent being able to communicate with another agent does not mean it can control that agent.

For example:
- An analyst may request additional price data from a collector.
- A collector may respond with available observations or explain a limitation.
- The analyst cannot automatically change the collector's permissions or assign it unrelated work.
- A coordinator may distribute approved tasks, but cannot grant workers permissions it does not possess.

Keep communication rights, task-assignment rights, decision authority and permission-management authority distinct.

### Common communication patterns

Agents can interact through several broad patterns:

- **Direct communication:** one agent sends a request or message to another identified agent.
- **Shared workspace:** agents contribute to and retrieve information from a shared task record or knowledge space, subject to access rules.
- **Publish and subscribe:** an agent publishes an event or update, and interested authorised agents receive it.
- **Orchestrated communication:** a coordinator routes tasks and responses among specialised agents.
- **Hierarchical communication:** requests and results move through defined levels of responsibility or supervision.

A system can combine these patterns. The right arrangement depends on coordination needs, independence, reliability and complexity. No particular platform or communication technology is required by this conceptual lesson.

### Relationship contracts and message clarity

A dependable agent relationship needs an agreed understanding of what is exchanged.

For a task request or result, the system may need to specify:
- The sender and intended recipient.
- The task or purpose.
- The input information and its source.
- The expected output and format.
- The relevant deadline or priority.
- The status of the work.
- Any restrictions on use or disclosure.
- Errors, uncertainty or missing information.
- Whether a response, acknowledgement or approval is required.

This is a communication contract: an agreed expectation for interaction. It helps prevent one agent from assuming that another has received, understood or completed a request when that has not been established.

### Information sharing and trust

Agents should share only information needed for the receiving agent's authorised task.

A receiving agent should be able to distinguish:
- Original observations from derived analysis.
- Verified information from unverified reports.
- Facts from assumptions or predictions.
- Current information from stale information.
- Complete results from partial results.

Preserve useful source and provenance details when information moves between agents. Otherwise, later agents may treat an unverified statement as established fact simply because it came from another agent.

An agent's message is not automatically trustworthy merely because another agent sent it. Important information may need independent verification.

### Dependencies, failures and coordination

Agent relationships create dependencies. If one agent is delayed, unavailable, produces an incomplete result or returns conflicting information, other agents may be affected.

A relationship design should specify how the system handles:
1. Missing or delayed responses.
2. Failed or incomplete tasks.
3. Duplicate or repeated messages.
4. Conflicting results from different agents.
5. Changed requirements or cancelled tasks.
6. An agent becoming unavailable during a task.
7. Escalation when the agents cannot resolve a problem.

The system may wait, retry where safe, request clarification, use an approved alternative, pause dependent work or escalate to a human. It should not silently treat a missing response as a successful result.

### Avoid unnecessary agent-to-agent communication

More communication does not automatically produce better intelligence.

Excessive connections can create:
- Repeated or contradictory instructions.
- Unnecessary message traffic and cost.
- Confusion about which agent owns a task.
- Circular delegation or repeated work.
- Unclear information provenance.
- Difficulties tracing decisions and errors.

Create relationships because a task, dependency or control requires them. Define who initiates communication, what is exchanged and who is responsible for the next step.

### Principles established

- Agents should have explicit, purpose-driven relationships.
- Communication, delegation, coordination, supervision and authority are different concepts.
- Delegation does not automatically transfer unlimited authority.
- Share only information needed for an authorised task, preserving relevant provenance and uncertainty.
- A message from another agent is not automatically verified evidence.
- Define how dependencies, delays, failures and conflicts are handled.
- Avoid unnecessary connections and unclear ownership of work.

## 6.7 Agent Accountability

### Core question

How can a system establish what an agent did, what it was expected to do, whether it acted within its authority and boundaries, and who must review or address the consequences?

Agent accountability is the ability to trace, assess and respond to an agent's actions and outputs against its assigned role, responsibilities, permissions, rules and expected standards.

It makes agent behaviour reviewable. Without accountability mechanisms, it may be difficult to identify why an action occurred, which component was involved, whether approval was obtained or how a failure should be corrected.

### Agent accountability is not the same as making software legally responsible

An agent can be assigned operational responsibilities and its behaviour can be evaluated. That does not automatically make the software itself the legal or organisational bearer of ultimate responsibility.

Accountability arrangements should identify the relevant people and organisations that design, deploy, authorise, supervise and operate the system. Their responsibilities depend on the system, its use and applicable rules.

The engineering objective is to make actions attributable and reviewable, and to ensure there is a defined process for human or organisational oversight and remediation.

### What should be traceable?

For a consequential task or action, the system should retain enough reliable evidence to reconstruct what happened.

Depending on the risk and purpose, this may include:

1. **Agent identity:** which agent or service performed the action.
2. **Configuration and version:** the relevant agent configuration, model or component version, and applicable policy version.
3. **Task origin:** who or what initiated the task, and the objective or request provided.
4. **Assigned role and authority:** the role, responsibility, permission and boundary rules applicable at the time.
5. **Inputs and sources:** information used, its origin, timestamp and verification status, subject to privacy and data-minimisation requirements.
6. **Actions and tool calls:** what operations were requested or performed, which external systems were involved, and whether they succeeded.
7. **Decisions and approvals:** significant decision summaries, policy checks, approval requests, approver identity and approval or rejection outcome.
8. **Outputs and handoffs:** what was produced, who or what received it, and whether another agent continued the task.
9. **Outcome:** whether the objective was achieved, partially achieved, rejected, cancelled or left unresolved.
10. **Exceptions and incidents:** errors, boundary violations, overrides, retries, escalations and corrective actions.

Not every low-risk operation needs a detailed record of every internal event. The level of logging should be proportionate to the consequences, regulatory needs, privacy constraints and operational requirements.

### A traceable multi-agent task

Suppose the agricultural intelligence system detects an unusual increase in tomato prices.

A traceable task history might show:

1. A monitoring process created a task to investigate the price movement.
2. The Market Data Collector submitted observations with source and collection details.
3. The Information Verification Agent recorded which observations were verified, rejected or unresolved.
4. The Market Analyst produced an analysis based on the available evidence.
5. The Opportunity Discovery Agent identified a possible commercial opportunity and recorded its assumptions.
6. The Reporting Agent prepared a report.
7. An authorised reviewer approved or rejected publication.
8. The system recorded the final publication status and any follow-up.

This history helps reviewers understand the sequence, the participating agents, the evidence used and the approvals obtained.

It should be possible to distinguish an agent's own actions from information it received from another agent. A task or correlation identifier can help connect related events across the workflow.

### Logging, monitoring and audit

These concepts are related but different:

- **Logging:** recording relevant events, actions, errors and state changes.
- **Monitoring:** observing ongoing system activity and checking whether it is operating as expected.
- **Audit:** examining recorded evidence and decisions to assess compliance, performance or an incident.
- **Evaluation:** systematically testing or measuring whether an agent performs its assigned tasks to the required standard.

Logs provide evidence for monitoring and audit, but a log by itself does not prove that an action was correct or that the record is complete and truthful.

Monitoring can identify a problem as it happens. An audit may examine the incident afterward and establish what needs to change.

### Decision records and model reasoning

For important decisions, the system should capture an understandable summary of the decision, relevant evidence, applicable rules, uncertainty and outcome.

Accountability does not require storing every private internal reasoning token or hidden chain-of-thought of a model. A concise decision record, source references, policy checks, tool events and final outcome can provide useful review evidence without treating private internal reasoning as an audit log.

The record should help answer: what decision was made, on what relevant evidence and under which authority?

### Measuring whether responsibilities were fulfilled

Accountability also requires comparing actual performance with defined expectations.

Examples for the agricultural intelligence system include:

| Agent | Possible accountability evidence |
|---|---|
| Market Data Collector | Source coverage, timestamps, completeness, duplicates and correction rates |
| Information Verification Agent | Verification outcomes, evidence quality, unresolved conflicts and false acceptance or rejection findings |
| Market Analyst | Accuracy of calculations, source traceability, treatment of uncertainty and quality of analysis |
| Opportunity Discovery Agent | Evidence supporting opportunities, assumptions, risk disclosures and usefulness of recommendations |
| Reporting Agent | Correct recipients, approved content, delivery status and publication approvals |

These are possible measures, not universal metrics. Measures should reflect each role and should not reward an agent for speed or volume at the expense of accuracy, safety or evidence quality.

### What happens when an agent fails?

Accountability must lead to a response, not merely record the failure.

A suitable incident process may include:

1. Detect and record the incident.
2. Contain the immediate risk, including pausing affected actions where necessary.
3. Preserve relevant evidence and task history.
4. Establish which agents, components, permissions and decisions were involved.
5. Assess impact and notify the appropriate people.
6. Correct the output or reverse an action where possible and authorised.
7. Identify the underlying cause.
8. Update policies, permissions, instructions, tests or operating procedures as appropriate.
9. Verify that the corrective action has worked.

The response should distinguish a model error, bad input data, a permission-control failure, an orchestration defect, a human approval failure and an external service failure. Different causes require different remedies.

### Accountability in multi-agent systems

When several agents contribute to one result, accountability must not disappear between handoffs.

The system should preserve:
- Which agent received each task.
- Which agent produced each intermediate result.
- Which information and source details were passed along.
- Which agent made or recommended a consequential decision.
- Which human or system approved an action.
- Which agent or component executed the final operation.

Delegation should be traceable. An agent that delegates work should not assume the work is complete merely because it sent a request. The system should record the result, check it against the task requirements and escalate unresolved failures.

### Privacy and record integrity

Accountability records can contain sensitive information. They should be protected against unauthorised access and alteration, and retained only for a justified period.

A sound design considers:
- Access restrictions for logs and audit records.
- Data minimisation and appropriate redaction.
- Retention and deletion requirements.
- Time consistency and reliable event ordering.
- Protection against unauthorised modification.
- Separation of operational logs from sensitive content where appropriate.
- The ability to export or review records when needed.

More logging is not automatically better. Collect information that serves a defined accountability, safety, reliability or operational purpose.

### Principles established

- Agent actions and consequential outputs should be attributable and reviewable.
- Accountability records should connect identity, task, configuration, authority, inputs, actions, approvals, outputs, handoffs and outcomes where relevant.
- Logging, monitoring, auditing and evaluation serve different purposes.
- Important decisions need understandable evidence and decision summaries, not necessarily hidden internal reasoning traces.
- Multi-agent handoffs and delegation must remain traceable.
- Failures should trigger containment, investigation, correction and verification.
- Accountability records must be protected and proportionate to privacy and retention requirements.
- Operational responsibilities assigned to agents do not automatically make software the ultimate legal or organisational accountable party.

## Chapter 6 completion

Chapter 6 has covered all seven elements needed to define and organise agents within a larger system:

1. Agent Identity
2. Agent Roles
3. Agent Responsibilities
4. Agent Authority
5. Agent Boundaries
6. Agent Relationships
7. Agent Accountability

The next planned chapter is **Chapter 7 — Agent Configuration and Lifecycle**. Its detailed lessons have not yet been covered.
