# Decision Log

This file records decisions that shape the learning project. It is not a list of every idea discussed.

## D-001 — Use a structured 13-discipline curriculum

**Decision:** Organise the learning project into the 13 disciplines listed in [Curriculum](CURRICULUM.md).

**Reason:** The subject is broad and needs a stable structure that supports incremental learning and retrieval.

**Status:** Active.

## D-002 — Make Agentic Governance a dedicated and cross-cutting discipline

**Decision:** Include Agentic Governance and Self-Governing Systems as Discipline 8, while treating governance as relevant across the other disciplines.

**Reason:** Governance is not limited to a single agent or a single security feature. It concerns authority, shared rules, accountability, coordination and decision-making across the system.

**Status:** Active.

## D-003 — Keep the curriculum capability-led and technology-neutral

**Decision:** Do not select or investigate technologies merely because they are popular, advertised or mentioned during a lesson. Explore them in detail when a specific capability or design requirement makes them relevant.

**Reason:** The project should understand what needs to be achieved before selecting a means of achieving it. Avoid unnecessary complexity and premature implementation commitments.

**Status:** Active.

## D-004 — Defer detailed blockchain exploration unless a concrete need arises

**Decision:** Blockchain is not a separate required discipline or a mandatory layer in the agentic AI architecture. Revisit it only when a specific requirement calls for capabilities it provides and simpler alternatives are insufficient.

**Reason:** The project should not divert from its learning sequence or introduce technology without demonstrated need.

**Status:** Active.

## D-005 — Treat tools and platform recommendations as candidates, not requirements

**Decision:** Tool advertisements, recommendations and platform mentions do not automatically trigger detailed investigation or adoption. Assess them when the curriculum or a practical requirement makes the capability relevant.

**Reason:** Preserve focus and avoid tool-driven learning.

**Status:** Active.

## D-006 — Use the agricultural intelligence ecosystem as the recurring learning example

**Original decision:** Use specialised agricultural intelligence agents to illustrate architecture, roles, responsibility, autonomy and coordination.

**Reason:** A recurring example makes abstract engineering concepts easier to examine.

**Updated boundary:** Decision D-011 subsequently established agriculture as the first practical pilot path, not merely an illustrative classroom example. The agricultural intelligence programme remains a proposed practical direction whose requirements and capabilities must be validated; it is not a claim that a production system has already been built.

**Status:** Superseded by D-011, which governs the practical pilot and cross-sector transfer approach.

## D-007 — Different agents may require different autonomy levels

**Decision:** Assign autonomy according to each agent's responsibilities, reliability and potential consequences rather than giving every agent the same level.

**Reason:** Agents perform different functions and their actions carry different levels of risk.

**Status:** Active as a design principle. Example assignments in Chapter 5 are illustrative, not production settings.

## D-008 — Separate agent identity from its underlying model

**Decision:** Treat an agent's identity as distinct from the AI model powering it.

**Reason:** Multiple agents can use the same model while having different roles, configurations, permissions and memory; a model can also be changed without necessarily changing the agent's identity.

**Status:** Active learning principle introduced in Chapter 6.1.


## D-009 — Add an architecture-design synthesis chapter to Discipline 1

**Decision:** Add Chapter 8, From Requirements to Agent Architecture, as the final chapter of Discipline 1.

**Reason:** The existing seven chapters establish individual concepts and agent-level design elements, but the documented sequence does not yet teach a repeatable end-to-end method for determining whether an agent is appropriate and assembling the relevant concepts into a coherent architecture for a real problem.

**Scope boundary:** The chapter will synthesise existing material and address problem framing, requirements, capability mapping, high-level architecture selection, component boundaries and flows, autonomy and oversight integration, and architecture documentation/review. Detailed reasoning, context/memory, tools, execution loops, orchestration, security, governance, evaluation, infrastructure and continuous improvement remain in their assigned disciplines.

**Status:** Implemented. Chapter 8 is complete, and the final Discipline 1 review confirmed that it addresses the identified design-synthesis gap.


## D-010 — Establish a dedicated learning sequence for Reasoning and Planning

**Decision:** Define Discipline 2 as a ten-chapter learning sequence covering foundations, goal and problem formulation, reasoning and inference, problem representation, task decomposition, planning strategies and search, decision-making and action selection, uncertainty, plan validation and replanning.

