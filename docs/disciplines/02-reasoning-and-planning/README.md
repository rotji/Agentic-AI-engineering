# Discipline 2 — Reasoning and Planning

**Status:** In progress; Chapters 1–2 complete, Chapter 3 in progress (3.1–3.2 covered).

## 1. Purpose

Study how an agent moves from an assigned objective to a reasoned understanding of the problem, a set of possible actions, a feasible plan and an appropriate next decision.

Reasoning and planning are related, but they are not identical:

- **Reasoning** is the process of interpreting information, drawing or assessing conclusions, forming explanations and working through a problem.
- **Planning** is the process of deciding what steps, in what order and under what conditions, could achieve an objective.
- **Decision-making** selects among available options using goals, constraints, evidence, risk and priorities.
- **Execution** carries out the selected action or plan. Detailed execution loops belong to Discipline 5.

These activities influence one another. New information can change a conclusion, a plan can reveal missing information, and an observed result can require a decision to revise the plan.

This discipline focuses on reasoning and planning capabilities without prematurely choosing a model, framework, tool or platform. Concepts will be connected to the agricultural pilot and practical design questions. When a concrete requirement arises, we may investigate existing solutions, assemble them or build a justified missing capability without waiting for all ten chapters or all 13 disciplines to be completed.

## 2. Learning outcomes

By the end of this discipline, the learner should be able to:

1. Explain the difference and relationship between reasoning, planning, decision-making and execution.
2. Interpret an objective and formulate a problem with clear goals, success conditions and constraints.
3. Recognise and use different forms of inference, while understanding their limitations.
4. Represent relevant states, actions, preconditions, effects and constraints in a planning problem.
5. Decompose a broad objective into manageable subgoals and dependent tasks.
6. Compare planning strategies and understand how search and heuristics support plan generation.
7. Select among candidate actions using feasibility, priorities, expected benefit, cost and risk.
8. Plan when information is incomplete or outcomes are uncertain.
9. Check whether a proposed plan is coherent, feasible and within the agent's assigned authority.
10. Recognise when a plan needs revision, when to stop and when to ask for clarification or escalate.

## 3. Learning sequence

The discipline is organised into ten chapters. This is the initial learning sequence; it may be refined when a genuine conceptual gap is identified. The detailed lessons will be documented progressively rather than treated as already completed.

### Chapter 1 — Foundations of Reasoning and Planning

Establish the core concepts and how they fit into an agentic system.

Planned subsections:
- **1.1 What Reasoning and Planning Mean in Agentic Systems:** Covered.
- **1.2 Reasoning vs Planning vs Decision-Making vs Execution:** Covered.
- **1.3 How Reasoning and Planning Fit into an Agent's Operation:** Covered.
- **1.4 Deliberative and Reactive Behaviour:** Covered.

### Chapter 2 — Goals, Instructions and Problem Formulation

Understand how an agent interprets an objective and turns it into a problem it can work on.

Planned subsections:
- **2.1 Objectives, Goals and Desired Outcomes:** Covered.
- **2.2 Interpreting Instructions and Identifying Intent:** Covered.
- **2.3 Goal States and Conditions for Success:** Covered.
- **2.4 Constraints, Priorities and Conflicting Objectives:** Covered.
- **2.5 Ambiguity, Missing Requirements and Clarification:** Covered.

### Chapter 3 — Reasoning Patterns and Inference

Study ways of drawing conclusions, forming explanations and assessing evidence.

Planned subsections:
- **3.1 Deductive Reasoning:** Covered.
- **3.2 Inductive Reasoning:** Covered.
- **3.3 Abductive Reasoning and Explanation**
- **3.4 Causal Reasoning, Correlation and Analogy**
- **3.5 Hypotheses, Evidence, Confidence and Limitations**

### Chapter 4 — Representing Problems, States and Actions

Learn how to describe the situation an agent is reasoning about and the possible changes its actions may produce.

