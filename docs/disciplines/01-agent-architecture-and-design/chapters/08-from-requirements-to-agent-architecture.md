# Chapter 8 — From Requirements to Agent Architecture

**Status:** In progress.

## Purpose

Bring together the concepts studied in Discipline 1 and establish a repeatable method for translating a real problem or requirement into a coherent agent architecture.

The purpose is not to select implementation tools or infrastructure. It is to determine whether an agent is appropriate, what the system must accomplish, which capabilities and components are needed, how they fit together and how the proposed architecture can be reviewed.

## Why this chapter is needed

Chapters 1–7 introduced the agent concept, conceptual components, system distinctions, autonomy, identity, roles, responsibilities, authority, boundaries, relationships, accountability, configuration and lifecycle.

The remaining gap is an end-to-end design method for assembling those concepts in response to a concrete problem.

This chapter is a synthesis chapter. It should reuse prior material rather than repeat it.

## Proposed learning scope

The following subsections are planned and have not yet been taught:

1. **8.1 Problem Framing and Agent Suitability:** Covered.
2. **8.2 Requirements, Constraints and Operating Context:** Covered.
3. **8.3 Capability and Responsibility Mapping:** Covered.
4. **8.4 Selecting the High-Level Architecture Shape:** consider a single agent, an agent with supporting workflow or automation, a hybrid system, or multiple specialised agents; defer detailed orchestration to Discipline 6.
5. **8.5 Component Boundaries, Interfaces and Flows:** establish responsibilities, inputs, outputs, information flows, control boundaries and dependencies at architecture level.
6. **8.6 Integrating Autonomy, Authority and Human Oversight:** ensure decisions, permissions, boundaries, approvals and escalation are coherent across the design.
7. **8.7 Producing and Reviewing an Architecture Blueprint:** document the design, assumptions, alternatives, trade-offs, unresolved questions and traceability to requirements.

## Scope boundaries

This chapter establishes architecture-level decisions only.

Detailed reasoning and planning methods belong to Discipline 2. Context, memory and knowledge engineering belong to Discipline 3. Tool and environment engineering belongs to Discipline 4. Execution-loop engineering belongs to Discipline 5. Detailed multi-agent orchestration belongs to Discipline 6. Security, governance, evaluation, human interaction, observability, infrastructure and continuous improvement remain assigned to their respective disciplines.

No particular model, framework, protocol, platform, database, infrastructure or implementation stack is assumed.

## 8.1 Problem Framing and Agent Suitability

### Core question

Before designing an agent, how do we establish what problem actually needs to be solved and whether an agent is the appropriate way to solve it?

A common architecture mistake is to begin with a technology choice: "We need an AI agent." That statement describes a proposed solution, not the underlying problem.

Architecture should begin with the problem and the desired outcome. An agent is one possible means of achieving that outcome. Conventional software, a fixed workflow, ordinary automation, a human-operated process or a hybrid arrangement may be more appropriate.

The first design decision is therefore not which agent to build. It is whether an agent is justified at all.

### 1. Frame the problem before proposing a solution

A useful problem statement should describe:

1. **Who experiences the problem?** Identify the people, organisation or system affected.
2. **What is happening today?** Describe the current process, behaviour or condition.
3. **What is difficult or failing?** Identify the delay, cost, uncertainty, error, missed opportunity or other problem.
4. **What outcome is needed?** Describe the improvement in observable terms.
5. **How often does the problem occur?** Distinguish a recurring need from a rare or one-off task.
6. **What evidence shows that the problem exists?** Identify observations, records, examples or user reports. Do not treat assumptions as verified facts.
7. **What constraints matter?** Consider time, budget, data access, privacy, safety, reliability, legal obligations and human involvement.

Avoid embedding the proposed solution in the problem statement.

For example, "Build an autonomous agricultural AI agent" is not a sufficiently framed problem. It does not say who needs what outcome, what currently fails or why autonomy is necessary.

A better starting point is:

"People who trade agricultural produce need timely, traceable information about significant changes in market prices and supply across relevant markets. Current information is scattered across sources, arrives at different times and varies in reliability. The desired outcome is to detect meaningful changes, verify supporting evidence and present useful findings with clear uncertainty and source details."

