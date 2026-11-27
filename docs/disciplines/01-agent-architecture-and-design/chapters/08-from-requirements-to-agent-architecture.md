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

The chapter is being taught progressively. Subsections marked Covered have been completed; the remaining entries are planned and have not yet been taught:

1. **8.1 Problem Framing and Agent Suitability:** Covered.
2. **8.2 Requirements, Constraints and Operating Context:** Covered.
3. **8.3 Capability and Responsibility Mapping:** Covered.
4. **8.4 Selecting the High-Level Architecture Shape:** Covered.
5. **8.5 Component Boundaries, Interfaces and Flows:** Covered.
6. **8.6 Integrating Autonomy, Authority and Human Oversight:** Covered.
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


## 8.4 Selecting the High-Level Architecture Shape

### Core question

Given the problem, requirements, operating context, and mapped capabilities, what overall arrangement of components is the simplest one that can satisfy the system's needs?

An architecture shape describes the broad way the system's main responsibilities and components are arranged. It helps decide whether the solution should use conventional software, one agent, an agent supported by automation, multiple agents, or a hybrid arrangement involving agents, software, workflows and people.

This is a high-level design decision. It is not yet a detailed design of agent communication, task delegation or orchestration. Those topics belong to Discipline 6.

### 1. Start with the simplest sufficient arrangement

The goal is not to create the most sophisticated architecture. It is to choose an arrangement that meets the requirements with acceptable complexity, cost, risk and operational effort.

Begin with the simplest plausible design. Add agents or separate components only when a requirement, responsibility, risk or operational need justifies that separation.

A system that uses five agents is not automatically better than a system using one agent and several conventional components.

### 2. Common high-level architecture shapes

#### A. Conventional software, workflow or automation without an agent

Some problems do not require an AI agent.

A conventional application, deterministic processing component, scheduled automation or fixed workflow may satisfy the requirements.

Examples:
- Calculate price differences using an explicit formula.
- Validate that a price record contains a commodity, unit, date and source.
- Run a scheduled data import.
- Send a report after a predefined approval event.

This is an important architecture option, not a failure to use AI.

#### B. Single-agent architecture

One agent is responsible for a bounded objective and may use the capabilities assigned to it.

This can be suitable when:
- The work has one coherent objective.
- Tasks are closely related and share much of the same context.
- One role can own the outcome clearly.
- The agent's authority and boundaries can be defined without becoming excessively broad.
- A single agent can perform the work within acceptable cost, latency and reliability limits.

A single agent does not mean a system with no other components. It may still rely on conventional software, data sources, interfaces and controlled capabilities. The distinction is that one agent performs the adaptive, goal-directed work.

#### C. One agent supported by workflows and automation

In this arrangement, a workflow or automation handles predictable stages, while an agent handles the portions that need interpretation or adaptive decisions.

For example:
- A scheduled process starts the work.
- Conventional components collect and validate structured records.
- An agent investigates unusual or ambiguous findings.
- A deterministic process formats the result.
- A person approves a sensitive publication.

This arrangement often avoids asking an agent to perform routine steps that can be handled more predictably by ordinary software.

#### D. Multi-agent architecture

Several agents have distinct roles and collaborate to achieve a broader system objective.

This may be appropriate when:
- Responsibilities are genuinely separable.
- Different tasks need distinct context, expertise or permissions.
- Work can be performed independently or in parallel.
- Independent review or separation of duties is important.
- Agents need different autonomy levels or operating lifecycles.
- The benefits of separation outweigh the extra coordination, communication and monitoring costs.

A multi-agent architecture introduces additional design obligations: clear ownership, information handoffs, dependency management, conflict handling, traceability and failure recovery. More agents create more interactions that can fail or become difficult to understand.

A multi-agent design should therefore solve a real separation or coordination problem. Do not create an agent for every small activity.

#### E. Hybrid system

A hybrid system combines agents with conventional software, automation, workflows, external services and human roles.

This is not simply another competing pattern alongside the others. It is a broad arrangement that can include one agent or multiple agents together with non-agent components.

