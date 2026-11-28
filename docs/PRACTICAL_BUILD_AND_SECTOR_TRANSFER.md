# Practical Build and Sector Transfer Method

**Status:** Active project operating method  
**Applies to:** All 13 disciplines and all sector pilots

## 1. Purpose

Agentic AI Engineering is not a theory-only course. It is a practical learning, research, integration and engineering journey. Concepts are studied because they help us understand, select, assemble, test, govern or improve real capabilities.

The project will continue theoretical exploration, but theory will be learned in context and connected to practical work. We will not postpone all practical building until all 13 disciplines have been completed.

## 2. Pilot and expansion strategy

### Agriculture is the first pilot path

Agriculture is the initial practical domain in which to investigate real problems, identify required capabilities, discover existing solutions, assemble suitable components and test working methods.

The agricultural pilot is more than an illustrative classroom example. It is the first practical path for developing and validating reusable capabilities. A pilot result must still be supported by evidence; a proposed architecture or demonstration is not proof of successful operation.

### Transfer validated principles across sectors

When a capability, workflow or engineering principle works in the agricultural pilot, examine whether it can apply to other sectors, including:

- Real estate
- Mining
- Healthcare
- Other industries and public or commercial services where a real need is established

Transfer the validated principle, not the agricultural assumptions or implementation unchanged. Each sector has distinct entities, evidence standards, workflows, stakeholders, regulations, risks and consequences.

Healthcare and other high-consequence domains require appropriate domain expertise, regulatory and privacy review, clinical or professional oversight where applicable, and stricter validation. A successful agricultural pilot does not establish that the same autonomy, data handling or decision rules are safe in healthcare.

## 3. The integrated learning and building cycle

Use the following cycle repeatedly. It is a project method, not a universal engineering standard.

1. **Identify a real problem:** start with an operational need in the pilot domain, not a preferred technology.
2. **Understand the relevant concepts:** study the theory needed to analyse the problem and avoid shallow implementation.
3. **Define requirements and capabilities:** specify what must be achieved, constraints, evidence needs, quality expectations and acceptance conditions.
4. **Discover existing solutions:** research suitable products, open-source projects, services, APIs, MCP integrations, datasets, standards, providers and possible partners.
5. **Evaluate fit and evidence:** compare actual capabilities, limitations, cost, accessibility, licensing, security, reliability, data rights, interoperability and support. Distinguish vendor claims from verified tests.
6. **Assemble before building:** integrate suitable existing capabilities and use manual or lightweight processes where appropriate. Do not create custom components merely for architectural completeness.
7. **Test the practical result:** use controlled or authorised real-world data and workflows. Define what success means and record failures, limitations and operating costs.
8. **Build only a demonstrated gap:** create a custom component only when existing solutions cannot adequately satisfy an important requirement, or when building is otherwise clearly justified by control, integration, cost, differentiation or feasibility.
9. **Document and maintain:** preserve architecture, configuration, interfaces, decisions, tests, evidence, risks and continuation records.
10. **Extract and transfer:** identify which principles and components are reusable, define what must change for another sector, and validate the adaptation independently.

Repeat the cycle as the pilot reveals new needs.

## 4. Keep four workstreams connected

The project should maintain four connected workstreams rather than treating them as isolated stages:

| Workstream | Purpose | Expected output |
|---|---|---|
| Learning and theory | Understand concepts, methods, risks and limitations when they become relevant | Reusable knowledge and documented principles |
| Solution discovery | Find and assess existing capabilities and providers | Evidence-backed solution options and fit decisions |
| Pilot assembly and engineering | Combine existing solutions and build only justified gaps | Working, testable capability or workflow |
| Validation and sector transfer | Test results, identify reusable principles and assess adaptations | Evidence, limitations, reusable patterns and sector-specific requirements |

A learning chapter may advance while the pilot also advances. Practical needs may temporarily call for a concept from a later discipline, but any such detour should be documented and should not erase the curriculum's exact learning position.

## 5. Separate reusable foundations from sector-specific design

When a capability works in one sector, examine it at three levels.