This describes a need without committing to an agent, a multi-agent architecture or a particular technology.

### 2. Separate the problem from the proposed solution

Use three distinct statements:

- **Problem:** the condition or difficulty that needs to be addressed.
- **Desired outcome:** what should be different when the problem is addressed.
- **Proposed solution:** a possible way to achieve that outcome.

For example:

| Layer | Agricultural intelligence example |
|---|---|
| Problem | Market information is fragmented, inconsistent and difficult to verify quickly. |
| Desired outcome | Timely, traceable market intelligence that distinguishes verified information from uncertain signals. |
| Possible solution | A combination of scheduled data collection, structured processing, verification procedures, analysis and, where useful, agentic investigation. |

The proposed solution is deliberately provisional. It must still be tested against the requirements and simpler alternatives.

### 3. Understand when agentic behaviour is useful

Agents are most worth considering when the problem genuinely benefits from some combination of:

- **Variable or ambiguous inputs:** information does not always arrive in one predictable structure.
- **Contextual judgement:** the system must interpret information in relation to the current situation rather than apply only fixed rules.
- **Adaptive, multi-step work:** the next step depends on what has been discovered so far.
- **Goal-directed action selection:** the system must choose among several permitted actions to make progress.
- **Observation and feedback:** results from one action influence what should happen next.
- **Uncertain environments:** conditions change and the system must respond within defined boundaries.

These characteristics make agentic behaviour potentially useful, but none of them alone proves that an agent is necessary. The expected benefit must justify the additional complexity and risk.

### 4. Recognise when a simpler solution is more appropriate

| Type of problem | Often suitable starting approach | Why |
|---|---|---|
| A fixed calculation with known inputs and rules | Conventional software or formula | The result is deterministic and does not require adaptive judgement. |
| A recurring action triggered by a schedule | Automation | The trigger and action are known in advance. |
| A fixed sequence of steps with predictable handoffs | Workflow | The sequence can be defined and controlled. |
| A person needs help understanding or drafting something but makes the decisions | AI assistant with human direction | AI helps with interpretation or generation without independent task execution. |
| A task needs variable interpretation, multi-step decisions and feedback-driven action | Agent may be justified | The system needs to choose and adapt its next steps toward an objective. |
| A process mixes fixed rules, AI interpretation, people and adaptive actions | Hybrid system | Different parts of the problem need different capabilities. |

These are starting points, not rigid classifications. A solution may combine several approaches.

### 5. Apply an agent-suitability test

Before choosing an agent, examine the following questions:

1. **Is there a clear objective?** Can we describe the outcome the agent is intended to achieve?
2. **Does the task need adaptive judgement?** Are fixed rules or a predetermined sequence insufficient for important parts of the work?
3. **Does the agent need to choose among actions?** Does the next step depend on context or observations?
4. **Can it observe the result of its actions?** Is there useful feedback that allows it to assess progress?
5. **Are the necessary capabilities and information available?** Can the system access appropriate inputs and permitted actions?
6. **Can its work be bounded?** Can we define what it may do, what it must not do and when it must escalate?
7. **Can its results be evaluated?** Can we determine whether it performed adequately?
8. **Are failures manageable?** Can the system contain errors, recover safely or involve a human?
9. **Does the benefit justify the cost and complexity?** Would an agent produce enough value to justify model usage, additional controls, operating effort and failure risk?

A strong case for an agent requires a convincing answer to the relevant questions. If the task is predictable and a simpler method meets the need, use the simpler method.

If the agent's actions cannot be bounded, evaluated or made sufficiently safe for their consequences, do not grant it independent authority. Redesign the task, add suitable oversight or use another approach.

### 6. Consider the consequences of failure

Suitability is not only about whether an agent can perform a task. It is also about what happens when it gets something wrong.

Compare these examples:

- An agent incorrectly categorises a low-risk internal research note.
- An agent publishes a false public market warning.
- An agent transfers funds to the wrong recipient.
- An agent deletes important historical records.