Hybrid designs are useful when different parts of a problem have different characteristics. Predictable operations can remain deterministic, adaptive investigation can be assigned to an agent, and consequential decisions can remain under authorised human control.

In practical systems, a hybrid arrangement may be more suitable than trying to make the entire process autonomous.

### 3. A high-level view of multi-agent organisation

When several agents are justified, their broad authority and coordination may be arranged in different ways.

- **Coordinator-led arrangement:** a designated coordinator assigns or tracks work and gathers results from specialised agents.
- **Distributed or peer arrangement:** agents with distinct responsibilities cooperate through agreed relationships, without one agent controlling every operational decision.
- **Mixed arrangement:** some tasks are coordinated centrally while other interactions occur directly between specialised agents or through shared processes.

These labels describe high-level organisational choices only. They do not prescribe how messages, delegation, consensus or conflict resolution must be implemented. Detailed orchestration and communication engineering belong to Discipline 6; distributed authority and self-governing rules are explored in Agentic Governance.

A distributed arrangement does not mean that accountability disappears. Authority, ownership, constraints and escalation still need to be defined.

### 4. How do we decide whether one agent is enough?

A single agent may be sufficient when:
- The objective is coherent and bounded.
- The work shares a common context.
- The tasks are closely connected.
- One role can own the outputs.
- Permissions do not need substantial separation.
- The required workload can be handled within acceptable limits.

Consider a Market Investigation Agent that examines a reported price spike. It may collect relevant approved observations, compare time periods, investigate possible explanations and prepare a finding. If the work is tightly connected and the same agent can perform it safely, splitting each step into a separate agent may add unnecessary overhead.

### 5. When is splitting into multiple agents justified?

Separate agents may be justified when there is a real architectural reason, such as:

1. **Distinct responsibilities:** each function has a clear and independently meaningful outcome.
2. **Different information contexts:** one role needs a different set of information or a different operating context.
3. **Different authority or risk:** one function must not have the permissions needed by another.
4. **Parallel work:** independent investigations can proceed at the same time.
5. **Independent lifecycle or scaling:** one function must be updated, paused or scaled separately.
6. **Independent checking:** a separate role is needed to review or challenge another component's output.
7. **Operational isolation:** failure or excessive workload in one function should not necessarily stop another.

These are decision factors, not a checklist requiring every condition. A single strong reason may justify separation when the benefit is significant.

However, every additional agent adds communication, handoff, monitoring, testing, configuration and failure-management overhead. The separation must be worth that cost.

### 6. Architecture shape and autonomy are separate decisions

Do not confuse the number of agents with the autonomy of the system.

- A single agent can operate with low or high autonomy within its permitted authority.
- A multi-agent system can operate under strict human approval and supervision.
- A hybrid system can automate routine work while requiring human approval for consequential actions.
- Distributed agents do not automatically have equal authority or unrestricted freedom.

Architecture shape answers: **How are the main components and responsibilities arranged?**

Autonomy design answers: **How independently may each agent decide and act within its authority?**

The two decisions influence each other, but neither determines the other automatically.

### 7. Compare architecture shapes against the requirements

Use a simple comparison before committing to an arrangement.

| Consideration | Single agent | Agent plus workflow | Multi-agent | Hybrid |
|---|---|---|---|---|
| Number of agents | One | Usually one or a small number | Several | One or several |
| Predictable tasks | Agent may not be the best provider | Workflow handles them | Can be assigned to non-agent components too | Often handled by conventional components |
| Adaptive work | One agent handles it | Agent handles selected stages | Several specialised agents may handle separate parts | Allocated to the most suitable participants |
| Coordination overhead | Lower | Low to moderate | Higher | Depends on the combination |
| Separation of permissions | Can become broad if poorly designed | Can isolate fixed stages | Can separate agent permissions | Can combine agent and human controls |
| Main risk to watch | One agent becomes overloaded or over-scoped | Poor handoff between fixed and adaptive stages | Coordination failures and unclear ownership | Inconsistent interfaces and fragmented operations |

The table is qualitative. It is not a scoring formula and does not establish that one architecture is universally best.

