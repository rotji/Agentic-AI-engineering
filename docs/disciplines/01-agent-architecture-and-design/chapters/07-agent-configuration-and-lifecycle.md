# Chapter 7 — Agent Configuration and Lifecycle

**Status:** In progress.

## Purpose

Study how an agent is configured before and during operation, how it moves through its lifecycle, and how changes to its configuration or operating state are managed.

This chapter builds on Chapter 6, which established an agent's identity, role, responsibilities, authority, boundaries, relationships and accountability.

## Learning scope

The chapter is being taught progressively. Subsections marked as planned have not yet been covered:

1. **7.1 Agent Configuration:** Covered.
2. **7.2 Configuration Elements:** Covered.
3. **7.3 Initialization and Startup:** what must be checked or prepared before an agent begins work.
4. **7.4 Agent Lifecycle and States:** creation, configuration, initialization, ready, running, paused, failed, recovery, shutdown and retirement.
5. **7.5 Configuration and Version Changes:** how approved changes are introduced, tracked, tested and rolled back.
6. **7.6 Lifecycle Management and Continuity:** how agents are suspended, resumed, replaced or retired without losing necessary task history and accountability.

## 7.1 Agent Configuration

### Core question

What settings and instructions define how a particular agent is prepared to operate in its assigned environment?

Agent configuration is the collection of settings, instructions and references that determine how an agent is set up to perform its work. It describes how the agent is intended to operate for a particular purpose and environment.

Configuration is broader than a single system prompt. It may include the agent's objective, operating instructions, selected model, context sources, assigned capabilities, output expectations, limits, schedules and references to applicable policies.

The exact configuration depends on the agent's function. Not every agent needs every possible setting.

### Configuration is not identity

Identity answers: **Which agent is this?**

Configuration answers: **How is this agent set up to operate?**

For example, AGENT-001 may remain the Market Data Collector even when its permitted market coverage, schedule or output format is changed.

A configuration can be revised or versioned without necessarily creating a new agent identity. Systems should nevertheless be able to record which configuration version was active when an important task was performed.

### Configuration is not role

Role answers: **What function does the agent perform?**

Configuration answers: **How is that function set up in this particular operating situation?**

Two agents may share the same role but have different configurations. For example, two Market Data Collectors may cover different LGAs, use different approved sources or operate on different collection schedules.

The role gives them the same general function; their configurations tailor their operation.

### Configuration is not authority

Authority answers: **What is the agent permitted to decide or do?**

Configuration may contain or refer to the policies and permission settings relevant to an agent, but a configuration value or model instruction should not by itself grant unrestricted access.

Actual permissions and approval requirements should be enforced by the surrounding system. Changing an ordinary configuration must not silently bypass the authority and boundaries established for the agent.

### Configuration is not runtime state

Runtime state answers: **What is happening with the agent right now?**

Configuration usually describes the intended operating setup. Runtime state describes the current, changing condition of the agent while it is executing.

For example:

| Configuration | Runtime state |
|---|---|
| Assigned market coverage: Jos North | Currently collecting data from one approved source |
| Collection schedule: daily | Last collection completed at 10:15 |
| Expected output: structured price observations | 27 observations collected so far |
| Maximum task duration: 15 minutes | 6 minutes elapsed |
| Use approved source list | Current source request is pending |

Configuration may define initial values or operating limits, while runtime state changes as the task progresses.

### Example: configuring a Market Data Collector

Consider AGENT-001, whose role is Market Data Collector.

Its configuration might specify:

- **Purpose:** collect agricultural market price observations.
- **Geographic scope:** selected markets in Jos North.
- **Product coverage:** approved commodities in its assigned catalogue.
- **Sources:** the sources it is configured to consult.
- **Schedule:** when collection should run.
- **Collection instructions:** what information to capture from each observation.
- **Output expectations:** required fields, units and format.
- **Operating limits:** time, request and resource limits.
- **Policy references:** the applicable access, privacy, verification and escalation rules.

Its runtime state at a particular moment might show which market it is currently processing, which sources have responded, the number of observations collected and whether the task is running, paused or failed.

This is a conceptual example, not a final implementation configuration.

### Why configuration should be explicit and managed

If configuration is scattered across prompts, code, external files and informal instructions without a clear record, it becomes difficult to establish how an agent was supposed to operate.

A managed configuration should therefore be:

