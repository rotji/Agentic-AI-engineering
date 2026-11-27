# Current State

## Project
Agentic AI Engineering

## Curriculum
13 disciplines. See [Curriculum](CURRICULUM.md).

## Active learning position

- **Completed discipline:** 1 — Agent Architecture and Design
- **Completed chapters:** 1–8
- **Chapter 6:** Complete (subsections 6.1–6.7)
- **Chapter 7:** Complete (subsections 7.1–7.6)
- **Chapter 8:** Complete (subsections 8.1–8.7)
- **Final review:** Completed; no further foundational architecture chapter was identified.
- **Next discipline:** 2 — Reasoning and Planning
- **Discipline 2 status:** In progress; scope and 10-chapter sequence defined.
- **Chapter 1:** In progress; subsections 1.1–1.3 covered.
- **Next learning step:** Chapter 1.4 — Deliberative and Reactive Behaviour.

## Discipline 2 — Reasoning and Planning

The scope and initial 10-chapter sequence are defined. Chapter 1 subsection 1.1, What Reasoning and Planning Mean in Agentic Systems, is covered. The lesson defined reasoning as interpreting information and assessing conclusions, and planning as formulating a possible course of action toward an objective. It used an agricultural market-price investigation to show how evidence assessment informs a proposed investigation plan. It emphasised that reasoning and plans can be wrong, that plans are not completed execution, and that both must respect evidence, constraints and assigned authority. Subsection 1.2, Reasoning vs Planning vs Decision-Making vs Execution, is now covered. Reasoning interprets and assesses; planning organises a course of action; decision-making selects among options; execution carries out an authorised action. These functions can interleave, and an action attempt does not prove success. Subsection 1.3, How Reasoning and Planning Fit into an Agent's Operation, is now covered. Reasoning and planning depend on the objective, context, current state, model capabilities, system constraints and available actions. Plans must pass authority and feasibility checks; execution occurs through the surrounding system; outcomes must be observed and task state updated. Continue with 1.4, Deliberative and Reactive Behaviour.

See [Discipline 2 learning sequence](disciplines/02-reasoning-and-planning/README.md).

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



### 7.5 Configuration and Version Changes

Configuration changes should be justified, defined, impact-assessed, approved where required, validated, tested, deployed in a controlled way, monitored and recorded. Configuration versioning identifies the settings that governed an agent or task. Model, instruction, policy, schema and software versions may change independently and should be identified separately when relevant.

A controlled change process includes identifying the need, defining the change, assessing impacts on responsibilities, permissions, boundaries, resources and downstream agents, obtaining approval, preparing a candidate version, validating and testing it, releasing it, monitoring results, and promoting or rolling back as appropriate.

Testing should examine expected behaviour, failure cases, permissions, outputs and downstream compatibility. Rollback restores a previous approved configuration but does not automatically reverse external actions already performed. Configuration drift occurs when actual operating settings differ from the approved record. The system should define when new versions take effect so active consequential tasks do not unknowingly mix incompatible settings.

An agent may propose a configuration change but must not automatically approve or apply changes beyond its authority.



### 7.6 Lifecycle Management and Continuity

Lifecycle management governs agents throughout their operational lives. Continuity preserves the required service, task progress, information, authority and accountability when an agent is unavailable, updated, replaced or retired. Continuity does not require one process to run forever.

Important dimensions include identity, task, knowledge, service, responsibility/authority and accountability continuity. The system should distinguish a logical agent identity from its running instance, task and configuration version.

Long-running work may require checkpoints recording task identity, status, completed and outstanding work, inputs, outputs, relevant versions, pending approvals, errors and external-action status. A handover requires identifying affected tasks, preserving progress, checking the receiving agent's suitability and authority, defining transfer scope, authorising the transfer, preventing duplicate execution, confirming acceptance, updating permissions and recording the result.

A replacement must not blindly inherit the old agent's permissions. During unavailability, the system may wait, retry, reassign, use an approved fallback, pause the service or escalate. The correct response depends on risk and whether repeating an action could cause duplicate effects.

Maintenance requires a plan for active tasks, checkpoints, transfer or cancellation, reinitialization and readiness checks. Retirement must transfer or close responsibilities, handle outstanding tasks, revoke access, preserve required records and inform affected dependants.

Continuity expectations should reflect service criticality. Recovery Time Objective (RTO) is the target time to restore a service; Recovery Point Objective (RPO) is the maximum acceptable amount of data or progress loss expressed as time. These are planning targets, not guarantees. Test continuity by simulating restarts, unavailable dependencies, task handovers, permission revocation, duplicate-action risks and agent retirement.

## Discipline 1 review outcome

The review found that Chapters 1–7 establish the agent concept, components, autonomy, identity, authority, boundaries, relationships, accountability, configuration and lifecycle. The remaining gap is an end-to-end method for translating a problem and its requirements into a coherent agent architecture.