### 8. Apply the options to agricultural intelligence

The agricultural intelligence example contains different kinds of work:

- Scheduled collection from known sources.
- Parsing and standardisation of structured observations.
- AI-assisted interpretation of varied source material.
- Deterministic price calculations and validation.
- Investigation of unusual market movements.
- Human review of consequential findings.
- Controlled distribution of approved reports.

A plausible high-level starting arrangement is a **hybrid system**:

1. Scheduled automation initiates routine collection.
2. Conventional components parse, standardise and validate structured observations.
3. An AI agent is used where varied information needs interpretation or an investigation requires adaptive steps.
4. Calculation and threshold checks use appropriate deterministic or statistical components.
5. An authorised person reviews sensitive or consequential findings.
6. Automation distributes outputs only after the required approval condition is satisfied.

A separate verification agent or additional specialised agents may be justified later if independent responsibilities, authority separation, workload or scale warrant them. The current learning exercise does not require us to create them in advance.

This is an illustrative architecture shape, not an approved build plan or a claim that the sources, data and operating requirements have already been verified.

### 9. A practical architecture-selection procedure

1. Start with the problem, requirements and capability map.
2. Identify which work is deterministic, interpretive, adaptive, human-led or externally provided.
3. Sketch the simplest arrangement that could satisfy the requirements.
4. Decide whether one agent can safely and clearly own the adaptive work.
5. Identify any genuine reasons to separate responsibilities into multiple agents.
6. Add workflows, automation, conventional components and human approval where they provide a better fit.
7. Compare the candidate arrangement against quality requirements, constraints, dependencies, risk, cost and operational complexity.
8. Check that every important capability has an owner and that boundaries and handoffs are understandable.
9. Record why the selected shape is preferable to the simpler alternatives, and preserve unresolved questions.

The selected shape remains provisional until its interfaces, information flows and control boundaries are described in the next subsection.

### 10. Common architecture-selection mistakes

- Assuming that every capability needs its own agent.
- Selecting a multi-agent design because it appears more advanced.
- Putting predictable calculations inside an agent without a reason.
- Giving one agent unrelated responsibilities and excessively broad permissions.
- Splitting tightly connected tasks into agents that constantly depend on each other.
- Ignoring communication, coordination, evaluation and maintenance overhead.
- Assuming a coordinator automatically has authority to override every other agent.
- Treating distributed operation as freedom from accountability.
- Selecting an architecture before checking whether it can satisfy the actual requirements.

### Principles established

- Select the simplest architecture shape that satisfies the requirements.
- Conventional software, automation and workflows remain valid architecture choices even in an agentic system.
- Use a single agent when the adaptive work is coherent, bounded and manageable within one responsibility.
- Introduce multiple agents only when separation, specialisation, parallelism, independent authority, review or lifecycle benefits justify the overhead.
- Hybrid systems can combine deterministic components, agents, external services and people.
- Architecture shape and autonomy level are separate design decisions.
- Coordinator-led, distributed and mixed arrangements are high-level organisational choices; their detailed coordination belongs in later disciplines.
- A distributed system still needs explicit authority, ownership, boundaries and accountability.
- Record the reasons for the selected architecture and the alternatives rejected.


## 8.5 Component Boundaries, Interfaces and Flows

### Core question

Once the high-level architecture shape is selected, how do we define where each component's responsibility begins and ends, how components exchange information, and how work and control move through the system?

A component boundary defines the responsibility and scope assigned to a part of the system. An interface defines the agreed way that component interacts with another. A flow describes how information, work or control moves between components.

These decisions make the architecture understandable and help prevent components from becoming unnecessarily dependent on one another.

### 1. What is a component boundary?

A component is a distinguishable part of the overall system that performs one or more related functions. It may be an AI agent, conventional software service, workflow, data store, external system or human-operated function.

A component boundary clarifies:
- What the component is responsible for.
- What work it does not own.
- What inputs it is allowed or expected to receive.
- What outputs it must provide.
- Which other components it may interact with.
- What authority and restrictions apply to it.
- What conditions require it to stop, return an error or escalate.