The consequences are very different.

For higher-impact actions, the architecture may need stronger validation, restricted permissions, human approval, reversibility, monitoring and recovery procedures. Some tasks may be suitable for agent-assisted analysis but not for autonomous execution.

The decision should account for both the probability of failure and the severity of its consequences.

### 7. Use a hybrid solution when different parts of the problem need different approaches

A real system rarely needs every step to be agentic.

Consider agricultural market intelligence:

| Activity | Possible approach | Reason |
|---|---|---|
| Run a scheduled collection job | Automation | The trigger is predictable. |
| Read a structured source with a known format | Conventional parser | Fixed extraction rules may be sufficient. |
| Extract price information from varied posts or documents | AI-assisted extraction | Inputs may be unstructured or inconsistent. |
| Check required fields, units and accepted ranges | Deterministic validation rules | These checks should be explicit and repeatable. |
| Investigate an unusual price movement across several sources | Agent may be useful | The investigation may require adaptive, multi-step research. |
| Calculate price differences and trends | Statistical or conventional computation, possibly AI-assisted interpretation | Numerical calculations should use suitable, testable methods. |
| Recommend a possible commercial opportunity | Agent-assisted analysis with evidence and uncertainty | The work may require combining context and several findings. |
| Approve a purchase or commit funds | Authorised human or separately controlled process | Consequential financial authority must not be inferred from an analytical recommendation. |

The point is not to choose an agent for every row. The point is to assign each part of the problem to the simplest suitable capability and combine them where necessary.

### 8. Common mistakes in problem framing

Avoid these mistakes:

- Starting with "Which AI model or agent framework should we use?" before establishing the problem.
- Assuming that a larger number of agents means a more capable system.
- Giving an agent a broad objective when most tasks are predictable and rule-based.
- Treating every unstructured input as a reason to create an autonomous agent.
- Ignoring the cost of model calls, supervision, validation and failure recovery.
- Assuming that an agent can be trusted simply because it completed similar tasks before.
- Designing an autonomous action before establishing whether its consequences can be controlled.
- Confusing a desirable feature with a real user or operational requirement.

### 9. A problem-framing template

Before designing an agentic solution, write down:

| Item | What to capture |
|---|---|
| Problem | What condition or difficulty needs to change? |
| Affected users | Who experiences the problem? |
| Current process | How is the work handled today? |
| Evidence | What demonstrates that the problem exists? |
| Desired outcome | What measurable or observable improvement is needed? |
| Frequency and variability | How often does the work happen and how much does it vary? |
| Decision complexity | Which parts require judgement or adaptation? |
| Required actions | What must the system actually do? |
| Consequences of failure | What harm or loss could result? |
| Constraints | What limits or obligations apply? |
| Simpler alternatives | Could software, automation, workflow or human work solve it adequately? |
| Agent justification | What specific capability makes an agent worthwhile? |

This is a thinking aid, not a requirement to complete a large document for every small task. The detail should be proportionate to the size and risk of the problem.

### Principles established

- Start with the problem and desired outcome, not a predetermined technology.
- Separate problem, desired outcome and proposed solution.
- Use an agent when adaptive, goal-directed behaviour provides a justified advantage over simpler approaches.
- Do not use autonomy for predictable work that conventional software or automation can handle adequately.
- Consider hybrid designs where different activities need different capabilities.
- Judge suitability against both expected benefit and consequences of failure.
- Do not grant independent execution where authority, boundaries, evaluation or recovery cannot be made sufficiently safe.
- Record assumptions and evidence; do not present an unverified problem statement as established fact.


## 8.2 Requirements, Constraints and Operating Context

### Core question

Once the problem is understood, how do we describe what the system must achieve, the conditions it must operate under and the limits its architecture must respect?

Problem framing explains why a system may be needed. Requirements and constraints translate that problem into design obligations. Operating context describes the environment, people, information, processes and external conditions in which the system must work.

These three areas are related, but they answer different questions:

- **Requirements:** What must the system do, or what qualities must it satisfy?
- **Constraints:** What limits or obligations restrict the possible solutions?
- **Operating context:** Where, for whom, and under what real-world conditions will the system operate?

