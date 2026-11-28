# Changelog

## 2026-11-28 — Real-time capability when justified

- Established a conditional architecture principle: selected sources and workflows may support real-time or near-real-time updates when a demonstrated decision need justifies the cost and complexity.
- Distinguished on-demand, scheduled/batch, near-real-time and continuous/streaming update modes.
- Added a requirements test covering decision impact, acceptable freshness, source capabilities and permissions, reliability, economics, fallback, human authority and measurement.
- Documented candidate mechanisms such as webhooks, event feeds, polling, change detection, queues, retries and reconciliation without selecting a technology stack.
- Added provenance, evidence, privacy, reliability and authority safeguards.
- Clarified that the current agricultural daily brief remains scheduled and human-supervised; no real-time pipeline or always-on service is implemented or approved.
- Recorded decision D-016 and linked the principle from the agricultural relationship document and current state.

## 2026-11-28 — Make agricultural intelligence relationship explicit

- Added a dedicated relationship document defining Agricultural Ecosystem Intelligence as the first practical application and validation path for Agentic AI Engineering.
- Established separate repository responsibilities and sources of truth: reusable engineering learning here; agricultural operational evidence and activity in the agricultural repository.
- Positioned the scheduled daily brief as a human-supervised workflow and requirements source, not proof of a fully engineered autonomous system.
- Defined the theory → engineering application → agricultural validation learning loop and maturity progression from scheduled workflow toward possible integrated and agentic systems.
- Recorded decision D-015 and linked the relationship from project navigation, overview, current state and continuation guidance.
- Preserved the curriculum continuation point at Discipline 2, Chapter 4.4.

## 2026-11-28 — Document social platform intelligence and access boundaries

- Added a source reference covering Facebook, Instagram, WhatsApp, X and LinkedIn as candidate intelligence sources and voluntary submission channels.
- Distinguished public content, managed professional/Page accounts, public research libraries, business messaging inboxes and private conversations.
- Recorded current access barriers: Meta Content Library institutional eligibility and controlled environment, LinkedIn organisation/app vetting, and X's pay-per-use API pricing.
- Clarified WhatsApp Business Platform messaging and business-created Groups API are not general access to unrelated private chats or consumer groups.
- Established that social posts are claims or signals, not proof of quotations, transactions or market conditions.
- Added privacy, provenance, coverage, duplication, corroboration and cost controls; listed additional social platforms as unassessed candidates.
- Added decision D-014 and preserved the next learning step, Chapter 4.4.

## 2026-11-28 — Document web data acquisition and scraping

- Added a reference document locating crawling, scraping, browser automation, APIs and data ingestion within the wider information-acquisition capability.
- Established a source-first method: prefer suitable APIs, official datasets, feeds, exports or approved integrations before considering permitted scraping.
- Documented an acquisition pipeline covering source assessment, retrieval, preservation, extraction, normalisation, quality checks, provenance, evidence classification and monitoring.
- Recorded responsible collection boundaries, including terms and licences, privacy, request limits, access controls and the limited role of robots.txt.
- Connected data acquisition to the 13 disciplines and the agricultural pilot without selecting or deploying a scraper.
- Added decision D-013 and preserved the next learning step, Chapter 4.4.

## 2026-11-28 — Clarify automation, workflows, agents and Skills

- Expanded the reusable procedural knowledge document to distinguish workflow, automation and orchestration.
- Clarified that automation may be deterministic, AI-assisted or agent-enabled, while Skills provide reusable procedural guidance and do not trigger or schedule work by themselves.
- Added a hybrid agricultural intelligence example combining scheduled collection, deterministic validation, agent-assisted interpretation, human review and governed reporting as a conceptual illustration only.
- Kept the example provisional; no automation platform, runtime or production workflow has been selected or implemented.

## 2026-11-28 — Reusable Skills and procedural knowledge principle

- Added a cross-cutting architecture note on packaging reusable procedural expertise as Skills.
- Distinguished Skills from agents, prompts, context, tools, workflows/orchestration, governance and evaluation.
- Documented progressive disclosure, candidate Skill contents, evaluation-first development, lifecycle, security and portability boundaries.
- Established the principle to assess a reusable procedure with an existing agent/runtime before creating a specialist agent, while retaining separate agents where requirements justify them.
- Added provisional agricultural Skill candidates for source assessment, market-observation assessment, producer/location evidence, evidence comparison and intelligence reporting; none is treated as implemented or validated.
- Explicitly kept Skills cross-cutting rather than adding a fourteenth discipline, and did not select a vendor, format or runtime.
- Preserved the next learning step: Chapter 4.4, Constraints, Resources, Time and Dependencies.