A boundary is a design responsibility boundary. It does not necessarily mean a separate computer, application, process, container or agent. Those implementation decisions come later.

One component may contain several internal functions. Conversely, a single capability may require several components to cooperate.

### 2. Give each component a coherent responsibility

A component should have a clear purpose and a responsibility that can be understood independently.

For example, in the agricultural intelligence system:
- The intake component receives observations from approved sources.
- The normalisation component standardises fields and units.
- The evidence assessment function assigns evidence status according to defined criteria.
- The monitoring component identifies changes that meet agreed conditions.
- The investigation agent examines unusual or ambiguous findings.
- The approval function handles decisions reserved for authorised people.
- The reporting and notification components prepare and distribute approved outputs.

These are candidate responsibilities, not a requirement to implement each as a separate service or agent.

Avoid giving a component unrelated duties simply because it is convenient to place them together. Also avoid splitting one small responsibility into many components without a meaningful reason.

### 3. Understand cohesion and coupling

Two useful architecture concepts help assess component boundaries.

- **Cohesion** describes how closely the responsibilities inside a component belong together. A component with high cohesion has a clear, focused purpose.
- **Coupling** describes how strongly one component depends on other components. Excessive coupling means a change or failure in one part can cause widespread effects elsewhere.

A useful design aim is:

**High cohesion within components and manageable coupling between components.**

For example, a unit-normalisation component should focus on standardising measurement units. It should not also decide which commercial opportunities the system should pursue.

If many components need to know each other's internal details, the boundaries may be unclear or the interfaces too tightly connected.

Some dependencies are unavoidable. The aim is not zero coupling, but dependencies that are explicit, limited and manageable.

### 4. What is an interface?

An interface is the agreed way one component interacts with another.

It describes what a component provides or requires without exposing every detail of how it performs its internal work.

An interface may support:
- Supplying information to another component.
- Requesting a task or service.
- Receiving a result or status.
- Notifying another component that an event occurred.
- Requesting a decision or approval.
- Reporting an error or inability to proceed.

An interface is not necessarily a software API. It may be a message, a shared record, a human approval step, a file exchange or another defined interaction. Specific interface technologies and integration mechanisms belong to Discipline 4.

### 5. Define an interface contract

Components should not rely on vague assumptions about what another component will provide.

An interface contract establishes the expectations for an interaction. Depending on the type of exchange, it may define:

1. **Producer and consumer:** which component provides the information or service and which component receives or uses it.
2. **Purpose:** why the interaction occurs.
3. **Input:** what information, request or trigger is supplied.
4. **Output:** what result, response or status is returned.
5. **Structure and meaning:** required fields, data types, units, definitions and interpretation.
6. **Evidence and provenance:** source, timestamp, verification status and relevant limitations.
7. **Conditions:** when the interaction is valid and what preconditions must be met.
8. **Authority and access:** who is allowed to initiate, receive or perform the interaction.
9. **Failure behaviour:** how errors, missing information, delays or rejected requests are represented.
10. **Completion or acknowledgement:** how the parties know the interaction was received, accepted, completed or rejected.
11. **Version and compatibility:** how changes to the interaction are identified and managed.

The contract should contain enough detail to make the interaction reliable, but should not duplicate every internal implementation detail of either component.

### 6. Information flow and control flow are different

Architecture diagrams often show components connected by arrows. But an arrow can represent different kinds of movement.

**Information flow** describes how data, evidence, requests or results move between components.

Example:
- The intake component sends price observations to normalisation.
- Normalisation sends standardised records to evidence assessment.
- The investigation agent sends findings to reporting.

**Control flow** describes how work is triggered, directed, approved, paused or allowed to proceed.

Example:
- A scheduled trigger starts collection.
- A significant-change condition requests an investigation.
- A sensitive report is held until an authorised reviewer approves it.
- An approval result allows the notification process to proceed.

The two flows may travel between the same components, but they answer different questions. An architecture should make both understandable.

### 7. Example information and control flows

Consider this illustrative agricultural intelligence arrangement:

**Information flow**