A good architecture should be traceable back to these requirements and should make its assumptions and unresolved questions visible.

### 1. Functional requirements: what the system must do

Functional requirements describe system behaviours, capabilities or services that must be provided.

For the agricultural intelligence example, possible functional requirements might be:

1. Collect agricultural price observations from approved sources.
2. Record the product, market, location, price, unit, observation time and source.
3. Distinguish verified observations from unverified reports and market signals.
4. Identify significant price changes according to agreed rules.
5. Prepare an investigation when a defined condition is detected.
6. Produce reports that show the evidence and uncertainty behind their findings.
7. Notify authorised users when specified conditions are met.

These statements describe required functions. They do not yet prescribe whether each function should be implemented using an agent, conventional software, automation or a human process.

### 2. Quality requirements: how well the system must operate

Requirements are not limited to functions. A system also needs qualities that determine whether it is useful and acceptable.

Common quality areas include:

- **Accuracy:** How correct must its calculations, classifications and outputs be?
- **Timeliness:** How quickly must information be collected, analysed or delivered?
- **Availability:** When must the service be accessible?
- **Reliability:** How consistently must it perform under expected conditions?
- **Security and privacy:** What information and operations must be protected?
- **Traceability:** Can findings be linked to sources, versions, decisions and approvals?
- **Usability:** Can intended users understand and act on the outputs?
- **Scalability:** What increase in markets, products, users or workload must it accommodate?
- **Maintainability:** Can the system be corrected and changed without destabilising it?

These qualities may conflict. For example, collecting from more sources may improve coverage but increase processing time and cost. Requirements therefore need priorities and trade-offs, not just an unranked wish list.

Where possible, make quality requirements measurable.

Instead of saying "reports should be fast", specify a target such as "routine daily reports should be ready by an agreed local time, provided required sources have responded". The target, measurement method and exceptions must be agreed rather than invented by the architect.

### 3. Constraints: what limits the design?

Constraints restrict the set of acceptable architectural choices. They are not necessarily features the system must deliver.

Examples include:

- A fixed or limited budget.
- Limited availability of reliable data sources.
- Restrictions on the collection or use of personal or confidential information.
- Geographic or jurisdictional obligations.
- Limited network connectivity in some locations.
- A required response window.
- Existing organisational procedures that must be respected.
- Restrictions on who may approve external or financial actions.
- Requirements to use or integrate with an existing system.

A constraint can make an otherwise attractive design unsuitable. For example, an architecture that depends on continuous high-bandwidth connectivity may not be appropriate for an operating environment where connectivity is intermittent.

Record the source and status of important constraints. Distinguish confirmed constraints from preferences, assumptions or temporary conditions.

### 4. Operating context: the environment in which the system must work

Operating context describes the real conditions surrounding the system.

It may include:

1. **People and users:** who requests information, consumes outputs, supervises activity or approves actions?
2. **Organisations and processes:** which existing roles, procedures and decision-making arrangements does the system interact with?
3. **Geography and time:** which locations, local calendars, time zones, languages and regional conventions matter?
4. **Information environment:** which sources exist, how reliable and timely are they, and in what formats do they provide information?
5. **Technical environment:** what connectivity, devices, existing systems and operating conditions are available?
6. **External environment:** what market events, policy changes, seasonal conditions or third-party dependencies may affect operations?
7. **Operational conditions:** when will the system be used, how often, by whom and under what workload?

Operating context should describe reality as it is understood, including uncertainty. Do not write an unverified assumption as if it were a confirmed property of the environment.

### 5. Actors and stakeholders

An architecture must account for the people and external systems that interact with it or are affected by it.

A stakeholder is a person, group or organisation with an interest in the system or its outcomes. An actor is a role or external system that directly interacts with the system in a particular use case.

In the agricultural intelligence example, possible stakeholders include producers, traders, market operators, analysts, buyers and organisations using the information. Possible actors include an authorised analyst requesting an investigation, a source system supplying observations and an authorised reviewer approving a sensitive report.