## 2026-11-28 — Discipline 2 Chapter 4.3

- Covered and documented subsection 4.3, Actions, Preconditions and Effects.
- Defined actions, preconditions and effects; distinguished actions from external events.
- Explained action representations using actor, target, parameters, prerequisites, expected effects, observable results and failure conditions.
- Separated technical capability, access, authority and safety permission.
- Covered positive, negative and conditional effects and the distinction between intended effects and verified outcomes.
- Explained success, failure, partial success, unexpected results and unknown outcomes, including caution with timeouts and repeated operations.
- Applied the action model to retrieving an agricultural dataset and checking its integrity, identity and version.
- Set the next learning point to Chapter 4.4, Constraints, Resources, Time and Dependencies.

## 2026-11-28 — Discipline 2 Chapter 4.2

- Covered and documented subsection 4.2, Current State, Goal State and State Changes.
- Defined state as a task-relevant representation and distinguished current state, goal state and state changes.
- Distinguished goals as completion conditions from activity lists and workflow progress.
- Explained how state may change through agent actions, external events, other actors, corrections, new observations and time.
- Separated real-world state, information state, task state and workflow status.
- Applied the distinctions to an agricultural source-assessment workflow; preserved event, observation, publication, collection, review and update times.
- Emphasised that attempted actions and completed workflow steps do not prove goal achievement; preserved the distinctions among zero, missing, unknown, unavailable, estimated and stale values.
- Set the next learning point to Chapter 4.3, Actions, Preconditions and Effects.

## 2026-11-28 — Discipline 2 Chapter 4.1

- Covered and documented Chapter 4.1, Problem and Environment Representation.
- Explained the purpose of structured problem and environment representations, including task scope and system/environment boundaries.
- Distinguished actors, entities, attributes, relationships, processes, events, sources, resources, conditions and interfaces.
- Distinguished real-world entities from digital records, source documents and claims; covered identity matching and the risks of false entity merges or invented relationships.
- Explained abstraction, observability and partial knowledge, including known, observed-but-unverified, inferred, unknown, unavailable and disputed information.
- Applied a provisional representation to an agricultural market-quotation comparison; explicitly kept it as a teaching aid rather than an approved schema or final pilot scope.
- Set the next learning point to Chapter 4.2, Current State, Goal State and State Changes.

## 2026-11-27 — Chapter 3.5 and evidence assessment

- Covered and documented subsection 3.5, Hypotheses, Evidence, Confidence and Limitations.
- Distinguished observation, evidence, hypothesis, inference and conclusion; separated source reliability from claim verification, freshness, representativeness and inference strength.
- Covered supporting, contradicting and missing evidence, absence-of-evidence limits, qualitative confidence and revising assessments when new evidence arrives.
- Completed Chapter 3, Reasoning Patterns and Inference (3.1–3.5).
- Updated the discovery register with newer indexed World Bank variable metadata; FAO's documented country-filtered series and price retrieval API; and Agromate's differing nine-state source-data and 21 state-market pilot descriptions.
- Recorded that NBS and World Bank raw file/API retrieval attempts did not yield inspected row-level data in this session; the FAO API documentation is inspected but Nigeria series have not yet been enumerated.
- Kept the Plateau traceability/coverage opportunity as an unvalidated hypothesis, not a confirmed market gap.
- Set the next learning step to Chapter 4.1, Problem and Environment Representation.

## 2026-11-27 — Discipline 2 Chapter 3 completed

- Covered and documented subsection 3.5, Hypotheses, Evidence, Confidence and Limitations.
- Distinguished observations, evidence, hypotheses, inferences and conclusions.
- Explained claim-specific evidence assessment and separated source reliability, claim verification, evidence status, freshness, representativeness, comparability and inference strength.
- Covered supporting, contradicting and missing evidence, including the limits of absence-of-evidence arguments.
- Introduced qualitative confidence reporting, evidence-based reassessment and explicit limitation reporting; warned against invented confidence percentages.
- Applied claim assessment to the provisional Plateau market-information opportunity hypothesis; it remains weakly supported and is not a validated user problem or confirmed market gap.
- Completed Chapter 3, Reasoning Patterns and Inference (subsections 3.1–3.5).
- Set the next learning point to Chapter 4.1, Problem and Environment Representation.