Planned subsections:
- **4.1 Problem and Environment Representation**
- **4.2 Current State, Goal State and State Changes**
- **4.3 Actions, Preconditions and Effects**
- **4.4 Constraints, Resources, Time and Dependencies**
- **4.5 State Spaces, Trees and Graphs as Planning Representations**

### Chapter 5 — Task Decomposition and Hierarchical Planning

Learn how to turn a broad objective into smaller, manageable and related parts.

Planned subsections:
- **5.1 From Objectives to Subgoals**
- **5.2 Task Decomposition Methods**
- **5.3 Task Ordering, Dependencies and Parallel Activities**
- **5.4 Hierarchical Plans and Levels of Abstraction**
- **5.5 Choosing the Right Decomposition Granularity and Knowing When to Stop**

### Chapter 6 — Planning Strategies and Search

Understand different approaches for constructing a path from the current state to a goal.

Planned subsections:
- **6.1 Forward and Backward Planning**
- **6.2 Means–Ends Analysis**
- **6.3 Hierarchical and Partial-Order Planning**
- **6.4 State-Space Search and Plan Exploration**
- **6.5 Heuristics and Search Trade-offs**
- **6.6 Choosing Between Deliberative and Reactive Planning**

### Chapter 7 — Decision-Making and Action Selection

Study how an agent chooses among possible actions and balances competing considerations.

Planned subsections:
- **7.1 Generating Candidate Actions**
- **7.2 Action Feasibility and Constraint Checking**
- **7.3 Priorities and Competing Objectives**
- **7.4 Cost, Benefit, Utility and Risk**
- **7.5 Selecting an Action, Deferring, Asking or Taking No Action**

### Chapter 8 — Reasoning and Planning Under Uncertainty

Understand how to plan when information is incomplete, ambiguous or changing and when actions may have uncertain outcomes.

Planned subsections:
- **8.1 Incomplete Information and Partial Observability**
- **8.2 Assumptions, Beliefs and Confidence**
- **8.3 Scenarios, Contingencies and Alternative Plans**
- **8.4 Information-Gathering Actions and the Value of Information**
- **8.5 Risk-Aware Planning and Uncertain Outcomes**

### Chapter 9 — Plan Validation and Feasibility

Learn how to examine a proposed plan before it is carried out.

Planned subsections:
- **9.1 Checking Preconditions, Ordering and Dependencies**
- **9.2 Resource, Time and Constraint Feasibility**
- **9.3 Side Effects, Failure Points and Reversibility**
- **9.4 Comparing Alternatives and Assessing Plan Robustness**
- **9.5 Checking Plans Against Goals, Boundaries and Assigned Authority**

### Chapter 10 — Replanning, Adaptation and Stopping Conditions

Study how an agent responds when the original plan no longer fits the situation.

Planned subsections:
- **10.1 Expected Outcomes vs Observed Results**
- **10.2 Events and Conditions That Trigger Replanning**
- **10.3 Revising Part of a Plan or Rebuilding It**
- **10.4 Retries, Alternative Actions, Abandonment and Escalation**
- **10.5 Success, Failure, Time, Resource and Stopping Conditions**
- **10.6 Preserving Decisions, Assumptions and Plan Changes**

## 4. Scope boundaries and connections to other disciplines

Reasoning and planning are central agent capabilities, but they do not replace the other engineering disciplines.