A final synthesis chapter, Chapter 8 — From Requirements to Agent Architecture, has therefore been added. It will cover problem framing and agent suitability, requirements and constraints, capability mapping, high-level architecture selection, component boundaries and flows, autonomy and oversight integration, and architecture documentation and review.

Detailed methods assigned to Disciplines 2–13 remain in those disciplines. See [Discipline 1 Review](disciplines/01-agent-architecture-and-design/REVIEW.md) and [Chapter 8 outline](disciplines/01-agent-architecture-and-design/chapters/08-from-requirements-to-agent-architecture.md).



## Chapter 8 progress

### 8.1 Problem Framing and Agent Suitability

Architecture should begin with the problem and desired outcome, not a predetermined decision to build an agent. A useful problem statement identifies affected users, current process, difficulty, desired outcome, frequency, supporting evidence and constraints.

Separate the problem, desired outcome and proposed solution. An agent may be useful when the work requires contextual judgement, adaptive multi-step activity, action selection and feedback. These are suitability signals, not automatic proof that an agent is needed.

Compare an agent with conventional software, workflow, automation, AI assistance and hybrid approaches. Use simpler methods for predictable, rule-based work when they adequately meet the need. Consider hybrid systems when different parts of a process need different capabilities.

Assess objective clarity, need for adaptive judgement, action selection, feedback, available information and capabilities, enforceable boundaries, evaluability, manageable failures and whether benefits justify cost and complexity. Consider both likelihood and severity of failure. Higher-impact actions may require stronger validation, restricted authority, human approval and recovery controls.

The agricultural intelligence example illustrated a hybrid approach: scheduled collection and structured parsing may be conventional automation; variable document extraction may use AI assistance; field and unit checks can be deterministic; unusual market investigations may justify an agent; and purchases or financial commitments require separately authorised control.

Principles: frame the problem first; distinguish problem, outcome and solution; use agents only where adaptive goal-directed behaviour provides justified value; prefer simpler methods for predictable tasks; consider hybrid designs; assess failure consequences and preserve evidence and assumptions.



### 8.2 Requirements, Constraints and Operating Context

Requirements describe what the system must do and the qualities it must satisfy. Functional requirements describe behaviours and capabilities; quality requirements cover properties such as accuracy, timeliness, availability, reliability, security, traceability, usability, scalability and maintainability.

Constraints limit acceptable design choices, such as budget, access, connectivity, jurisdictional obligations, existing procedures or approval requirements. Operating context describes the people, organisations, processes, geography, information environment, technical conditions, external circumstances and workload in which the system will work.

The lesson distinguished stakeholders from actors and identified the need to describe data requirements, information sources, dependencies and what happens when they are unavailable or unreliable. It also established the importance of classifying information as verified fact, assumption, constraint, preference, open question or risk.

Requirements should be prioritised, made testable where possible and traced from problem to desired outcome, requirement, architecture component/process and validation evidence. The agricultural intelligence table is illustrative and not a verified description of current market operations.



### 8.3 Capability and Responsibility Mapping

Requirements describe what the system must achieve; capabilities describe what it must be able to do; responsibilities identify which participant owns delivery of a capability or outcome. Components perform work, while tools are specific means a component may use. These concepts should not be confused.

Capabilities should be derived from requirements, decomposed until inputs, outputs and ownership are clear, and classified by the nature of the work: deterministic, interpretive, adaptive, human-led or hybrid. Capabilities may be provided by conventional software, automation/workflows, agents, people or external systems.

The agricultural intelligence example mapped collection, extraction, normalisation, validation, evidence assessment, change detection, adaptive investigation, report preparation, human approval and notification to a mixed set of candidate providers. This is an illustrative architecture exercise, not an implementation decision.

Each defined responsibility should have a clear owner, identified contributors, inputs, output, acceptance condition, boundary, dependencies and escalation path. The map is incomplete if requirements are uncovered, capabilities have no viable provider or outputs have no receiving participant.

Principles: derive capabilities from requirements; avoid creating an agent for every activity; use the simplest suitable provider; keep ownership clear; define important handoffs; preserve evidence status; record unresolved assumptions and gaps.



### 8.4 Selecting the High-Level Architecture Shape

Architecture shape is the broad arrangement of system components and responsibilities. The lesson compared conventional software or automation without agents, a single-agent design, one agent supported by workflows, multi-agent systems and hybrid systems.

The selection principle is to begin with the simplest sufficient arrangement. A single agent may suit coherent, bounded adaptive work that shares context and can be owned clearly. Multiple agents may be justified by distinct responsibilities, separate contexts or permissions, parallel work, independent checking, lifecycle or scaling needs, or operational isolation. The coordination, testing, monitoring and maintenance overhead must be weighed against those benefits.