## 2026-11-27 — Chapter 3.4 and agricultural source verification

- Covered and documented Chapter 3.4, Causal Reasoning, Correlation and Analogy.
- Distinguished correlation from causation and examined confounding, reverse causality, shared trends, temporal order, mechanisms and counterfactual comparisons.
- Compared observational evidence with controlled experiments and explained why before-and-after changes alone do not prove cause.
- Applied causal reasoning to agricultural price and transport examples.
- Explained analogical reasoning and the need to validate cross-sector transfers in mining, healthcare and other domains.
- Refined the discovery register with five candidate source assessments using current published catalogue and platform descriptions.
- NBS May 2026 ZIP listing confirmed, but the download timed out; the workbook remains uninspected.
- World Bank November 17 indexed release identified; detailed pages accessible in this review remained on older cached versions, so the newest market rows remain unverified.
- FAO FPMA platform capabilities and national/regional integration model documented; Nigeria series remain to be checked.
- PLACOM advertises local indicative prices; underlying observations and methodology remain under review.
- Agromate explicitly distinguishes nearby surveyed FEWS NET/WFP markets from its separate Plateau pilot estimates; CSVs and backtests remain uninspected.
- Retained the Plateau traceability/coverage opportunity as a hypothesis, not a confirmed market gap.
- Set the next learning point to Chapter 3.5, Hypotheses, Evidence, Confidence and Limitations.

## 2026-11-27 — Chapter 3.3 and initial agricultural source discovery

- Covered and documented Chapter 3.3, Abductive Reasoning and Explanation.
- Distinguished abduction from deduction and induction, and explained why a plausible explanation remains a hypothesis.
- Covered competing explanations, supporting and contradicting evidence, discriminating tests and common abductive errors.
- Applied abductive reasoning to an unusual agricultural market quotation without claiming a cause.
- Conducted initial desk research on five candidate sources/platforms: NBS Selected Food Price Watch, World Bank Nigeria food price estimates, FAO FPMA, PLACOM and Agromate Intelligence.
- Populated the agricultural discovery register with source descriptions, preliminary status, limitations and follow-up checks.
- Identified a possible Plateau local-market price coverage and traceability gap as a hypothesis only; no unmet user need has been confirmed.
- Recorded important limitations: NBS monthly selected-food reports and state/national averages; World Bank's indexed/opened version discrepancy and model-imputed values; FAO series granularity to check; PLACOM indicative prices with methodology to verify; and Agromate's distinction between nearest external survey markets and its own Plateau pilot estimates.
- Set the next learning point to Chapter 3.4, Causal Reasoning, Correlation and Analogy.

## 2026-11-27 — Parallel learning and practical pilot progress

- Covered and documented Chapter 3.2, Inductive Reasoning.
- Distinguished deduction from induction and explained why inductive conclusions remain provisional.
- Covered generalisation, sampling, representativeness, selection bias, source dependence, comparability and cautious prediction.
- Applied induction to agricultural market observations while preserving geographic, product, market-level and time limits.
- Created a provisional Agricultural Pilot Charter to guide problem discovery and a first bounded end-to-end evidence workflow.
- Kept the pilot hypothesis, first users, sample scope, evidence thresholds and solution choice explicitly unresolved pending discovery.
- Confirmed practical work proceeds alongside the curriculum.
- Set the next learning point to Chapter 3.3, Abductive Reasoning and Explanation.

## 2026-11-27 — Discipline 2 learning progress

- Began Chapter 3, Reasoning Patterns and Inference.
- Covered and documented subsection 3.1, Deductive Reasoning.
- Distinguished premises, conclusions and inference, and explained logical validity versus soundness.
- Covered categorical reasoning, modus ponens, modus tollens, affirming the consequent and denying the antecedent.
- Explained necessary and sufficient conditions and the danger of reversing one-way rules.
- Applied deduction to agricultural producer-location evidence and market-observation classification.
- Emphasised that valid logic does not establish the truth of premises and that missing evidence does not prove an event did not occur.
- Set the next learning point to Chapter 3.2, Inductive Reasoning.