### A. Potentially reusable core principles and capabilities

Depending on evidence and requirements, reusable capabilities may include:
- Entity and participant registries.
- Information acquisition and source connectors.
- Data normalisation and classification.
- Evidence provenance and verification status.
- Event and change detection.
- Search, analysis and reasoning.
- Opportunity discovery and decision support.
- Workflow, approvals and task coordination.
- Reporting, notifications and audit records.
- Evaluation, monitoring and reliability practices.

This list is a discovery framework, not a predetermined product architecture. A capability belongs in the reusable core only when its value and portability are demonstrated.

### B. Sector-specific adapters

Each sector may require its own:
- Entity types and relationships.
- Terminology, units, taxonomies and data models.
- Information sources and access conditions.
- Operational workflows and decision criteria.
- Evidence standards and validation procedures.
- User roles, external participants and integration requirements.

For example, agricultural commodity observations are not interchangeable with property title records, mineral production data or clinical records.

### C. Sector-specific governance and risk controls

Rules for autonomy, privacy, safety, approval, accountability, retention and permitted actions must be assessed separately for each sector and use case.

Do not transfer a permission level, threshold, model prompt, decision rule or risk assumption merely because a capability worked elsewhere.

## 6. Evidence required before declaring a working principle reusable

A successful demonstration in one situation is not sufficient to claim broad generality.

Before promoting a capability or principle to reusable status, document:

- The problem and operating conditions in which it worked.
- The requirements it satisfied.
- The data and evidence used.
- The tests and acceptance criteria.
- Observed results, failures and limitations.
- Dependencies, operating costs and ongoing maintenance.
- Which parts appear sector-independent.
- Which assumptions are specific to the original sector.
- What needs to change in the next sector.
- The evidence required to validate that adaptation.

Classify transferability as **proven in the original pilot**, **plausibly reusable but not yet validated elsewhere**, or **validated in multiple sectors**. Avoid treating a proposal as a proven reusable principle.

## 7. Rules for existing solutions and custom development

- Search for existing capability before proposing custom development.
- Consider commercial, open-source, public, local and global solutions where relevant.
- Evaluate products on actual requirements, not feature-list size or marketing claims.
- Prefer interoperable components and preserve the ability to replace providers.
- Examine licensing, data rights, security, support, reliability, costs and exit options.
- Consider partnership, implementation, distribution or integration opportunities where they are more practical than building.
- Build a custom component only for a demonstrated gap or a clearly justified strategic reason.
- Do not introduce a technology merely because it is fashionable, advertised or mentioned in a lesson.

### Prefer reusable procedures before creating more agents

When a recurring task appears to need specialist expertise, first assess whether an existing agent/runtime can perform it using a focused reusable procedure (often called a Skill), the appropriate reference knowledge and the required authorised tools. Test that combination on representative tasks before creating another agent.

A reusable procedure does not provide its own tools, credentials, permissions, data or governance. Nor should every problem be turned into a Skill: create or retain separate agents when distinct identity, security boundaries, isolated state, independent lifecycle, parallel execution or accountable responsibility make them necessary. See [Reusable Skills and Procedural Knowledge](REUSABLE_SKILLS_AND_PROCEDURAL_KNOWLEDGE.md) for the detailed design and quality controls.

## 8. Relationship with the 13-discipline curriculum

The 13 disciplines remain the knowledge structure. They are not a requirement to finish theory in sequence before practical work begins.

When a practical task needs a capability:
- Study the relevant concept to an appropriate depth.
- Identify the related discipline and preserve the main curriculum position.
- Research or test existing solutions when the requirement is concrete.
- Apply the concept to the pilot where appropriate.
- Record what the practical work taught us.
- Return to the planned learning sequence and revisit deeper concepts when needed.

## 9. Operating principle

**Learn what is needed, discover what already exists, assemble what works, build what is genuinely missing, validate the result, and transfer only what evidence supports.**

Agriculture is the first pilot path; it is not the limit of the project. The longer-term objective is to develop reusable engineering capabilities and principles that can be adapted responsibly across sectors.