1. **Explicit:** important settings should be identifiable rather than hidden in assumptions.
2. **Purpose-aligned:** settings should support the agent's assigned role and responsibilities.
3. **Controlled:** changes should follow the appropriate approval and permission rules.
4. **Versioned:** the system should be able to identify which configuration version was active for a task.
5. **Environment-aware:** settings should match the environment in which the agent is expected to operate.
6. **Reviewable:** authorised people should be able to inspect relevant settings and understand their purpose.

Configuration should not become a place to duplicate every policy or permission. Where possible, it should reference the appropriate controlled rules rather than create conflicting copies.

### Configuration can affect behaviour without changing identity

Changing an agent's configuration can change how it operates. For example, changing its assigned market coverage or collection schedule may produce different outputs while the agent remains the same logical agent.

This is why configuration changes need care. A change should be understandable, authorised where required and traceable to the tasks performed under it.

The detailed contents of configuration, how it is loaded at startup, and how it is changed safely will be examined in the next subsections.

### Principles established

- Configuration describes how an agent is set up to operate.
- Configuration is distinct from identity, role, authority and runtime state.
- Agents with the same role may have different configurations.
- Configuration may refer to permissions and policies, but must not silently override enforced authority or boundaries.
- Important configuration should be explicit, controlled, versioned and reviewable.
- Configuration changes may alter behaviour without necessarily changing agent identity.


## 7.2 Configuration Elements

### Core question

What individual elements make up an agent's configuration, and what does each one control?

An agent configuration is not one single instruction. It is a structured collection of related settings. The exact elements depend on the agent's purpose, risk, operating environment and required capabilities. There is no single universal configuration format that every agent must use.

### 1. Objective and scope

Defines what the agent is intended to achieve and the area within which it should operate.

Examples:
- Objective: collect agricultural market price observations.
- Geographic scope: selected markets in Jos North.
- Subject scope: specified commodities in the approved catalogue.
- Exclusions: markets or products outside its assignment.

The objective gives direction; the scope prevents the agent from interpreting that objective too broadly.

### 2. Instructions and operating policies

Defines how the agent should approach its work.

This may include:
- Role-specific operating instructions.
- Procedures for collecting or analysing information.
- Evidence and source-handling rules.
- Requirements to state uncertainty.
- Escalation instructions.
- References to applicable safety, privacy and organisational policies.

Instructions guide behaviour. Important permissions and prohibitions still need enforcement by the surrounding system; text instructions alone do not create secure access controls.

### 3. Model and model behaviour settings

Where the agent uses a configurable AI model, its configuration may identify the model and set relevant behaviour parameters.

Examples include:
- Which model or model class is assigned.
- Response-format requirements.
- Context or output limits.
- Sampling or generation settings, where supported.
- Fallback behaviour if a model is unavailable, where a fallback is approved.

Different agents may use different models or settings. Selecting a model is one configuration decision, not the entire agent configuration.

### 4. Context and knowledge sources

Defines which information the agent should use or consult for its task.

Examples:
- Approved datasets.
- Reference documents.
- Product catalogues.
- Market or geographic reference lists.
- Knowledge bases.
- Relevant previous task information.

The configuration should identify the intended sources and any relevant access restrictions. The agent should still distinguish the source material from its own interpretation and check whether information is current enough for the task.

### 5. Capabilities and tool access

Defines which capabilities the agent has been assigned for its work.

Examples:
- Read an approved dataset.
- Submit a collected observation.
- Search a designated information source.
- Prepare a report.
- Send an internal notification.

A capability being listed in configuration does not necessarily mean the agent may use it in every situation. Actual access must remain consistent with its authority, boundaries and the system's enforcement controls.

This subsection identifies the capability category only. Specific tools and platforms will be examined when the learning or a concrete system requirement makes them necessary.

### 6. Permissions and policy references

Identifies the permission rules and policies that govern operation.

Examples:
- Which data sources are accessible.
- Whether the agent may create or update records.
- Whether external communication is permitted.
- Which actions require human approval.
- Which resource or spending limits apply.

Configuration may reference a centrally managed permission policy rather than copying all permission rules into each agent's own settings. This helps avoid conflicting or outdated copies.

The effective permission must be enforced outside the model. Changing an instruction or ordinary setting must not silently expand the agent's authority.

### 7. Input and output specifications

Defines what information the agent is expected to receive and what form its results should take.

Input specifications may identify:
- Required fields.
- Accepted data types and units.
- Source and timestamp requirements.
- Optional fields.
- Validation rules.

Output specifications may identify:
- Required result fields.
- Expected structure or format.
- Required evidence references.
- Status values, such as verified, unverified, incomplete or rejected.
- How errors and uncertainty should be represented.