## 2026-11-27 — Discipline 2 learning progress

- Covered and documented subsection 2.5, Ambiguity, Missing Requirements and Clarification.
- Distinguished ambiguity, missing requirements, underspecification, inconsistency and evidence uncertainty.
- Established response options: proceed, disclose a low-risk assumption, clarify, provide an honest partial result, or stop/defer/escalate.
- Applied the method to the agricultural producer-mapping task, including scope, destination relationships, evidence standards, information freshness and contact authority.
- Established progressive clarification and preserving interpretation decisions for recurring tasks.
- Completed Chapter 2, Goals, Instructions and Problem Formulation (subsections 2.1–2.5).
- Set the next learning point to Chapter 3.1, Deductive Reasoning.


## 2026-11-27 — Discipline 2 learning progress

- Covered and documented subsection 2.4, Constraints, Priorities and Conflicting Objectives.
- Distinguished goals, constraints, preferences and assumptions, and explained hard versus soft constraints.
- Identified goal conflicts, goal-versus-constraint conflicts, constraint conflicts, instruction conflicts and resource conflicts.
- Established feasibility and authority checks before optimisation.
- Explained priority-ordered selection and weighted scoring, including the rule that scoring must never override mandatory constraints.
- Applied conflict resolution to the agricultural producer-information pilot and defined responses when no feasible option exists.
- Set the next learning point to subsection 2.5, Ambiguity, Missing Requirements and Clarification.


## 2026-11-27 — Discipline 2 learning progress

- Covered and documented subsection 2.3, Goal States and Conditions for Success.
- Distinguished current state, goal state, success conditions, acceptance criteria and evidence of achievement.
- Explained quantitative and qualitative criteria, baselines, targets, thresholds and the distinction between mandatory conditions and indicators.
- Established honest reporting of achieved, partially achieved, blocked, not achieved and unresolved results.
- Applied the method to a sourced, evidence-labelled producer and product register for an agreed agricultural pilot scope without inventing numeric targets or evidence thresholds.
- Clarified that goal-state methods transfer across sectors, while domain-specific evidence and governance must be adapted.
- Set the next learning point to subsection 2.4, Constraints, Priorities and Conflicting Objectives.


## 2026-11-27 — Discipline 2 learning progress

- Covered and documented Chapter 2.2, Interpreting Instructions and Identifying Intent.
- Distinguished explicit instruction, intended purpose and relevant context.
- Established a method for identifying requester authority, literal request, scope, deliverable, constraints, context and assumptions.
- Used the Plateau agricultural producer-mapping instruction to illustrate careful interpretation of producer, product and destination relationships.
- Clarified the boundary between requested work and additional actions requiring separate authority.
- Established proceed, disclose-assumption, clarify and defer/escalate responses to uncertainty.
- Set the next learning point to Chapter 2.3, Goal States and Conditions for Success.


## 2026-11-27 — Discipline 2 practical learning progress

- Began Chapter 2, Goals, Instructions and Problem Formulation.
- Covered and documented subsection 2.1, Objectives, Goals and Desired Outcomes.
- Established project working definitions for objective, goal, desired outcome and task, while noting that terminology varies across methodologies.
- Distinguished outputs, outcomes and longer-term impacts.
- Connected the lesson to the practical agricultural pilot and recorded a provisional objective for refinement, not an approved system specification.
- Clarified that a bounded test scope does not permanently narrow the wider agricultural programme.
- Set the next learning point to subsection 2.2, Interpreting Instructions and Identifying Intent.


## 2026-11-27 — Practical pilot and cross-sector transfer direction

- Clarified that Agentic AI Engineering is an integrated learning, solution-discovery, assembly, engineering and validation journey, not a theory-only course.
- Established agriculture as the first practical pilot path rather than only an illustrative teaching example.
- Established the cycle: identify a real problem, study relevant concepts, define requirements, discover existing solutions, assemble, test, build only genuine gaps, document evidence and assess transferability.
- Added a sector-transfer method for assessing reusable principles across real estate, mining, healthcare and other domains without blindly copying sector-specific assumptions or controls.
- Clarified that practical pilot work may advance alongside the 13-discipline curriculum, with learning progress and build progress tracked separately.
- Recorded decision D-011 and added the Practical Build and Sector Transfer Method.


## 2026-11-27 — Discipline 2 learning progress