Not every stakeholder needs direct system access. Some may only be affected by its outputs or decisions.

For each relevant actor, clarify:
- What do they need from the system?
- What information may they provide?
- What information or service should they receive?
- What authority do they have?
- What decisions remain theirs?
- What could go wrong for them if the system is incorrect or unavailable?

This helps avoid designing around the assumptions of only one user or one organisation.

### 6. Data and information requirements

The system's required information should be described before deciding how to store or retrieve it.

Questions include:
- What information is needed to fulfil each requirement?
- Where could it originate?
- Who owns or controls access to it?
- How current must it be?
- What units, definitions and formats must be consistent?
- How will provenance and verification status be preserved?
- What information is sensitive or restricted?
- What happens when information is missing, conflicting or stale?
- How long does information need to be retained, and why?

For example, a price observation without a unit, market, date or source may be unsuitable for comparison. The architecture must therefore account for these information requirements.

Detailed data modelling, memory, knowledge representation and retrieval belong to Discipline 3. Here, the goal is to identify what information the architecture must provide for and what uncertainties remain.

### 7. Dependencies and external conditions

A dependency is something the system relies on but does not fully control.

Examples:
- A third-party information source.
- A data provider or market reporting organisation.
- An external service or system.
- A human reviewer or approval process.
- Network connectivity.
- Another internal component or agent.
- A legal or organisational decision that must be made before operation.

For every important dependency, identify:
- What the system needs from it.
- Who controls it.
- How reliable or available it is known to be.
- What happens if it is delayed, inaccurate or unavailable.
- Whether an approved alternative exists.
- Whether the dependency creates cost, access, privacy or continuity risks.

Do not assume a dependency will always be available simply because it works during an initial demonstration.

### 8. Assumptions, facts and open questions

Architecture work often begins before every detail is known. The important thing is to distinguish the status of information.

- **Verified fact:** supported by evidence or direct confirmation.
- **Assumption:** temporarily accepted for design purposes but not yet confirmed.
- **Constraint:** a confirmed limit or obligation that the design must respect.
- **Preference:** something stakeholders would like, but which may be negotiable.
- **Open question:** information or a decision still needed.
- **Risk:** an uncertain condition that could affect the system or its objectives.

For example:

| Statement | Classification |
|---|---|
| A particular source has supplied usable observations during a documented test | Verified fact, limited to that test |
| The same source will remain available every day | Assumption until sustained availability is established |
| Only approved staff may publish sensitive reports | Constraint, if confirmed by the organisation's rules |
| Users would prefer reports before 9 AM | Preference until agreed as a requirement |
| Who pays for external data access? | Open question |
| A source may change its format without notice | Risk if this possibility is credible |

A statement can change category as evidence is obtained or decisions are made. Keep its status visible rather than silently upgrading an assumption into a fact.

### 9. Prioritise requirements

Not every requested feature is equally important. Requirements should be prioritised so that essential obligations are not obscured by desirable additions.

A simple prioritisation approach is:

- **Must have:** without this, the system does not solve the core problem or cannot operate acceptably.
- **Should have:** important, but a temporary or limited first version may work without it.
- **Could have:** useful improvement if resources and circumstances allow.
- **Not now:** explicitly deferred to avoid scope expansion.

This is a practical prioritisation aid, not a universal legal or engineering standard. Safety, privacy and other binding obligations should not be demoted simply because they are inconvenient or expensive.

### 10. Make requirements testable and traceable

A requirement should be clear enough that someone can later determine whether it has been satisfied.

Compare:

- Vague: "The system should provide reliable market information."
- More testable: "Each published price observation must include a product, market, location, unit, observation date and source reference; records missing required fields must be marked incomplete and excluded from verified-price summaries."

The second statement gives designers and evaluators something concrete to check.

Traceability means linking a requirement to the relevant design elements and later to tests or evidence.

A simple chain is:

**Problem → Desired outcome → Requirement → Architecture component or process → Validation evidence**

This chain helps answer why a component exists and what evidence will establish whether it fulfils its purpose.