For example, a price observation may require commodity, market, location, price, unit, observation date, source and verification status. A receiving agent can then interpret the output consistently.

### 8. Operating parameters and resource limits

Defines operational constraints for a task or agent.

Examples:
- Maximum task duration.
- Maximum number of records to process at once.
- Request or retry limits.
- Context and output limits.
- Computing or storage limits.
- Approved budget or spending threshold, where relevant.

These settings help prevent runaway execution and uncontrolled resource use. A limit in configuration should be backed by enforcement mechanisms wherever its consequences matter.

### 9. Schedule and activation conditions

Defines when or under what conditions the agent should begin work.

Examples:
- Run at a specified time.
- Run once per day.
- Start when a new dataset arrives.
- Start when an authorised user submits a task.
- Start when an approved event or threshold is detected.

A schedule defines when work should be triggered. It is not the same as runtime state, which records whether the agent is currently waiting, running or has completed a task.

### 10. Environment and integration settings

Defines environment-specific information needed for the agent to operate in its intended setting.

Examples:
- The relevant deployment environment.
- Approved service addresses or integration references.
- Locale, time zone or regional conventions.
- Environment-specific data locations.
- Non-secret connection settings.

Sensitive credentials, passwords and private keys should not be written directly into ordinary configuration files or exposed in prompts and logs. Configuration should refer to an appropriately protected secret or credential mechanism, and access should be limited to what the agent requires.

### 11. Exception, recovery and escalation settings

Defines how the agent should respond when normal operation is not possible.

Examples:
- What to do when a source is unavailable.
- How many safe retries are allowed.
- When to mark a task incomplete.
- When to stop and request human assistance.
- Which conditions require escalation.
- Whether an approved alternative source or process may be used.

These settings help prevent an agent from fabricating results or continuing beyond its authority simply because it has not completed its objective.

### 12. Observability and record settings

Defines what operational evidence the system should record or make available for review.

Examples:
- Task and correlation identifiers.
- Required event records.
- Error and escalation records.
- Output references.
- Configuration version used.
- Operational status reporting.

The amount recorded should be proportionate to risk and purpose. Avoid collecting unnecessary personal, confidential or sensitive information.

### Putting the elements together: Market Data Collector

The following is an illustrative configuration profile, not a universal template or production specification.

| Configuration element | Example setting |
|---|---|
| Objective and scope | Collect prices for approved commodities in selected Jos North markets |
| Instructions and policies | Record source, date, unit and uncertainty; do not invent missing values |
| Model settings | Use the model assigned for structured extraction and classification |
| Context and knowledge | Approved market list and commodity catalogue |
| Capabilities | Read approved sources and submit observations |
| Permissions | No permission to delete verified historical records |
| Input/output | Produce structured observations with provenance |
| Operating limits | Task duration and request limits |
| Schedule | Daily collection window |
| Environment | Approved data destination and regional time settings |
| Exception handling | Mark unavailable sources and escalate repeated failures |
| Observability | Record task ID, configuration version, source, status and errors |

### Configuration elements are related, not independent

A setting in one area can affect another.

For example:
- The geographic scope affects which sources are relevant.
- The output specification affects what information must be collected.
- The permissions determine which configured capabilities can actually be used.
- Resource limits may constrain how much work can be completed during a scheduled run.
- Exception settings determine what happens when a required source is missing.

The configuration should therefore be internally consistent. A system should detect conflicts such as an output requiring information that the agent is not authorised or able to access.

### A practical configuration review

Before an agent is activated or a configuration change is accepted, reviewers should be able to ask:

1. Does the objective match the assigned role and responsibilities?
2. Are the scope and exclusions clear?
3. Are the required sources appropriate and accessible?
4. Are the assigned capabilities consistent with the agent's authority and boundaries?
5. Are input and output requirements clear enough for other components to use?
6. Are operating limits and activation conditions reasonable?
7. Are credentials and sensitive settings protected?
8. Are error handling, escalation and record requirements defined?
9. Can the active configuration version be identified later?

### Principles established

- Agent configuration consists of multiple related elements, not just a prompt.
- The elements should be selected according to the agent's purpose and risk; not every agent needs every setting.
- Objective, scope, instructions, model settings, context, capabilities, permissions, inputs, outputs, limits, triggers, environment, exceptions and observability may all be relevant.
- Configured capabilities must remain consistent with enforced permissions and boundaries.
- Sensitive credentials must be protected and should not be exposed in ordinary configuration or prompts.
- Configuration elements must be internally consistent and reviewable.
- There is no single mandatory configuration format for every agent.


No particular implementation technology or framework is assumed.
