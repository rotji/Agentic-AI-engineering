# Chapter 8 — From Requirements to Agent Architecture

**Status:** Planned — not yet taught.

## Purpose

Bring together the concepts studied in Discipline 1 and establish a repeatable method for translating a real problem or requirement into a coherent agent architecture.

The purpose is not to select implementation tools or infrastructure. It is to determine whether an agent is appropriate, what the system must accomplish, which capabilities and components are needed, how they fit together and how the proposed architecture can be reviewed.

## Why this chapter is needed

Chapters 1–7 introduced the agent concept, conceptual components, system distinctions, autonomy, identity, roles, responsibilities, authority, boundaries, relationships, accountability, configuration and lifecycle.

The remaining gap is an end-to-end design method for assembling those concepts in response to a concrete problem.

This chapter is a synthesis chapter. It should reuse prior material rather than repeat it.

## Proposed learning scope

The following subsections are planned and have not yet been taught:

1. **8.1 Problem Framing and Agent Suitability:** define the problem and decide whether an agent is justified compared with simpler alternatives.
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

## Continuation point

Begin with **8.1 Problem Framing and Agent Suitability**. Do not treat the planned subsection headings as lessons already covered.