1. Approved sources provide observations to intake.
2. Intake passes captured observations and source details to normalisation.
3. Normalisation produces standardised records for evidence assessment.
4. Evidence assessment provides records with verification status to monitoring and analysis.
5. When an investigation is required, relevant evidence is supplied to the investigation agent.
6. The investigation agent returns findings, source references and uncertainty to reporting.
7. The report is delivered to an authorised reviewer and, after approval, to the notification function.

**Control flow**

1. A schedule or approved trigger initiates collection.
2. Validation and evidence checks determine whether records can proceed.
3. A defined condition triggers an investigation.
4. The investigation may be marked complete, incomplete or requiring escalation.
5. Sensitive publication is held pending the required approval.
6. An approved result permits distribution; a rejected result stops publication and records the decision.

This distinction prevents the design from showing only where information travels while leaving unclear who or what controls the next action.

### 8. Example component boundary map

The following is an architecture-level illustration. It does not commit the project to separate deployments or specific technology.

| Component or participant | Owns | Receives | Provides | Does not own |
|---|---|---|---|---|
| Intake | Capturing observations from approved sources | Source content and collection trigger | Raw observations with source details | Final verification or market interpretation |
| Normalisation | Standardising fields, formats and units | Raw observations | Standardised records and validation errors | Deciding whether a market claim is true |
| Evidence assessment | Assessing evidence status against defined criteria | Standardised records and provenance | Verified, unverified, rejected or unresolved status | Changing the original source record |
| Monitoring and calculation | Applying defined comparisons and thresholds | Eligible observations and reference data | Calculated changes and investigation triggers | Explaining every cause of a change |
| Investigation agent | Adaptive investigation of assigned cases | Trigger, relevant evidence and task scope | Findings, sources, assumptions and uncertainty | Publishing sensitive findings or committing funds |
| Human approval | Making reserved approval decisions | Proposed report and supporting evidence | Approval, rejection or request for revision | Performing all routine data processing |
| Reporting and notification | Preparing and distributing outputs under policy | Findings and approval status | Reports and delivery status | Approving its own restricted publication |

One actual component may perform more than one row's work if the responsibilities are closely related and the design remains clear. A row does not automatically mean a separate agent.

### 9. Avoid circular and hidden dependencies

A dependency exists when one component needs another component's input, service or decision to continue.

A straightforward chain might be:
- Intake → Normalisation → Evidence assessment → Analysis.

A problematic circular dependency might look like:
- Component A cannot finish without B.
- B cannot finish without C.
- C cannot finish without A.

Such cycles can cause deadlocks, repeated handoffs or unclear ownership unless they are deliberately designed and controlled.

Also watch for hidden dependencies: a component that appears independent but actually relies on an undocumented data field, a particular output format, a person being available or an external service behaving in a specific way.

Important dependencies should be recorded, including what happens when the dependency is unavailable.

### 10. Boundaries should preserve evidence and authority

When information moves between components, its meaning and status must not be lost.

For example, an unverified market report should not become a verified observation merely because it passed through a normalisation component.

Interfaces should preserve relevant:
- Source references.
- Observation and processing timestamps.
- Units and definitions.
- Verification status.
- Uncertainty and limitations.
- Identity of the producing component where relevant.

Interactions must also respect the authority and boundaries already assigned to each participant. A component receiving a request must not interpret that request as permission to perform actions outside its own authority.

### 11. What happens when an interface fails?

A component boundary should include expectations for unsuccessful interactions.

Examples include:
- Required input is missing or malformed.
- A response arrives too late.
- The receiving component rejects the input.
- A downstream component is unavailable.
- Two components interpret a field differently.
- An approval is denied or never arrives.
- A result is incomplete or contains unresolved evidence.

The architecture should establish whether the affected work is retried, paused, rejected, sent to an alternative approved route or escalated. A failed handoff should not be silently treated as successful completion.

Detailed retry, messaging, orchestration and recovery engineering will be studied in later disciplines. At this stage, the architecture must at least identify the dependency and the required failure outcome.

### 12. A practical boundary and interface review

For each important component, ask:

