# Discipline 1 Review — Agent Architecture and Design

**Review status:** Completed  
**Date:** 2026-11-27  
**Outcome:** One final synthesis chapter is justified before moving to Discipline 2.

## 1. Purpose of this review

Review the seven chapters currently documented for Discipline 1, identify what they cover, check for missing foundational architecture work, and decide whether another chapter is warranted.

The review follows the project's curriculum change-control principle: add material only when a genuine learning gap exists, and place it in an existing discipline where possible.

This is a review of the repository's documented learning record. The concise notes in Chapters 1–4 are summaries of introductory coverage; they should not be interpreted as proof that every underlying topic has been studied in full depth.

## 2. Coverage assessment

| Existing chapter | Main coverage | Review finding |
|---|---|---|
| 1. Understanding Agent Architecture | Goal-directed agent definition and basic observe–interpret–act–evaluate pattern | Foundational definition established |
| 2. Basic Architecture of an Agent | Objective, model, context, memory, tools, state, execution environment, observation and feedback | Core conceptual component map established |
| 3. Core Concepts Within Agent Architecture | Harness engineering, runtime, goal architecture, state, identity, configuration, lifecycle, boundaries and capability architecture | Vocabulary introduced; deeper treatment appropriately distributed across later chapters and disciplines |
| 4. Agent vs Chatbot vs Workflow vs Automation vs Autonomous System | Distinctions and relationships among common system forms | Classification established |
| 5. Autonomy Levels and the Autonomy Spectrum | Five-level teaching framework, authority factors and human oversight | Autonomy and differentiated authority introduced |
| 6. Agent Identity, Roles and Responsibilities | Identity, roles, responsibilities, authority, boundaries, relationships and accountability | Individual agent definition and organisation covered |
| 7. Agent Configuration and Lifecycle | Configuration, configuration elements, startup, states, version changes, lifecycle and continuity | Operational preparation and lifecycle management covered |

## 3. What is sufficiently covered for now?

The documented curriculum has established:
- What an agent is and how it differs from adjacent system types.
- The main conceptual components that may make up an agent.
- The distinction between an AI model and the wider agent system.
- Identity, role, responsibility, authority and boundaries.
- Autonomy and human oversight.
- Agent relationships and accountability.
- Configuration, initialization, lifecycle, change management and continuity.

These topics provide a meaningful foundation for studying the more specialised disciplines.

## 4. Genuine gap identified: an end-to-end architecture design method

The existing chapters explain individual concepts and components, but the documented sequence does not yet teach a complete method for turning a real problem or requirement into a coherent agent architecture.

A learner can know what an agent is, understand its components, define its permissions and configure its lifecycle, yet still lack a repeatable process for answering:

- Is an agent actually appropriate for this problem, or would conventional software, a workflow or automation be simpler?
- What outcomes and constraints must the overall system satisfy?
- Which capabilities are required, and which belong inside an agent versus surrounding system components?
- Should the solution use one agent, a hybrid workflow or several specialised agents?
- How should component responsibilities, interfaces, information flows and control boundaries fit together?
- How can the resulting architecture be reviewed against the original requirements?

This is a design-synthesis gap, not a reason to create a new discipline. It belongs at the end of Agent Architecture and Design.

## 5. Scope boundaries: what should remain in later disciplines?

The final synthesis chapter should not duplicate the deeper treatment assigned elsewhere.

| Topic | Discipline for detailed study | Treatment in the synthesis chapter |
|---|---|---|
| Reasoning, task decomposition and planning algorithms | 2 — Reasoning and Planning | Identify planning needs; defer detailed methods |
| Context, memory, retrieval and knowledge engineering | 3 — Context, Memory and Knowledge | Identify information requirements and component responsibilities |
| APIs, tools, integrations and environment interaction | 4 — Tools and Environment Engineering | Identify required capabilities and integration boundaries |
| Agent loops, action execution and feedback control | 5 — Execution and Loop Engineering | Show where the execution cycle belongs in the architecture |
| Multi-agent coordination and orchestration patterns | 6 — Orchestration and Multi-Agent Systems | Make a high-level choice; defer coordination mechanics |
| Security engineering, safety controls and governance | 7 and 8 | Carry requirements and boundaries into the architecture; defer detailed controls |
| Evaluation methodology | 9 — Evaluation and Testing | Define what must be validated; defer test design and metrics |
| Human interaction and approval experience | 10 — Human-Agent Interaction | Identify human control points |
| Monitoring and reliability engineering | 11 — Observability and Reliability | Identify observability and reliability requirements |
| Infrastructure, scale, latency and cost engineering | 12 — Performance and Infrastructure | Capture constraints; defer infrastructure choices |
| Updating and improving deployed systems | 13 — Evolution and Continuous Improvement | Preserve evolution requirements and traceability |

## 6. Decision

Add one final chapter to Discipline 1:

**Chapter 8 — From Requirements to Agent Architecture**

This chapter will bring together the concepts already studied and teach a practical, repeatable architecture-design process.

It will not select implementation technologies, prescribe an infrastructure stack or turn the agricultural intelligence example into a build commitment.

## 7. Proposed Chapter 8 learning scope

The following is an outline; the lessons have not yet been taught.

1. **8.1 Problem Framing and Agent Suitability** — define the problem and decide whether an agent is justified compared with simpler alternatives.
2. **8.2 Requirements, Constraints and Operating Context** — identify desired outcomes, users, environment, dependencies, risks and quality constraints.
3. **8.3 Capability and Responsibility Mapping** — translate requirements into capabilities and assign them to agents or conventional system components.
4. **8.4 Selecting the High-Level Architecture Shape** — consider a single agent, an agent with supporting workflow or automation, a hybrid system, or multiple specialised agents; defer detailed orchestration to Discipline 6.
5. **8.5 Component Boundaries, Interfaces and Flows** — establish responsibilities, inputs, outputs, information flows, control boundaries and dependencies at architecture level.
6. **8.6 Integrating Autonomy, Authority and Human Oversight** — ensure decisions, permissions, boundaries, approvals and escalation are coherent across the design.
7. **8.7 Producing and Reviewing an Architecture Blueprint** — document the design, assumptions, alternatives, trade-offs, unresolved questions and traceability to requirements.

The outline may be refined as each lesson is taught.

## 8. Review conclusion

Discipline 1 is not yet complete. Chapters 1–7 establish the main concepts and agent-level lifecycle, but Chapter 8 is needed to show how to assemble those concepts into a coherent architecture for a real problem.

After Chapter 8, review the discipline once more. If the design method is clear and the remaining specialist topics are properly assigned to later disciplines, transition to Discipline 2 — Reasoning and Planning.

## 9. Current continuation point

**Discipline 1 → Chapter 8 → 8.1 Problem Framing and Agent Suitability.**

No implementation or tool-selection work is implied by this decision.
