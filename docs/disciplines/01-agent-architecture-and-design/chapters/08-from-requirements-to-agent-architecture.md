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
2. **8.2 Requirements, Constraints and Operating Context:** identify desired outcomes, users, environment, dependencies, risks and quality constraints.
3. **8.3 Capability and Responsibility Mapping:** translate requirements into capabilities and assign them to agents or conventional system components.
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


## Continuation point

Begin with **8.1 Problem Framing and Agent Suitability**. Do not treat the planned subsection headings as lessons already covered.
