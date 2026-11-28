# Reusable Skills and Procedural Knowledge

**Status:** Adopted as a cross-cutting design principle for the project  
**Implementation status:** Concept documented; no production Skill, Skill runtime or agent architecture has been selected or validated  
**Applies to:** All 13 disciplines and practical sector pilots

## 1. Purpose

A capable general-purpose agent may still lack the specialised procedures, domain knowledge, quality checks and operating conventions needed for reliable work in a particular setting.

The project will therefore treat **reusable procedural knowledge** as an architectural capability in its own right. Instead of automatically creating a separate, bespoke agent for every domain or task, first ask whether an existing agent runtime can perform the work more reliably by being equipped with a well-defined, reusable procedure and the appropriate tools, data and permissions.

The term **Skill** is used here as a convenient name for a packaged, reusable procedure. It is a design concept, not a commitment to one vendor, file format, runtime or implementation.

This direction is informed by Barry Zhang and Mahesh Murag's talk, [“Don't Build Agents, Build Skills Instead”](https://www.youtube.com/watch?v=CEvIs9y1uog), and Anthropic's [Agent Skills overview](https://www.anthropic.com/research/equipping-agents-for-the-real-world-with-agent-skills). The project adopts the reusable-knowledge principle while retaining technology neutrality and independent evaluation.

## 2. The central distinction

A Skill is not a smaller agent. It is a reusable package of procedural expertise that an agent can apply when relevant.

| Concept | Primary purpose |
|---|---|
| **Model** | Provides the underlying language, reasoning or other AI capability. |
| **Agent/runtime** | Interprets goals, maintains task state, reasons, selects actions and operates within its configured environment. |
| **Skill / reusable procedure** | Explains how to perform a recurring class of work: steps, decision rules, domain conventions, checks and expected outputs. |
| **Prompt / instruction** | Directs the agent for a particular interaction or task. |
| **Context / reference knowledge** | Supplies facts, background, schemas, records or other information needed for the current work. |
| **Tool / connector** | Provides an interface through which an authorised system can read, calculate, retrieve or change something. |
| **Workflow / orchestration** | Organises task order, dependencies, hand-offs, parallel work and coordination across components or agents. |
| **Governance / policy** | Defines authority, permissions, restrictions, approvals, accountability and oversight. |
| **Evaluation** | Tests whether the agent and procedure produce acceptable results under representative conditions. |

These elements complement one another. A Skill can explain how to use a tool, but it does not itself provide the connection, credentials, technical capability or permission to use that tool.

Likewise, describing a procedure in a Skill does not make the procedure correct. Its content must be grounded in evidence, tested and maintained.

## 3. What a reusable Skill may contain

A Skill should contain only the material needed to perform its defined work. Depending on the task and runtime, it may include:

- **Identification metadata:** a clear name, purpose and description of when the procedure applies.
- **Instructions:** ordered steps, decision points, required inputs, expected outputs, exception handling and escalation conditions.
- **Reference materials:** domain definitions, classification rules, schemas, source guidance, examples or other material that can be consulted when needed.
- **Scripts or deterministic operations:** code for repeatable transformations, calculations, parsing or validation where execution is supported and justified.
- **Templates and assets:** reusable report structures, forms, checklists or other task resources.
- **Evaluation material:** test cases, expected results, known limitations and regression checks.

A useful design pattern is **progressive disclosure**: make a short description available for discovery, load the main procedure only when it is relevant, and consult larger reference materials or run scripts only when needed. This can reduce unnecessary context loading and help keep procedures composable.

This is a design pattern, not a requirement that every runtime use Anthropic's exact `SKILL.md` structure or loading mechanism.

## 4. Prefer a reusable procedure before creating another agent

When a new task or domain appears, use this decision sequence:

1. Define the actual problem, users, intended outcome and constraints.
2. Identify the capabilities and tools required.
3. Check whether an existing agent/runtime can already perform the basic reasoning and interaction.
4. Determine whether the recurring gap is primarily missing procedural expertise, reference knowledge, a tool, data access, workflow coordination or a genuinely different operational responsibility.
5. Where the gap is procedural and recurring, test whether a focused reusable Skill is sufficient.
6. Evaluate the result on representative tasks before treating the Skill as reliable.
7. Create a separate agent only when a distinct identity, permission boundary, isolated state, independent lifecycle, parallel execution, specialised runtime or accountable responsibility is justified.

Do not force every problem into a Skill. A Skill cannot replace a missing tool, reliable data source, secure execution environment, human approval, external integration or necessary agent boundary.

The principle is **general-purpose agent plus reusable procedures where sufficient; additional agents where justified by evidence and system requirements**.

## 5. When separate agents remain appropriate

Separate agents may still be justified when they need materially different:

- identities, responsibilities or accountable ownership;
- permissions, credentials, security boundaries or isolation;
- memory, state, data access or retention rules;
- tools, execution environments or operating lifecycles;
- independent work that benefits from parallel execution;
- approval and escalation paths; or
- monitoring, evaluation and failure containment.

These conditions must be established by the task and risk analysis. Creating multiple agents merely to label different steps or subject areas adds coordination and governance overhead without necessarily adding capability.

Skills and agents are therefore complementary, not competing architectural choices.

## 6. Relationship to the 13 disciplines

Reusable Skills are **cross-cutting**, not a new fourteenth discipline.

| Discipline | Relationship |
|---|---|
| 1. Agent Architecture and Design | Decide whether a reusable procedure, one agent or multiple agents best fit the requirements. |
| 2. Reasoning and Planning | Apply procedures to interpret tasks, form plans, select actions and revise plans. |
| 3. Context, Memory and Knowledge | Retrieve and manage the reference knowledge a procedure needs; keep durable knowledge distinct from task state. |
| 4. Tools and Environment Engineering | Identify the tools, interfaces, data and execution capabilities a procedure depends on. |
| 5. Execution and Loop Engineering | Apply procedural steps in a controlled loop and verify actual outcomes. |
| 6. Orchestration and Multi-Agent Systems | Compose procedures into workflows and coordinate agents only where needed. |
| 7. Security, Safety and Governance | Enforce permissions, data boundaries, safe handling, approval and trusted-source requirements. |
| 8. Agentic Governance and Self-Governing Systems | Govern changes to procedures, shared rules, delegated authority and accountable oversight. |
| 9. Evaluation and Testing | Test procedures against representative cases, edge cases and regression suites. |
| 10. Human-Agent Interaction | Make review, clarification, correction and escalation understandable to people. |
| 11. Observability and Reliability | Record procedure versions, actions, results, failures and relevant provenance. |
| 12. Performance and Infrastructure | Assess loading, execution, context, runtime and resource costs. |
| 13. Evolution and Continuous Improvement | Improve procedures through reviewed evidence, versioning and controlled release. |

The concept may be introduced during architecture work and revisited in later disciplines as the engineering methods become more detailed.

## 7. Application to the agricultural pilot

The agricultural pilot should not begin by assuming that separate agents are needed for every information category or workflow step.

As practical discovery identifies recurring work, we can assess candidate procedures such as:

- **Source assessment:** inspect a source's identity, scope, access conditions, methodology, provenance, freshness, limitations and permitted use.
- **Market-observation assessment:** classify a price observation by product form, grade, market level, location, unit, currency, time and evidence status; flag records that are not comparable.
- **Producer and location evidence assessment:** distinguish producers, farms, cooperatives, facilities, places and source records; preserve unresolved identity and supply relationships.
- **Evidence comparison:** compare claims only where their definitions, periods, units and geographic scopes support comparison; record conflicts and missing evidence.
- **Intelligence reporting:** produce traceable findings, uncertainty, limitations, changes, opportunities and decisions requiring human review.

These are **candidate Skill ideas only**. None is approved as a final procedure, implemented Skill or validated capability. We should not create them merely because the names sound useful. First observe real recurring tasks, identify where current methods fail or vary, define the expected result and test whether a reusable procedure improves performance.

Agricultural evidence classifications, product definitions, local market conventions and source-use conditions must be grounded in the pilot's own research. They must not be silently generalised to other sectors.

## 8. Skill lifecycle and quality controls

A reusable procedure should move through an evidence-based lifecycle:

1. **Candidate:** a recurring task or repeated failure suggests reusable procedural knowledge may help.
2. **Specified:** purpose, intended users, trigger conditions, inputs, outputs, dependencies, limits and authority boundaries are defined.
3. **Drafted:** the smallest useful procedure is written, with references and scripts separated where appropriate.
4. **Tested:** representative normal, boundary, ambiguous, failure and adversarial cases are evaluated.
5. **Reviewed and approved:** correctness, safety, data rights, security, maintainability and ownership are assessed at the required level.
6. **Released and versioned:** the procedure is stored with its dependencies, version and change history.
7. **Monitored and maintained:** real use is observed; errors, drift, new source conditions and user corrections are assessed.
8. **Revised or retired:** changes are tested before release, and obsolete procedures are clearly withdrawn.

A procedure should not be described as self-improving simply because an agent used it or received feedback. Improvement requires deliberate review, evidence, controlled changes and regression testing. An agent may help propose a change, but changes to trusted procedures must follow the project's approval and governance rules.

Evaluation should record at least the task cases tested, expected results, observed results, failure modes, limitations, procedure version and review outcome.

## 9. Security, authority and portability boundaries

- Treat externally obtained Skills, scripts and reference files as untrusted until reviewed.
- Inspect code, dependencies, file access, network activity and tool instructions before execution.
- Do not allow a Skill to override system, project, user, security or governance policies.
- Do not embed secrets, credentials or private data in reusable procedure files.
- Apply least privilege through the runtime and tool permissions; a Skill description is not an access-control mechanism.
- Require human approval for actions that the project's governance model reserves for a person.
- Record what procedure version was used when traceability matters.
- Do not assume that a Skill written for one platform will work unchanged on another. File formats may be shareable while runtimes, APIs, execution environments, dependencies, tools and permission models differ.

Portability must be demonstrated through testing in the target environment, not inferred from a shared folder structure or an open format.

## 10. Practical design questions

Before adopting or creating a Skill, answer:

- What recurring task or demonstrated failure does it address?
- Who or what is expected to use it, and when should it activate?
- What knowledge belongs in the procedure, and what should remain in external data or references?
- Which tools, data sources, dependencies and permissions does it require?
- What must it never do, claim or infer?
- How will outputs and evidence be checked?
- Which representative cases prove that it is useful?
- Who reviews, approves, versions and maintains it?
- What would justify a separate agent instead?
- Can the procedure be transferred elsewhere, and what must be adapted and revalidated?

## 11. Project decision

The project adopts reusable procedural knowledge (often packaged as **Skills**) as a cross-cutting design principle. Before designing a new specialist agent, assess whether an existing agent/runtime with an appropriate reusable procedure and authorised tools is sufficient.

This is not a blanket instruction to build Skills, a commitment to Anthropic's implementation, a rejection of multi-agent systems or a claim that one agent can solve every problem. Agent boundaries, procedures, tools and governance must follow demonstrated requirements.

**Working rule:** package repeatable expertise for reuse; provide tools for actual operations; enforce authority through governance; and test the result before calling it a capability.
