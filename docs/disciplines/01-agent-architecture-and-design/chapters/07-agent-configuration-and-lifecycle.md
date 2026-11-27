# Chapter 7 — Agent Configuration and Lifecycle

**Status:** In progress.

## Purpose

Study how an agent is configured before and during operation, how it moves through its lifecycle, and how changes to its configuration or operating state are managed.

This chapter builds on Chapter 6, which established an agent's identity, role, responsibilities, authority, boundaries, relationships and accountability.

## Learning scope

The chapter is being taught progressively. Subsections marked as planned have not yet been covered:

1. **7.1 Agent Configuration:** Covered.
2. **7.2 Configuration Elements:** objectives, instructions, operating parameters, permissions references, assigned capabilities and environment-specific settings.
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


No particular implementation technology or framework is assumed.