| Related discipline | What it contributes | Boundary for this discipline |
|---|---|---|
| **1. Agent Architecture and Design** | Defines the agent's purpose, role, responsibilities, boundaries and place in the system. | This discipline uses those architectural limits when reasoning and planning. |
| **3. Context, Memory and Knowledge** | Provides context, stored information, knowledge sources and retrieval. | This discipline studies how reasoning uses information, not how persistent memory or retrieval systems are engineered. |
| **4. Tools and Environment Engineering** | Provides available tools, interfaces and permitted environmental actions. | This discipline may choose an abstract action; detailed tool selection, integration and operation belong there. |
| **5. Execution and Loop Engineering** | Carries out actions, observes results and manages runtime feedback cycles. | This discipline forms and revises plans; execution mechanics are studied later. |
| **6. Orchestration and Multi-Agent Systems** | Coordinates agents, delegation, distributed tasks and handoffs. | Task decomposition is covered here; assigning and coordinating work across agents is covered there. |
| **7. Security, Safety and Governance** | Establishes security controls, policy restrictions and safeguards. | This discipline checks plans against known constraints; detailed security controls are covered there. |
| **8. Agentic Governance and Self-Governing Systems** | Defines shared rules, authority, accountability and collective governance. | Planning respects governance rules; it does not create authority for itself. |
| **9. Evaluation and Testing** | Provides systematic methods for measuring performance and validating behaviour. | This discipline introduces plan-level checks; formal evaluation methods belong there. |
| **10. Human-Agent Interaction** | Designs how people instruct, clarify, review, approve and intervene. | This discipline identifies when clarification or human decisions are needed; interaction design belongs there. |
| **11. Observability and Reliability** | Makes system behaviour visible and supports dependable operation. | This discipline uses relevant feedback conceptually; monitoring and telemetry engineering belong there. |
| **12. Performance and Infrastructure** | Addresses computational resources, latency, scale and operating cost. | Planning may consider resource limits; infrastructure and performance engineering belong there. |
| **13. Evolution and Continuous Improvement** | Maintains and improves systems over time. | This discipline covers replanning within a task; system-wide improvement and change management belong there. |

## 5. Learning method

Use agricultural market intelligence as the first practical pilot path to make concepts concrete and to inform real design and validation work. Mark proposed architectures, untested workflows and hypothetical examples clearly; do not present them as working capabilities until tested. Practical work may progress alongside the chapter sequence.

For each chapter:
- Explain the concept and distinguish it from related concepts.
- Connect it to a practical problem or design decision in the agricultural pilot where relevant.
- Identify whether the capability can be supplied by existing solutions, assembled components, a human process or custom development.
- Research tools and platforms only when a concrete requirement makes the investigation relevant.
- Use worked examples and practical tests where possible.
- Identify assumptions, evidence, uncertainty, costs, risks and limits.
- Record the lesson's key principles and what the practical work demonstrates.
- Update the chapter document and exact learning continuation point.
- Record practical pilot progress separately so the learning sequence and build status are not confused.

Where useful, exercises will ask the learner to formulate goals, decompose tasks, compare candidate plans or identify when an agent should ask for clarification rather than proceed.

## 6. Scope principles

- Start from the objective and available evidence, not from a preferred reasoning technique.
- Distinguish conclusions supported by evidence from hypotheses and assumptions.
- A plausible explanation is not automatically a verified fact.
- A plan is a proposed course of action, not proof that the actions are possible or authorised.
- Check preconditions, constraints, dependencies, consequences and stopping conditions.
- Do not confuse planning with execution or multi-agent orchestration.
- Do not assume every task needs elaborate reasoning; use the simplest sufficient method.
- An agent must be able to defer, ask, stop or escalate when it cannot form a sufficiently sound or permitted plan.
- Treat frameworks and examples as learning aids unless explicitly established as universal standards.
- Investigate tools only when a specific capability requirement makes them necessary.

## Chapter documents

1. [Chapter 1 — Foundations of Reasoning and Planning](chapters/01-foundations-of-reasoning-and-planning.md)
2. [Chapter 2 — Goals, Instructions and Problem Formulation](chapters/02-goals-instructions-and-problem-formulation.md)
3. [Chapter 3 — Reasoning Patterns and Inference](chapters/03-reasoning-patterns-and-inference.md)

## 7. Current continuation point

**Discipline 2 → Chapter 3 → 3.3 Abductive Reasoning and Explanation.**

Chapters 1–2 (subsections 1.1–1.4 and 2.1–2.5) are complete. Chapter 3 is in progress; subsections 3.1 and 3.2 are covered.
