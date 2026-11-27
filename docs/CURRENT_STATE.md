# Current State

## Project
Agentic AI Engineering

## Curriculum
13 disciplines. See [Curriculum](CURRICULUM.md).

## Active learning position

- **Discipline:** 1 — Agent Architecture and Design
- **Chapter:** 6 — Agent Identity, Roles and Responsibilities
- **Completed chapter coverage:** Chapters 1–5
- **Chapter 6 status:** Covered (subsections 6.1–6.7)
- **Current chapter:** 7 — Agent Configuration and Lifecycle
- **Covered subsections:** 7.1 Agent Configuration; 7.2 Configuration Elements; 7.3 Initialization and Startup; 7.4 Agent Lifecycle and States
- **Next subsection:** 7.5 — Configuration and Version Changes

## Completed chapter coverage

1. **Understanding Agent Architecture:** an agent is a goal-directed system that uses an AI model to observe, decide, interact with an environment and evaluate results.
2. **Basic Architecture of an Agent:** objective, model, context, memory, tools, state, execution environment, observation and feedback.
3. **Core Concepts Within Agent Architecture:** introduced architecture, harness engineering, runtime, goal architecture, state management, identity, configuration, lifecycle, boundaries and capability architecture.
4. **Agent vs Chatbot vs Workflow vs Automation vs Autonomous System:** distinguished these concepts and noted that they can overlap or be combined.
5. **Autonomy Levels and the Autonomy Spectrum:** introduced a five-level teaching framework and the principle that autonomy should be differentiated by responsibility, reliability and potential consequences.

## Chapter 6 progress

### 6.1 Agent Identity

An agent needs a distinguishable identity. Its identity is separate from the model powering it. Multiple agents can use the same model while retaining different identities, roles, configurations, permissions and memory. A model may also change without necessarily changing the agent's identity.

Principle: every agent should have a clearly identifiable identity independent of the model powering it.

### 6.2 Agent Roles

A role defines the function an agent performs in a system. Identity distinguishes the agent; role explains its function. Role, responsibility, task and authority are different concepts. One agent may perform multiple roles, and multiple agents may share a role, provided the design remains clear and justified.

### 6.3 Agent Responsibilities

Responsibilities define the duties and expected outcomes an agent is expected to handle within its role. They are broader than individual tasks and are distinct from authority to act.

A well-defined responsibility identifies scope, expected outcomes, quality criteria, dependencies, exceptions and escalation, and supporting evidence. Agents should report limitations rather than fabricate results or act beyond their authority. Assigning operational responsibility to an agent does not automatically transfer ultimate organisational or legal accountability to the software.

### 6.4 Agent Authority

Authority defines which decisions, data access and actions an agent is permitted to exercise, and under what conditions. It is distinct from responsibility (what the agent is expected to accomplish) and capability (what it is technically able to do).

Authority can cover decision-making, data access and modification, external actions, resource use, operational scope, conditional permissions, delegation, and approval or escalation requirements.

The agricultural intelligence example illustrated that different agents should receive different permissions. A market data collector may submit observations but not delete verified history; an analyst may prepare reports but not publish high-impact public alerts without approval.

Authority and autonomy are separate: authority defines the permitted scope, while autonomy describes how independently the agent acts inside that scope. An agent can have high autonomy within narrow authority.

Principles: apply least privilege; make authority explicit, scoped, proportionate and revocable; enforce permissions through the surrounding system rather than relying only on model instructions; do not allow an agent to expand its own authority; require additional approval for actions whose impact or irreversibility warrants it.



### 6.5 Agent Boundaries

Boundaries define the limits an agent must respect, including limits on its role, data, actions, resources, operating environment, safety, delegation, evidence claims and self-modification.

Authority identifies what the system permits; boundaries define constraints the agent must not cross while operating within that permission. A tool being available does not mean every use is permitted.

Important restrictions should be enforced by the surrounding system wherever practical, rather than relying only on model instructions. When a boundary or unresolved uncertainty prevents safe completion, the agent should stop, explain and escalate.

Boundary testing should check whether the agent can access out-of-scope data, perform prohibited actions, disclose protected information, bypass approval, follow manipulative instructions, delegate prohibited work or alter its own permissions.

Principles: define explicit boundaries; enforce high-impact restrictions outside the model where practical; stop and escalate when necessary; test boundaries as the system changes.



### 6.6 Agent Relationships

Agent relationships define how agents exchange information, request or delegate work, coordinate activities and depend on one another. Common patterns include peer, producer–consumer, delegation, coordinator–worker, supervisory and dependency relationships.

Communication does not automatically confer authority. An agent may be able to contact another without being allowed to control it, change its permissions or assign unrelated work.

Communication patterns may include direct messages, shared workspaces, publish-and-subscribe arrangements, orchestrated routing and hierarchical communication. A system may combine patterns according to its requirements.

Reliable interactions need clear expectations for sender, recipient, task, inputs, expected outputs, deadlines or priorities, status, restrictions, errors and acknowledgement. Information should retain relevant provenance and uncertainty; a message from another agent is not automatically verified evidence.

Relationships also create dependencies. The system should define how it handles missing or delayed responses, incomplete work, duplicate messages, conflicting results, cancelled tasks and unavailable agents. It should not silently treat a missing response as successful completion.

Principles: make relationships explicit and purpose-driven; distinguish communication, delegation, coordination, supervision and authority; share only information needed for an authorised task; preserve provenance; define failure and escalation handling; avoid unnecessary connections and unclear task ownership.



### 6.7 Agent Accountability

Agent accountability means that agent actions and outputs can be traced, assessed and addressed against assigned responsibilities, authority, boundaries and expected standards. It makes behaviour reviewable, but does not automatically make software the ultimate legal or organisational bearer of responsibility.