Hybrid systems combine agents with conventional software, automation, workflows, external services and people. The agricultural intelligence example used scheduled collection, deterministic parsing and validation, adaptive investigation where justified, human review for consequential findings and controlled notification after approval. This remains illustrative, not a final implementation commitment.

The lesson also distinguished architecture shape from autonomy: a single agent can have high autonomy within limited authority, and a multi-agent system can remain under close human supervision. Coordinator-led, distributed and mixed arrangements were introduced only as high-level organisational choices; detailed orchestration remains in Discipline 6 and self-governing arrangements in Agentic Governance.

Principles: select the simplest sufficient architecture; do not make an agent for every capability; use multiple agents only when real separation benefits justify coordination overhead; preserve human control and accountability where required; document alternatives and the reasons for the chosen shape.



### 8.5 Component Boundaries, Interfaces and Flows

A component boundary defines the responsibility and scope of a system part. A component may be an agent, conventional software, workflow, data store, external system or human-operated function; a boundary does not necessarily mean a separate deployment or agent.

The lesson established the design aim of high cohesion within components and manageable coupling between them. An interface defines the agreed interaction between components and is not necessarily a software API. Important interactions should have a contract covering producer and consumer, purpose, inputs, outputs, structure and meaning, provenance, conditions, authority, failure behaviour, acknowledgement and relevant version compatibility.

Information flow describes how observations, requests, evidence and results move. Control flow describes how work is triggered, directed, approved, paused or allowed to proceed. Both matter. The agricultural intelligence example mapped intake, normalisation, evidence assessment, monitoring/calculation, adaptive investigation, human approval and reporting/notification as candidate responsibilities—not necessarily separate deployed components.

Boundaries should clarify what each component owns and does not own, its inputs and outputs, dependencies, permissions and escalation. Preserve source references, timestamps, units, verification status and uncertainty across handoffs. Avoid hidden or circular dependencies and define what happens when an interface fails.

Principles: use coherent responsibility boundaries; aim for high cohesion and manageable coupling; define important interface contracts; distinguish information flow from control flow; preserve provenance and authority across handoffs; make dependencies and failure behaviour explicit; do not assume each component must be a separate agent or technology.



### 8.6 Integrating Autonomy, Authority and Human Oversight

Autonomy describes how independently an agent may operate; authority defines what it is permitted to decide or do; human oversight describes how people supervise, approve, constrain or intervene. These decisions must be designed together but are not interchangeable.

The lesson reused the project's five-level autonomy framework from Chapter 5: Level 1 Advisory; Level 2 Assisted execution; Level 3 Conditional autonomy; Level 4 High autonomy; Level 5 Full operational autonomy. These are project teaching levels, not a universal industry standard. Autonomy should reflect responsibility, demonstrated reliability, operating conditions and potential consequences. Different agents and action categories may have different levels and controls.

Human-in-the-loop means a person participates before a decision or action proceeds. Human-on-the-loop means a person supervises and can intervene while the system operates within limits. Human-out-of-the-loop means no routine human participation in each action; it does not remove governance or organisational accountability.

Meaningful oversight requires relevant information, competence, time, authority, visibility, intervention capability and clear responsibility. Approval gates should be placed at consequential boundaries such as sensitive publication or financial commitment. Define who may approve, what evidence they receive, how rejection or silence is handled and how the decision is recorded.

Escalation conditions include conflicting evidence, out-of-scope requests, threshold breaches, missing approval, repeated failures and safety or security concerns. The system should stop or hold restricted actions when required decisions are unavailable. Operating conditions may reduce or suspend autonomy; an agent must not unilaterally increase its own authority or autonomy.

An action-level control map helps expose permissions and oversight requirements that a single autonomy label might hide. Record decisions, permissions, approvals and interventions so the design remains accountable.

## Chapter 8 completion

Chapter 8 completed the end-to-end architecture-design synthesis: problem framing, requirements and context, capability mapping, architecture-shape selection, component boundaries and flows, autonomy/authority/oversight integration, and architecture blueprint production and review.

## Discipline 1 final review

Discipline 1 is complete for progression to the specialist disciplines. Chapters 1–7 establish foundational agent concepts and agent-level design. Chapter 8 provides the end-to-end method for translating a problem and requirements into a coherent, technology-neutral architecture. The detailed treatment of specialist topics remains assigned to Disciplines 2–13. The concise introductory coverage in Chapters 1–4 should not be mistaken for exhaustive treatment of the topics they introduce.

## Important project boundaries

- Do not divert the learning sequence into detailed platform or tool evaluations before a relevant need arises.
- Do not assume blockchain or any other technology is compulsory. Revisit a technology only when a specific requirement warrants it.
- The agricultural intelligence system is an illustrative example, not a final implementation specification.
- The five autonomy levels are a project teaching framework, not a universal industry standard.

## Next action

Begin **Discipline 2 — Reasoning and Planning** by establishing its learning scope, boundaries and chapter sequence. Do not start detailed tool selection before a relevant capability requirement arises.