**Reason:** Reasoning and planning are core agent capabilities that need structured treatment, distinct from the architecture decisions in Discipline 1 and the detailed execution, context, tools and orchestration concerns assigned to later disciplines.

**Scope boundary:** This discipline covers forming and revising plans, not executing tools, engineering persistent memory/retrieval, implementing runtime loops or coordinating work across multiple agents. Those responsibilities remain in their assigned disciplines.

**Status:** Active. Scope and sequence defined; Chapter 1.1 covered.


## D-011 — Integrate practical building and cross-sector transfer into the learning journey

**Decision:** Run Agentic AI Engineering as an integrated learning, solution-discovery, assembly, engineering, validation and sector-transfer journey rather than a theory-only curriculum. Agriculture is the first practical pilot path. When a capability or principle is validated there, assess its reuse in other sectors, including real estate, mining and healthcare, with sector-specific adaptation and independent validation.

**Operating cycle:** Identify a real problem; study relevant concepts; define requirements and capabilities; discover and evaluate existing solutions; assemble suitable capabilities; test the result; build only demonstrated gaps; document evidence and decisions; and assess transferability to other sectors.

**Build principle:** Reuse, integrate, partner or implement existing solutions when they adequately satisfy the need. Develop custom components only when a genuine capability gap or other clearly justified reason remains.

**Transfer boundary:** Reuse proven principles and suitable components, not unvalidated sector assumptions, data models, thresholds, permissions or decision rules. Healthcare and other high-consequence sectors require appropriate domain expertise, privacy and regulatory review, professional oversight and stronger validation.

**Reason:** The purpose is not merely to understand agentic AI concepts, but to use that understanding to assemble working capabilities and build only what is genuinely missing, while creating reusable methods across industries.

**Status:** Active.


## D-012 — Treat reusable procedural knowledge as a cross-cutting design capability

**Decision:** Before designing a new specialist agent for recurring work, assess whether an existing agent/runtime can perform it with a focused, reusable procedure (often packaged as a Skill), the necessary reference knowledge and authorised tools.

**Scope:** Reusable procedures are cross-cutting across the 13 disciplines, not a new fourteenth discipline. They package procedural expertise; they do not independently provide tool access, credentials, data, execution infrastructure, authority or governance.

**Agent-boundary rule:** Separate agents remain appropriate where distinct identity, permissions, security isolation, state, lifecycle, parallel execution or accountable responsibility are justified by requirements.

**Quality boundary:** Candidate procedures must be grounded in evidence, tested on representative tasks, reviewed for safety and security, versioned and maintained. A procedure is not a validated capability merely because it has been written or used once.

**Technology boundary:** This decision does not mandate Anthropic, the `SKILL.md` format, a particular runtime or a Skills platform. Compatibility and portability must be tested in each target environment.

**Reason:** Reusable procedural expertise can reduce duplicated instructions and unnecessary agent scaffolding while allowing specialist knowledge to be shared and maintained. The project should prefer the simplest architecture that satisfies demonstrated requirements.

**Status:** Active design principle; implementation remains unselected and unvalidated.


## D-013 — Treat web scraping as one option within source-first data acquisition

**Decision:** Treat web scraping as one method within the project's wider information-acquisition capability, not as the default method or a goal in itself. Select the source and required information first; then prefer a suitable documented API, official downloadable dataset, feed, export or approved integration. Consider permitted HTML scraping or browser-based acquisition only when structured routes are unavailable or materially insufficient.

**Quality boundary:** Preserve source identity, original location, retrieval time, publication/observation times where available, extraction method, original values, transformations, quality checks and evidence status. Successful extraction is not proof that the extracted claim is true.

**Governance boundary:** Review applicable access conditions, terms, licences, privacy and data-protection obligations, request limits and publisher instructions. Do not bypass access controls or treat `robots.txt` as a grant of permission. Escalate uncertain or higher-risk collection for review.

**Architecture boundary:** Scraping is primarily a data-acquisition capability implemented through tools/connectors. It may be scheduled by automation, used within a workflow, or invoked by an agent where appropriate; it is not itself an agent, Skill, workflow, automation platform or new discipline.

**Reason:** The project's mission depends on useful, traceable and reliable information, not on collecting the largest possible volume of web pages. The most suitable permitted interface should be used for each source, with extraction and evidence quality tested.

**Status:** Active design principle; no scraper, crawler or scraping platform has been selected or deployed.