For consequential work, appropriate records may connect agent identity, configuration and policy version, task origin, assigned role and authority, input sources, actions and tool calls, decision summaries, approvals, outputs, handoffs, outcomes, exceptions and incidents. The level of detail should be proportionate to risk, privacy and operational needs.

Logging records events; monitoring observes ongoing operation; auditing examines evidence; evaluation measures performance. Logs alone do not prove correctness or completeness. Decision records should capture relevant evidence, rules, uncertainty and outcomes without requiring storage of hidden model chain-of-thought.

Multi-agent delegation and handoffs should remain traceable so that task ownership and intermediate results do not disappear. When failures occur, the system should record and contain the incident, preserve evidence, identify affected components and approvals, correct the outcome where possible, investigate the cause and verify corrective action.

Accountability records should be access-controlled, protected against unauthorised alteration and retained only as justified. Measures should reflect each role and not reward speed or volume at the expense of accuracy, safety or evidence quality.

Principles: make consequential actions attributable and reviewable; preserve important handoffs and approvals; distinguish logging, monitoring, auditing and evaluation; respond to failures through containment, investigation, correction and verification; protect records; do not mistake operational agent responsibility for ultimate legal or organisational accountability.



## Chapter 7 progress

### 7.1 Agent Configuration

Agent configuration is the collection of settings, instructions and references that define how an agent is prepared to operate in a particular purpose and environment. It is broader than a system prompt and may include objectives, model settings, context sources, assigned capabilities, output expectations, schedules, limits and policy references.

Configuration is distinct from:
- **Identity:** which agent this is.
- **Role:** what function it performs.
- **Authority:** what it is permitted to do.
- **Runtime state:** what is happening with it at the current moment.

Two agents with the same role may have different configurations. A configuration change can alter behaviour without necessarily changing the agent's identity. Configuration should be explicit, controlled, versioned and reviewable, and must not silently override enforced permissions or boundaries.

The agricultural Market Data Collector example illustrated configuration settings such as market coverage, product scope, approved sources, collection schedule, required output fields and operating limits, contrasted with changing runtime information such as current task, progress and pending requests.



### 7.2 Configuration Elements

An agent configuration is a set of related elements, not one prompt. Depending on purpose and risk, it may cover objective and scope; instructions and policies; model settings; context and knowledge sources; assigned capabilities; permission and policy references; input and output specifications; operating and resource limits; schedules and triggers; environment settings; exception, recovery and escalation behaviour; and observability records.

These elements are connected. For example, the output specification affects what data must be collected, while the agent's permissions determine which configured capabilities it can actually use. Configuration must be internally consistent with the agent's role, responsibilities, authority and boundaries.

Sensitive credentials should not be exposed in ordinary configuration files or prompts. Use appropriately protected credential mechanisms. Not every agent needs every configuration element, and no single configuration format is mandatory for all agents.

A practical review checks purpose, scope, access, capabilities, input/output clarity, resource limits, triggers, secret handling, failure handling, record requirements and the active configuration version.



### 7.3 Initialization and Startup

Initialization prepares an agent instance and its operating context; startup activates the prepared agent or task; runtime is the period when work is performed and state changes. A typical startup sequence receives a valid trigger, identifies the agent and environment, loads and validates approved configuration, checks policy and permissions, prepares dependencies, loads credentials securely, creates the task context and initial state, performs readiness checks, and starts only when required checks pass.

A running process is not necessarily ready. Liveness checks show whether a process is alive; readiness checks establish whether it can perform its intended work. Startup must define safe responses to invalid configuration, failed permission checks, missing credentials, unavailable dependencies and incomplete input. Reduced operation is acceptable only when explicitly allowed and clearly reported.

For the agricultural Market Data Collector, the startup flow checks its identity, configuration version, geographic and commodity scope, permissions, credentials, sources and destination, then creates a task ID and begins collection after readiness checks. If a configured source is unavailable, the agent must follow its exception policy and disclose any reduced coverage rather than imply complete collection.

Principles: validate before execution; distinguish liveness from readiness; do not bypass permissions; protect credentials; define failure and degraded-mode handling; record startup outcomes and configuration versions.



### 7.4 Agent Lifecycle and States

An agent lifecycle describes the journey from creation and configuration through initialization, operation, maintenance, shutdown and eventual retirement. An agent state describes its current operating condition. The project framework introduced states such as Created, Configuring, Initializing, Ready, Running, Waiting or Blocked, Paused, Failed, Recovering, Stopping, Stopped and Retired. These are illustrative, not a universal standard.

A state machine defines permitted states and transitions, the events that trigger them, required checks and who is authorised to request them. Agent state must be distinguished from task state: one agent may handle many tasks, and a task can complete while the agent remains ready for further work.

Paused, stopped, failed and retired have different meanings. Recovery should establish the cause of failure, preserve relevant evidence and state, check authority and consider whether retrying could duplicate an external action. Graceful shutdown should handle new and in-progress work, save necessary state, close connections and release resources. Retirement should stop new assignments, handle outstanding work, revoke access and preserve records required for accountability.

## Important project boundaries

- Do not divert the learning sequence into detailed platform or tool evaluations before a relevant need arises.
- Do not assume blockchain or any other technology is compulsory. Revisit a technology only when a specific requirement warrants it.
- The agricultural intelligence system is an illustrative example, not a final implementation specification.
- The five autonomy levels are a project teaching framework, not a universal industry standard.

## Next action

Continue with **Discipline 1 → Chapter 7 → 7.5 Configuration and Version Changes**. Chapter 7 is in progress; do not treat the remaining planned subsections as lessons already covered.
