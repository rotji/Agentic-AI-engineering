# Changelog

## 2026-11-27 — Chapter 8 learning progress

- Covered and documented subsection 8.5, Component Boundaries, Interfaces and Flows.
- Distinguished component boundaries, interfaces, information flows and control flows.
- Introduced cohesion and coupling as architecture quality concepts.
- Established interface-contract elements, including inputs, outputs, provenance, authority, failure behaviour and version compatibility.
- Mapped candidate agricultural intelligence components and clarified that architecture components do not automatically imply separate agents or deployments.
- Set the next learning point to 8.6, Integrating Autonomy, Authority and Human Oversight.


## 2026-11-27 — Chapter 8 learning progress

- Covered and documented subsection 8.4, Selecting the High-Level Architecture Shape.
- Compared non-agentic software/automation, single-agent, agent-plus-workflow, multi-agent and hybrid arrangements.
- Established criteria for using one agent or separating work across multiple agents.
- Distinguished architecture shape from autonomy level.
- Introduced coordinator-led, distributed and mixed arrangements at a high level while deferring detailed orchestration to Discipline 6.
- Applied a provisional hybrid architecture example to agricultural intelligence without committing to implementation.
- Set the next learning point to 8.5, Component Boundaries, Interfaces and Flows.


## 2026-11-27 — Chapter 8 learning progress

- Covered and documented subsection 8.3, Capability and Responsibility Mapping.
- Distinguished requirements, capabilities, responsibilities, components and tools.
- Documented capability derivation, decomposition and classification by work type.
- Mapped agricultural intelligence requirements to a mixed set of candidate providers: conventional software, automation, agents, human review and external dependencies.
- Established clear responsibility ownership, contributor roles, inputs, outputs, acceptance conditions, boundaries and escalation.
- Set the next learning point to 8.4, Selecting the High-Level Architecture Shape.


## 2026-11-27 — Chapter 8 learning progress

- Covered and documented subsection 8.2, Requirements, Constraints and Operating Context.
- Distinguished functional requirements, quality requirements, constraints and operating context.
- Documented stakeholders, actors, data requirements, dependencies, assumptions, preferences, risks and open questions.
- Established requirement prioritisation, testability and traceability to architecture decisions and validation evidence.
- Set the next learning point to 8.3, Capability and Responsibility Mapping.


## 2026-11-27 — Chapter 8 learning progress

- Began Chapter 8, From Requirements to Agent Architecture.
- Covered and documented subsection 8.1, Problem Framing and Agent Suitability.
- Established problem-first framing and the distinction between problem, desired outcome and proposed solution.
- Compared agents with conventional software, workflows, automation, AI assistance and hybrid solutions.
- Added an agent-suitability test based on adaptive judgement, action selection, feedback, control, evaluation, failure consequences and value.
- Set the next learning point to 8.2, Requirements, Constraints and Operating Context.


## 2026-11-27 — Discipline 1 coverage review

- Reviewed the documented coverage of Chapters 1–7.
- Confirmed that core agent concepts, components, autonomy, identity, responsibilities, authority, boundaries, relationships, accountability, configuration and lifecycle have been introduced.
- Identified one genuine gap: no end-to-end method yet exists in the documented curriculum for translating a real problem and its requirements into a coherent agent architecture.
- Added a final synthesis chapter, Chapter 8 — From Requirements to Agent Architecture, without expanding the number of disciplines.
- Recorded the review, scope boundaries and decision D-009.
- Set the next learning point to 8.1, Problem Framing and Agent Suitability.


## 2026-11-27 — Chapter 7 completed

- Covered and documented subsection 7.6, Lifecycle Management and Continuity.
- Distinguished identity, task, knowledge, service, responsibility/authority and accountability continuity.
- Documented checkpoints, agent handover, replacement, fallback handling, maintenance, retirement and continuity testing.
- Introduced Recovery Time Objective (RTO) and Recovery Point Objective (RPO) as recovery-planning concepts.
- Marked Chapter 7 complete and set the next step to review remaining Discipline 1 coverage before defining any further chapter.


## 2026-11-27 — Chapter 7 learning progress

- Covered and documented subsection 7.5, Configuration and Version Changes.
- Documented change assessment, approval, version identification, validation, testing, controlled rollout, monitoring, promotion and rollback.
- Distinguished agent configuration, model, instruction, policy, schema and software versions.
- Covered compatibility, configuration drift and changes during active tasks.
- Clarified that rollback does not automatically reverse external actions, and that agents may propose but not unilaterally authorise configuration changes.
- Set the next learning point to 7.6, Lifecycle Management and Continuity.


## 2026-11-27 — Chapter 7 learning progress