- Completed and documented Chapter 1.4, Deliberative and Reactive Behaviour.
- Distinguished deliberative behaviour from reactive responses and clarified that the distinction is not whether AI is used.
- Compared their strengths, limitations and appropriate use.
- Documented a hybrid behavioural arrangement and the need for explicit priorities and conflict handling.
- Completed Chapter 1, Foundations of Reasoning and Planning (subsections 1.1–1.4).
- Set the next learning point to Chapter 2.1, Objectives, Goals and Desired Outcomes.


## 2026-11-27 — Discipline 2 learning progress

- Covered and documented Chapter 1.3, How Reasoning and Planning Fit into an Agent's Operation.
- Connected reasoning and planning to objectives, assigned tasks, context, memory, model capabilities, state, authority controls, execution and feedback.
- Clarified that the model contributes capabilities but is not the entire agentic system.
- Documented the conceptual operating picture from objective and context through reasoning, planning, decision/control checks, execution, observation and task-state update.
- Reaffirmed boundaries with Disciplines 3–9 for memory, tools, execution, orchestration, governance and evaluation.
- Set the next learning point to Chapter 1.4, Deliberative and Reactive Behaviour.


## 2026-11-27 — Discipline 2 learning progress

- Covered and documented Chapter 1.2, Reasoning vs Planning vs Decision-Making vs Execution.
- Distinguished interpretation and assessment, plan formulation, option selection and carrying out an authorised action.
- Used the agricultural tomato-price investigation to show how the four activities interact.
- Clarified that these are conceptual functions, not necessarily separate software modules or a rigid sequence.
- Emphasised that a plan does not grant authority and that an action attempt does not prove success.
- Set the next learning point to Chapter 1.3, How Reasoning and Planning Fit into an Agent's Operation.


## 2026-11-27 — Discipline 2 started

- Began Chapter 1, Foundations of Reasoning and Planning.
- Covered and documented subsection 1.1, What Reasoning and Planning Mean in Agentic Systems.
- Defined reasoning as interpreting information and assessing conclusions, and planning as formulating a possible course of action toward an objective.
- Used the agricultural market-price investigation example to distinguish evidence assessment from the proposed investigation plan.
- Emphasised uncertainty, plan feasibility, authority boundaries and the distinction between planning and completed execution.
- Set the next learning point to 1.2, Reasoning vs Planning vs Decision-Making vs Execution.


## 2026-11-27 — Discipline 2 scope and learning sequence defined

- Established the scope, learning outcomes and boundaries for Discipline 2, Reasoning and Planning.
- Defined an initial 10-chapter sequence from foundational reasoning concepts through goal formulation, inference, problem representation, task decomposition, planning strategies, action selection, uncertainty, plan validation and replanning.
- Clarified boundaries with Context, Memory and Knowledge; Tools and Environment Engineering; Execution and Loop Engineering; and Orchestration and Multi-Agent Systems.
- Recorded that the sequence is defined but no Discipline 2 lesson has yet been taught.
- Set the next learning point to Chapter 1.1, What Reasoning and Planning Mean in Agentic Systems.


## 2026-11-27 — Chapter 8 and Discipline 1 completed

- Covered and documented subsection 8.7, Producing and Reviewing an Architecture Blueprint.
- Established the purpose, scope, contents, review process and maintenance of an architecture blueprint.
- Created a reusable, technology-neutral Agent Architecture Blueprint Template.
- Completed Chapter 8 (subsections 8.1–8.7).
- Performed the final Discipline 1 review and confirmed that no additional foundational architecture chapter is currently required.
- Marked Discipline 1 complete for progression to Discipline 2.
- Set the next action to define the scope and learning sequence for Discipline 2, Reasoning and Planning.


## 2026-11-27 — Chapter 8 learning progress

- Covered and documented subsection 8.6, Integrating Autonomy, Authority and Human Oversight.
- Integrated the project's five-level autonomy framework with action-level authority and oversight design.
- Distinguished human-in-the-loop, human-on-the-loop and human-out-of-the-loop arrangements.
- Established requirements for meaningful human oversight, approval gates, escalation and safe-stop behaviour.
- Documented risk-sensitive reduction or suspension of autonomy and the prohibition on agents unilaterally increasing their authority or autonomy.
- Set the next learning point to 8.7, Producing and Reviewing an Architecture Blueprint.


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