1. Is its purpose and responsibility clear?
2. What does it explicitly not own?
3. What inputs does it receive, and from whom?
4. What outputs does it provide, and to whom?
5. Are the meaning, format, units and evidence status clear?
6. Are information flow and control flow both understood?
7. Are the interaction's authority and approval conditions explicit?
8. Are dependencies and failure responses visible?
9. Can one component change internally without unnecessarily disrupting others?
10. Is there any circular, hidden or unnecessary dependency?

If these questions cannot be answered, the architecture boundaries or interfaces need further work.

### Principles established

- A component boundary defines responsibility and scope, not necessarily a separate deployment or agent.
- Give components coherent purposes and clear ownership.
- Aim for high cohesion and manageable coupling.
- An interface defines an agreed interaction between components; it is not necessarily a software API.
- Define interface contracts for important exchanges.
- Distinguish information flow from control flow.
- Preserve provenance, evidence status, uncertainty and units across handoffs.
- Make dependencies, permissions, approvals and failure handling explicit.
- Avoid circular, hidden and unnecessary dependencies.
- Do not assume every component is a separate agent or must use a particular technology.


## 8.6 Integrating Autonomy, Authority and Human Oversight

### Core question

How do we decide how independently each component or agent may operate, what it is allowed to do, and where people must supervise, approve or intervene?

Architecture must bring three related but distinct decisions together:

- **Autonomy:** how independently an agent may decide and act within its permitted scope.
- **Authority:** which decisions, information and actions the system permits it to access or perform.
- **Human oversight:** how people review, approve, supervise, constrain or intervene in the system's operation.

A design is incomplete if it defines autonomy without authority, grants authority without considering consequences, or names a human approver without ensuring that meaningful oversight is possible.

### 1. Autonomy, authority and oversight are not interchangeable

| Concept | Main question | Example |
|---|---|---|
| Autonomy | How independently may the agent operate? | May it investigate a price movement without waiting for approval at every step? |
| Authority | What is it actually permitted to decide or do? | May it read approved sources, create records or send notifications? |
| Human oversight | Where and how can people supervise or control the work? | Must a reviewer approve a sensitive public alert? |

An agent may have high autonomy within a narrow authority. It may independently perform routine data collection but have no access to payment functions or permission to publish sensitive claims.

Likewise, a system with several agents may still require human approval for important actions. The number of agents does not determine the degree of autonomy.

### 2. Reuse the project's five-level autonomy framework

Chapter 5 introduced a five-level teaching framework. It is a project framework, not a universal industry standard.

| Level | Name | Operating arrangement |
|---:|---|---|
| 1 | Advisory | The agent analyses information and recommends; a human decides. |
| 2 | Assisted execution | The agent prepares an action but waits for human approval before executing it. |
| 3 | Conditional autonomy | The agent executes approved categories of work within limits and escalates unusual or high-risk cases. |
| 4 | High autonomy | The agent plans, executes, monitors and adjusts work independently within established policies. |
| 5 | Full operational autonomy | The agent manages complex, ongoing objectives with minimal routine human intervention. |

These levels should not be assigned merely because an agent is technically capable of operating at that level. The level must be justified by its responsibility, the permitted actions, demonstrated reliability, operating conditions and potential consequences.

### 3. Assign autonomy according to responsibility and consequences

Different agents in the same system should not automatically receive equal autonomy.

Consider the agricultural intelligence example:

| Agent or function | Responsibility | Illustrative autonomy starting point | Oversight consideration |
|---|---|---:|---|
| Market Data Collector | Collect approved market observations | Level 4 for routine collection within its scope | Monitor source coverage, data quality and exceptions |
| Information Verification Agent | Assess evidence status | Level 3 | Escalate disputed or insufficient evidence |
| Market Analyst | Analyse price movements and patterns | Level 4 for bounded analysis | Review important conclusions and preserve evidence |
| Opportunity Discovery Agent | Identify and recommend opportunities | Level 2–3 | Human review before external commitments |
| Reporting Agent | Prepare and distribute authorised reports | Level 3 | Approval required for sensitive or public reports |
| Procurement or payment function | Commit funds or enter transactions | Human-authorised execution | Strong approval and transaction controls |