- Covered and documented subsection 7.4, Agent Lifecycle and States.
- Distinguished lifecycle stages from current operational states.
- Distinguished agent state from individual task state.
- Documented state transitions, readiness, pausing, stopping, failure, recovery, shutdown and retirement.
- Added recovery safeguards for repeated actions and controlled decommissioning.
- Set the next learning point to 7.5, Configuration and Version Changes.


## 2026-11-27 — Chapter 7 learning progress

- Covered and documented subsection 7.3, Initialization and Startup.
- Distinguished configuration, initialization, startup and runtime.
- Documented configuration validation, authority and policy checks, dependency preparation, secure credential loading, task-state initialization and readiness checks.
- Distinguished process liveness from readiness to perform work.
- Added startup failure and explicitly permitted degraded-mode handling.
- Set the next learning point to 7.4, Agent Lifecycle and States.


## 2026-11-27 — Chapter 7 learning progress

- Covered and documented subsection 7.2, Configuration Elements.
- Documented objective and scope, instructions and policies, model settings, context and knowledge sources, capabilities, permissions, input/output specifications, operating limits, triggers, environment settings, exception handling and observability.
- Distinguished configurable elements from enforced authority and runtime state.
- Added credential-protection guidance and a practical configuration review.
- Set the next learning point to 7.3, Initialization and Startup.


## 2026-11-27 — Chapter 7 started

- Began Chapter 7, Agent Configuration and Lifecycle.
- Covered and documented subsection 7.1, Agent Configuration.
- Distinguished configuration from identity, role, authority and runtime state.
- Established that important configuration should be explicit, controlled, versioned and reviewable.
- Set the next learning point to 7.2, Configuration Elements.


Significant changes to the project's structure, curriculum, decisions and learning progress are recorded here.

## 2026-11-27 — Chapter 6 completed

- Covered and documented Chapter 6.7, Agent Accountability.
- Distinguished operational accountability of agent behaviour from ultimate human or organisational accountability.
- Documented traceability evidence for agent identity, configuration, task origin, authority, inputs, actions, approvals, outputs, handoffs and outcomes.
- Distinguished logging, monitoring, auditing and evaluation.
- Covered multi-agent accountability, incident response, record protection and proportionate retention.
- Marked Chapter 6 complete and planned Chapter 7, Agent Configuration and Lifecycle.

## 2026-11-27 — Previous Chapter 6 learning progress

- Covered and documented Chapter 6.6, Agent Relationships.
- Documented peer, producer–consumer, delegation, coordinator–worker, supervisory and dependency relationships.
- Distinguished communication, delegation, coordination and authority.
- Covered communication patterns, message expectations, information provenance, trust, dependencies and failure handling.
- Established purpose-driven connections, information minimisation, provenance preservation and explicit escalation handling.
- Updated the project continuation point to Chapter 6.7, Agent Accountability.

## 2026-11-27 — Previous Chapter 6 progress

- Covered and documented Chapter 6.5, Agent Boundaries.
- Distinguished permitted authority from the boundaries and constraints that limit an agent's operation.
- Documented role, data, action, resource, operational, safety, delegation, evidence and change boundaries.
- Distinguished system-enforced restrictions from behavioural guidance.
- Established stop, explain and escalate behaviour, and boundary testing as design practices.
- Updated the project continuation point to Chapter 6.6, Agent Relationships.

## 2026-11-27 — Previous Chapter 6 progress

- Covered and documented Chapter 6.4, Agent Authority.
- Distinguished responsibility, authority and technical capability.
- Documented dimensions of authority, including decisions, data, actions, resources, scope, conditions, delegation and approvals.
- Clarified the difference between authority and autonomy.
- Established least privilege, explicit permission boundaries and system-enforced authorization as design principles.
- Updated the project continuation point to Chapter 6.5, Agent Boundaries.

- Covered and documented Chapter 6.2, Agent Roles.
- Covered and documented Chapter 6.3, Agent Responsibilities.
- Clarified the distinction between identity, role, responsibility, task and authority.
- Recorded that responsibility should be scoped, observable, achievable and supported by appropriate authority and dependencies.
- Clarified that assigning operational responsibility to an agent does not automatically transfer ultimate organisational or legal accountability to software.
- Updated the project continuation point to Chapter 6.4, Agent Authority.

## 2026-11-26 — Initial repository documentation

- Initialised the repository documentation and navigation.
- Recorded the project purpose, working principles and technology-neutral scope.
- Documented the 13-discipline curriculum.
- Recorded learning progress for Discipline 1, Chapters 1–5.
- Documented the start of Chapter 6 and subsection 6.1 Agent Identity.
- Recorded key decisions on Agentic Governance, differentiated autonomy, technology selection, blockchain deferral and the agricultural intelligence example.
- Set the next learning point to Chapter 6.2 Agent Roles.