Detailed test cases and evaluation metrics belong to Discipline 9. In this chapter, we establish the need for requirements to be testable and traceable.

### 11. Example: a requirements and context summary

The following is an illustrative summary for the agricultural intelligence case. It is not a verified statement about current market operations and does not commit the project to implementation.

| Area | Illustrative requirement or condition |
|---|---|
| Problem | Market information is fragmented and varies in reliability. |
| Desired outcome | Timely, traceable information about relevant market changes. |
| Functional need | Collect, classify, compare, investigate and report observations. |
| Quality need | Preserve source references, timestamps, units and uncertainty. |
| Users and actors | Analysts, authorised reviewers and information sources. |
| Data need | Product, market, location, price, unit, date, source and evidence status. |
| Constraint | Sensitive or external actions require appropriate authorisation. |
| Operating context | Multiple locations, different source formats and variable connectivity. |
| Dependency | External sources and human review where required. |
| Assumption | Some approved sources will provide sufficiently current information; this needs verification. |
| Open question | Which sources can be accessed reliably and under what terms? |
| Risk | Missing, delayed or misleading observations may distort analysis. |
| Must have | Clear provenance and distinction between verified and unverified information. |
| Should have | Coverage across additional markets after source reliability is established. |

### 12. Requirements review before architecture selection

Before moving to capability mapping, check:

1. Is the problem and desired outcome still clear?
2. Are functional requirements distinct from quality requirements?
3. Are constraints confirmed and their sources recorded?
4. Does the operating context reflect actual users, processes and conditions?
5. Are data requirements and dependencies visible?
6. Are assumptions, preferences, risks and open questions distinguished?
7. Have requirements been prioritised?
8. Can important requirements be tested or otherwise verified?
9. Can each requirement be traced to the problem it addresses?

If important requirements remain unknown, record them. Do not invent certainty merely to make the architecture look complete.

### Principles established

- Requirements describe what the system must do and the qualities it must satisfy.
- Constraints limit acceptable design choices.
- Operating context describes the real environment, people, information and conditions in which the system must work.
- Identify stakeholders, actors, data needs and external dependencies.
- Distinguish verified facts, assumptions, constraints, preferences, risks and open questions.
- Prioritise requirements without weakening binding safety, privacy or legal obligations.
- Make important requirements testable and traceable to architecture decisions and later validation.
- Keep unresolved information visible; do not invent certainty.


## 8.3 Capability and Responsibility Mapping

### Core question

Once we know what the system must achieve, how do we identify the capabilities it needs and decide which agents, conventional software components, automated processes or people should be responsible for providing them?

Requirements describe what the system must do. Capabilities describe what the system must be able to do to satisfy those requirements. Responsibility mapping assigns ownership for providing those capabilities and achieving the expected outcomes.

This step begins to turn requirements into an architecture, but it does not yet select particular tools, models or platforms.

### 1. What is a system capability?

A capability is an ability the system needs in order to achieve an outcome.

Examples in an agricultural intelligence system include:
- Collect market observations.
- Extract information from different source formats.
- Standardise prices, units and location references.
- Preserve source provenance.
- Assess evidence quality.
- Detect unusual price movements.
- Investigate possible causes.
- Calculate comparisons and trends.
- Prepare reports.
- Notify authorised users.
- Obtain approval for sensitive actions.

Capabilities describe what must be possible. They do not automatically specify which software, agent or technology will provide that ability.

### 2. Requirement, capability, responsibility, component and tool are different

These concepts are connected but should not be confused.

| Concept | Question it answers | Example |
|---|---|---|
| Requirement | What must the system achieve? | Every price observation must retain its source and unit. |
| Capability | What must the system be able to do? | Capture and preserve price-observation provenance. |
| Responsibility | Which part or actor is responsible for providing the capability or outcome? | The data-intake function must capture source and unit fields. |
| Component | What part of the system performs the work? | A collection service or a Market Data Collector agent. |
| Tool | What specific means can a component use? | A data connector, parser or approved information source. |

A capability is not a tool. A capability may be provided by one component, several cooperating components or a human process. A component may provide several capabilities.