These are illustrative starting points based on the responsibilities described in earlier lessons, not approved production settings. Actual levels must be determined from verified requirements, real-world risk, operating evidence and authorisation rules.

A useful rule is to consider both the likelihood of an error and the severity of its consequences. Actions that affect money, legal commitments, personal data, public reputation, safety or important records generally warrant stronger controls than reversible, low-impact internal work.

### 4. Distinguish the agent's autonomy from the authority of an action

An agent may be autonomous in one activity and tightly constrained in another.

For example, the Market Analyst may independently:
- Compare approved market observations.
- Identify unusual price movements.
- Request additional approved evidence.
- Prepare an internal analytical report.

But it may be prohibited from:
- Changing original source records.
- Publishing a public warning without approval.
- Contacting external buyers without authorisation.
- Committing money or entering a contract.

Therefore, autonomy should not be treated as one unrestricted setting for the entire agent. The architecture should consider the actions the agent can take and apply different permissions and approval conditions to different action categories.

Where practical, high-impact permissions should be enforced by the surrounding system rather than relying only on the model's instructions.

### 5. Three human-oversight arrangements

Chapter 5 introduced three useful terms.

#### A. Human-in-the-loop

A person is required to participate in a decision or action before the process can proceed.

Example: an Opportunity Discovery Agent identifies a proposed purchase. An authorised person reviews the evidence and approves or rejects the transaction before it can be committed.

Use this where a decision requires human judgement, formal authorisation or a deliberate check before a consequential action.

#### B. Human-on-the-loop

The agent or system operates independently within approved limits while a person supervises its activity and can intervene.

Example: a Market Data Collector gathers and processes routine observations automatically. An operator monitors its coverage, failures and unusual behaviour and can pause it when required.

This is suitable for bounded activities where continuous approval of every routine step would add little value, but intervention must remain possible.

#### C. Human-out-of-the-loop

The system operates without routine human participation in each decision or action.

This may be appropriate only for sufficiently bounded, tested and controlled activities where the consequences of failure are acceptable and recovery arrangements are adequate.

It should not be interpreted as the absence of organisational accountability, governance or emergency intervention arrangements. A process can operate without routine human approval while still being subject to defined ownership, monitoring and review.

### 6. Human oversight must be meaningful

Merely adding an approval button or naming a human reviewer does not guarantee effective oversight.

For oversight to be meaningful, the person should have:

1. **Relevant information:** enough evidence, context and uncertainty to understand what is being proposed.
2. **Competence:** sufficient knowledge to assess the action or a suitable escalation route when specialist expertise is needed.
3. **Time:** a realistic opportunity to review before the action occurs.
4. **Authority:** the actual ability to approve, reject, pause or escalate.
5. **Visibility:** access to the status and relevant history of the agent's work.
6. **Intervention capability:** a practical way to stop or constrain the system when necessary.
7. **Clear responsibility:** a defined understanding of what the reviewer is being asked to decide and what remains the responsibility of the system operator or organisation.

If reviewers receive too many requests, have too little information or cannot realistically reject a proposal, oversight may become a rubber-stamp exercise.

The architecture should therefore avoid unnecessary approvals while preserving meaningful control at important decision points.

### 7. Place approval gates at consequential boundaries

An approval gate is a control point that prevents an action from proceeding until the required authorisation is received.

Examples:
- Approval before publishing a sensitive public report.
- Approval before sending an external commercial offer.
- Approval before committing funds.
- Approval before modifying or deleting important records.
- Approval before changing high-impact permissions or operating policies.

Not every internal action requires an approval gate. Routine, low-risk activities may operate within pre-approved limits.

For each gate, define:
- Which action is being held.
- What evidence the reviewer receives.
- Who is authorised to approve.
- What counts as approval, rejection or a request for revision.
- What happens if nobody responds.
- How the decision is recorded.
- Whether the approval expires or must be renewed if the proposal changes.

An agent must not interpret silence, a timeout or an unavailable reviewer as approval unless a formally approved policy explicitly defines a safe alternative for that situation.

