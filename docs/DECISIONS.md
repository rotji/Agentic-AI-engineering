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

## D-006 — Use the agricultural intelligence ecosystem as an illustrative learning example

**Decision:** Use specialised agricultural intelligence agents to illustrate architecture, roles, responsibility, autonomy and coordination.

**Reason:** A recurring example makes abstract engineering concepts easier to examine.

**Boundary:** This does not commit the project to building that system or establish a final production architecture.

**Status:** Active.

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
