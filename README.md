# Agentic AI Engineering

A structured, continuously documented learning and research project exploring how to design, engineer, govern, evaluate, deploy, and improve agentic AI systems.

## Purpose

Build a practical and reusable understanding of agentic AI engineering, from individual agent architecture to multi-agent systems and self-governing autonomous systems. The project is a learning and documentation effort; it does not assume that every concept requires immediate software implementation.

## Working principles

- **Capability before technology:** identify the capability or problem before selecting a tool or platform.
- **Assemble before building:** prefer existing, suitable capabilities and integrations before creating new components.
- **Reuse before repetition:** preserve prior research, decisions, and lessons so work can continue without repeatedly starting over.
- **Complexity only when justified:** do not add infrastructure, technologies, or architectural layers without a demonstrated need.
- **Evidence and verification:** distinguish established concepts, documented claims, proposals, assumptions, and unresolved questions.
- **Continuity and portability:** keep project knowledge understandable and useful independently of a particular conversation or tool.
- **Document as we learn:** record concepts, distinctions, examples, decisions, and open questions as the curriculum progresses.

## Curriculum

The current curriculum is organised into 13 disciplines:

1. Agent Architecture and Design
2. Reasoning and Planning
3. Context, Memory and Knowledge
4. Tools and Environment Engineering
5. Execution and Loop Engineering
6. Orchestration and Multi-Agent Systems
7. Security, Safety and Governance
8. Agentic Governance and Self-Governing Systems
9. Evaluation and Testing
10. Human-Agent Interaction
11. Observability and Reliability
12. Performance and Infrastructure
13. Evolution and Continuous Improvement

Agentic Governance is a dedicated discipline and also a cross-cutting concern. Its themes include distributed authority, shared rules, accountability, collective decision-making, conflict resolution, and governance without a single agent controlling every operational decision.

The curriculum is intentionally technology-neutral. Technologies such as blockchain are considered only when a specific capability or requirement makes them necessary; they are not assumed to be mandatory components of agentic systems.

## Learning progress

### Discipline 1 — Agent Architecture and Design

#### Chapter 1 — Understanding Agent Architecture

An AI agent is a system that uses an AI model to pursue an objective by observing information, making decisions, interacting with tools or an environment, and evaluating results. This distinguishes a goal-directed agent system from a chatbot that primarily responds to conversational prompts.

#### Chapter 2 — Basic Architecture of an Agent

The conceptual architecture includes:

- Objective or goal
- AI model
- Context
- Memory
- Tools
- State
- Execution environment
- Observation and feedback

This is a conceptual map, not a mandatory implementation blueprint. Different systems may combine or separate these components.

#### Chapter 3 — Core Concepts Within Agent Architecture

Introduced concepts include agent architecture, harness engineering, runtime, goal architecture, state management, identity, configuration, lifecycle, boundaries, and capability architecture.

#### Chapter 4 — Agent vs Chatbot vs Workflow vs Automation vs Autonomous System

- **Chatbot:** primarily conversation-oriented.
- **Workflow:** a defined sequence of tasks or stages.
- **Automation:** performs actions according to predefined rules or triggers and may not require AI.
- **AI agent:** uses model-driven decisions and actions to pursue an objective, with some degree of autonomy.
- **Autonomous system:** a broader system capable of sustained independent operation; it may contain agents, workflows, automation, databases, sensors, and other components.

These categories can overlap. An agent can be part of a workflow, and an autonomous system can contain multiple agents.

Related vocabulary introduced: agentic workflow, hybrid automation, autonomy levels, supervisory control, agentic system, and closed-loop system.

#### Chapter 5 — Autonomy Levels and the Autonomy Spectrum

A teaching framework was introduced with five illustrative levels:

1. **Advisory:** analyses and recommends; a human decides.
2. **Assisted execution:** prepares actions but waits for approval before execution.
3. **Conditional autonomy:** acts independently within approved limits and escalates exceptional or high-risk cases.
4. **High autonomy:** plans, executes, monitors, and adjusts within established policies.
5. **Full operational autonomy:** manages ongoing objectives with minimal routine human intervention.

These five levels are a project learning framework, not a claim that there is one universally adopted five-level industry standard.

Autonomy is shaped by decision authority, execution authority, permission boundaries, resource authority, approval requirements, escalation mechanisms, and recovery or reversibility.

Key concepts: bounded autonomy, human-in-the-loop, human-on-the-loop, human-out-of-the-loop, escalation, permission architecture, autonomy scaling, and reversibility.

A core principle established: **an agent's authority must be deliberately designed, not accidentally granted.**

A second principle established through the agricultural intelligence example: **agents should have different autonomy levels according to their responsibilities, reliability, and potential consequences.** Illustrative starting assignments were:
- Market data collection: Level 4
- Information verification: Level 3
- Market analysis: Level 4
- Opportunity discovery: Level 2–3
- Reporting and notifications: Level 3

These are examples for discussion, not final production settings.

#### Chapter 6 — Agent Identity, Roles and Responsibilities (in progress)

The chapter introduces:
- Agent identity: what distinguishes one agent from another.
- Agent role: the function it performs.
- Agent responsibilities: what it is expected to accomplish.
- Agent authority: what decisions and actions it is allowed to perform.
- Agent boundaries: what it must not do.
- Agent relationships: which other agents it can communicate or collaborate with.
- Agent accountability: how actions and decisions can be traced and assessed.

The first subsection, **6.1 Agent Identity**, has been introduced.

An agent should have a distinguishable identity so the system can establish which agent is performing a task, its assigned role, responsibilities, permissions, communication relationships, and activity history.

An agent's identity is separate from the AI model powering it. Multiple agents may use the same model while having different identities, roles, configurations, permissions, and memory. An agent's underlying model may also change without necessarily changing its identity.

Principle: **every agent should have a clearly identifiable identity independent of the model powering it.**

Next subsection: **6.2 Agent Roles** — how an agent's identity translates into a defined function within a larger system.

## Concepts and examples used in the learning process

An agricultural intelligence system has been used as a recurring illustrative example. It includes possible specialised agents for market data collection, information verification, market analysis, opportunity discovery, and reporting. The example is used to reason about responsibilities, authority, permissions, autonomy, coordination, and accountability; it is not yet a committed implementation architecture.

## Technology selection policy

Tools, platforms, protocols, databases, models, and infrastructure will be studied in detail when the curriculum or a concrete design requirement makes them relevant. A tool advertisement or recommendation is only a candidate for later investigation, not an endorsement or an implementation requirement.

When technology evaluation becomes necessary, assess the actual capability, fit, alternatives, accessibility, cost, evidence, limitations, security, and practical value before deciding whether to use it.

## Documentation status

- Project repository initialised.
- Curriculum established at 13 disciplines.
- Discipline 1 is in progress.
- Chapters 1–5 have been covered in the learning sequence.
- Chapter 6 has begun; subsection 6.1 is documented.
- No implementation stack or infrastructure is mandated at this stage.

## How to continue

Continue from **Discipline 1 → Chapter 6 → 6.2 Agent Roles**.

As learning continues, update the relevant chapter documents and this README's progress summary. Preserve earlier decisions and distinguish confirmed learning content from proposals and unresolved questions.