For example, the capability to calculate price differences may be provided by a conventional computation component. It does not automatically require an AI agent.

### 3. Derive capabilities from requirements

Start with the requirements already identified in subsection 8.2.

Look for the actions and outcomes the system needs to support. Convert them into clear capability statements.

For example:

| Requirement | Capability derived from it |
|---|---|
| Collect price observations from approved sources. | Market observation collection |
| Record product, market, location, price, unit, date and source. | Structured extraction and metadata capture |
| Distinguish verified observations from uncertain reports. | Evidence assessment and status classification |
| Identify significant price changes. | Price comparison and change detection |
| Investigate unusual market movements. | Adaptive investigation and evidence synthesis |
| Produce reports with sources and uncertainty. | Evidence-based report preparation |
| Notify authorised users when conditions are met. | Controlled notification |
| Require approval before sensitive publication. | Human review and approval control |

One requirement may require several capabilities. Several requirements may also depend on the same capability.

Do not assume a one-to-one relationship between requirements and capabilities.

### 4. Break broad capabilities into manageable sub-capabilities

A broad statement such as "provide agricultural market intelligence" is too large to assign clearly.

It can be decomposed into smaller capabilities:

**Market intelligence**
- Collect observations.
- Extract and standardise information.
- Check completeness and consistency.
- Preserve provenance.
- Assess verification status.
- Compare observations across locations and time.
- Detect unusual changes.
- Investigate possible explanations.
- Prepare evidence-based findings.
- Distribute approved outputs.

Decomposition helps reveal dependencies and prevents important work from being hidden inside a broad label.

However, do not split every small action into a separate capability or agent. Decompose until ownership, inputs, outputs and expected results are clear enough for architecture decisions.

### 5. Identify the nature of each capability

Before allocating a capability, consider what kind of work it involves.

- **Deterministic or rule-based:** predictable operations with explicit rules, such as arithmetic, field validation, unit conversion and scheduled triggers.
- **Interpretive or probabilistic:** work involving varied inputs, classification, language interpretation or uncertain evidence.
- **Adaptive and goal-directed:** work where the next step depends on findings, context or feedback, such as investigating an unusual market event.
- **Human judgement or authority:** decisions that require a person's expertise, responsibility, approval or discretion.
- **Hybrid:** work that combines more than one of these kinds.

This classification helps identify where an agent may add value and where ordinary software or people are more appropriate.

For example, an AI agent might interpret an unstructured market announcement, while conventional computation calculates the percentage change in prices. A person may approve a consequential public alert.

### 6. Allocate capabilities to the appropriate system participants

Possible capability providers include:

1. **Conventional software components:** suitable for predictable, well-defined operations that can be expressed as explicit rules.
2. **Automation or workflows:** suitable for scheduled actions, triggers and known sequences.
3. **AI agents:** potentially suitable for interpretation, adaptive investigation, multi-step judgement and selecting among permitted actions.
4. **People:** appropriate where human expertise, accountability, discretion or formal approval is required.
5. **External systems or organisations:** may provide information or services on which the system depends.

A hybrid allocation is often appropriate. The aim is not to maximise the number of agents. It is to use the simplest suitable provider for each capability.

### 7. Example capability and responsibility map

The following map is an illustrative architecture exercise based on the agricultural intelligence example. It is not a final design or an implementation commitment.

| Requirement | Required capability | Candidate responsible part | Nature of work |
|---|---|---|---|
| Collect observations from approved sources | Market observation collection | Scheduled intake process; an agent only where source interpretation requires it | Automation / possibly interpretive |
| Capture required fields and source details | Extraction and metadata capture | Parser or extraction component | Deterministic / AI-assisted for varied formats |
| Standardise units and check required fields | Normalisation and validation | Conventional processing component | Deterministic |
| Distinguish evidence quality and uncertainty | Evidence assessment | Verification agent with defined criteria and escalation | Interpretive / human review for disputed cases |
| Detect significant price movements | Comparison and change detection | Calculation and monitoring component | Deterministic/statistical |
| Investigate unusual changes | Adaptive investigation and synthesis | Market investigation agent | Adaptive and goal-directed |
| Prepare a report with traceable evidence | Evidence-based report preparation | Reporting component or reporting agent | Hybrid |
| Approve sensitive publication | Formal review and approval | Authorised human reviewer | Human judgement / authority |
| Send approved notifications | Controlled notification | Notification automation after approval status is confirmed | Automation |