### 8. Design escalation and intervention paths

An agent should know when it can proceed, when it must stop and when it must ask for help.

Escalation conditions may include:
- Conflicting or insufficient evidence.
- A request outside the agent's scope.
- A proposed action above an approved threshold.
- An unexpected change in risk.
- A required permission or approval being unavailable.
- Repeated failures or abnormal behaviour.
- A potential safety, privacy or security incident.

A useful architecture-level escalation path identifies:
1. The condition that triggers escalation.
2. The action the agent must stop or hold.
3. The person or authorised component that receives the escalation.
4. The evidence and context provided.
5. The decision or information required to resume.
6. What happens if no response is received within the permitted period.

The system should fail safely when a required decision is unavailable. It should not widen its own permissions or continue a restricted action simply to complete its objective.

### 9. Autonomy should be bounded by operating conditions

An autonomy level is not necessarily a permanent guarantee that the agent can always operate in the same way.

The architecture may define conditions that reduce or suspend autonomy, such as:
- A sharp increase in error rates.
- Missing or unreliable input data.
- An unexpected source or environment change.
- Repeated failed actions.
- Loss of a critical dependency.
- A security or policy alert.
- Expired credentials or approvals.

For example, a collector may normally operate at Level 4 for routine collection. If its source data becomes inconsistent or its validation checks fail repeatedly, the system may pause it or restrict it to collecting raw records pending review.

Any mechanism that reduces or restores autonomy must itself be governed. An agent should not independently promote itself to a higher autonomy level. Restoration should follow defined checks and approval rules appropriate to the risk.

### 10. Map actions to autonomy, authority and oversight

Instead of assigning a single autonomy label and assuming that it covers every activity, examine the important action categories.

| Action | Permitted authority | Autonomy arrangement | Human control |
|---|---|---|---|
| Read approved market data | Read assigned sources | Independent within scope | Monitor access and exceptions |
| Calculate price differences | Process approved records | Independent | Review through quality checks |
| Investigate an unusual price movement | Conduct bounded investigation | Conditional or high autonomy, depending on evidence and reliability | Escalate uncertainty or unusual cases |
| Prepare an internal report | Create draft report | Independent within format and scope | Review according to report risk |
| Publish a sensitive public alert | No independent publication permission | Approval required | Authorised reviewer approves |
| Commit funds | No autonomous spending authority in this example | Human-authorised execution | Explicit transaction approval |

This action-level view helps expose gaps that a broad label such as "Level 4 agent" might hide.

### 11. Review the integrated control design

Before accepting an architecture, check:

1. Does each agent's autonomy match its assigned responsibility and potential consequences?
2. Are decision, data, action and resource permissions explicit?
3. Are high-impact and irreversible actions separately controlled?
4. Are human approval points placed where they add necessary protection?
5. Do reviewers have the information, competence, time and authority to intervene?
6. Are escalation conditions and recipients defined?
7. Can the system pause, restrict or stop an agent safely?
8. Can an agent change or increase its own permissions or autonomy? It should not be able to do so unilaterally.
9. Are actions and approvals traceable for later review?
10. Are degraded operation and loss of oversight handled safely?

### Principles established

- Autonomy, authority and human oversight are distinct but must be designed together.
- Different agents and different action categories may require different autonomy levels.
- Match autonomy to responsibility, demonstrated reliability, operating conditions and potential consequences.
- High autonomy does not imply broad authority.
- Human-in-the-loop, human-on-the-loop and human-out-of-the-loop describe different oversight arrangements.
- Human oversight must be meaningful: reviewers need information, competence, time, authority and practical intervention capability.
- Place approval gates at consequential boundaries, not indiscriminately on every action.
- Define escalation, timeout and safe-stop behaviour.
- Conditions may reduce or suspend autonomy, but an agent must not unilaterally increase its own authority or autonomy.
- Record decisions, permissions, approvals and interventions so the control design remains accountable.


## Continuation point

Continue with **8.7 Producing and Reviewing an Architecture Blueprint**. Subsection 8.7 remains planned and has not yet been taught.