The allocation is deliberately mixed. It does not convert every row into a separate agent.

### 8. Map responsibilities, not just activity names

After identifying candidate capability providers, define who owns each responsibility.

A responsibility assignment should clarify:
- **Owner:** which component, agent or human role is accountable for delivering the defined output.
- **Contributors:** which other participants provide inputs or assistance.
- **Inputs:** what information or decisions are needed.
- **Output:** what result must be delivered.
- **Acceptance condition:** how the receiving part knows the output is usable.
- **Boundary:** what the owner is not permitted or expected to do.
- **Escalation:** where the work goes when it cannot be completed.

Try to give each defined outcome one clearly identified owner, even when several participants contribute. Shared contribution should not create ambiguity about who must ensure that the result is delivered or escalated.

This does not mean a single person or agent must perform every step. Ownership is about clarity of responsibility, not monopolising the work.

### 9. Check dependencies and handoffs

Capabilities rarely operate in isolation.

For example:
- Extraction depends on source information being accessible.
- Validation depends on agreed field definitions and units.
- Evidence assessment depends on provenance and collection details.
- Investigation depends on sufficiently reliable observations and relevant context.
- Reporting depends on analysis outputs and their evidence status.
- Publication depends on the required approval.

For each handoff, identify what is passed, in what form, with what status and who receives it. A downstream component must be able to tell whether an input is verified, uncertain, incomplete or rejected.

If a required capability has no owner, a dependency has no viable provider or an output has no receiving participant, the capability map is incomplete.

### 10. Avoid common mapping mistakes

- Treating every requirement as a separate agent.
- Assuming every capability needs AI.
- Selecting tools before understanding the capability.
- Assigning a broad responsibility that cannot be assessed.
- Giving multiple participants overlapping ownership with no clear decision rights.
- Ignoring human responsibilities and approval points.
- Forgetting that one capability may require several components.
- Forgetting that one component may provide multiple capabilities.
- Mapping an output without defining who consumes it.
- Treating an unverified information source as a dependable capability.

### 11. A practical mapping procedure

Use this sequence:

1. List the functional and quality requirements.
2. Identify the capabilities needed to satisfy each requirement.
3. Break broad capabilities into manageable sub-capabilities.
4. Classify each capability as deterministic, interpretive, adaptive, human-led or hybrid.
5. Identify a suitable candidate provider: conventional component, automation/workflow, agent, human or external dependency.
6. Assign one clear owner for each defined responsibility and identify contributors.
7. Define inputs, outputs, acceptance conditions, boundaries, dependencies and escalation.
8. Check that every requirement is covered and that no capability has been left without a viable owner.
9. Record unresolved questions and assumptions rather than filling gaps with invented decisions.

This produces a capability and responsibility map that can inform the high-level architecture choice in subsection 8.4.

### Principles established

- Requirements describe what must be achieved; capabilities describe what the system must be able to do.
- Responsibilities identify who or what owns delivery of a capability or outcome.
- Capabilities, components and tools are different concepts.
- Derive capabilities from requirements rather than starting with agents or tools.
- Decompose broad capabilities enough to make ownership and outputs clear, but avoid unnecessary fragmentation.
- Allocate work to the simplest suitable provider: conventional software, automation, agents, people or external services.
- Use agents where adaptive interpretation and goal-directed activity justify them, not by default.
- Give each defined outcome a clear owner while identifying contributors and dependencies.
- Define inputs, outputs, acceptance conditions, boundaries and escalation for important responsibilities.
- Verify that every requirement is covered and every capability has a viable provider.


## Continuation point

Continue with **8.4 Selecting the High-Level Architecture Shape**. Subsections 8.4–8.7 remain planned and have not yet been taught.
