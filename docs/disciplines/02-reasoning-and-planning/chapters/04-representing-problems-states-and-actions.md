# Chapter 4 — Representing Problems, States and Actions

**Status:** In progress; subsection 4.1 covered.

## Purpose

Learn how to describe the situation an agent is reasoning about and the possible changes its actions may produce. This chapter begins by representing a problem and its environment, then examines states, actions, preconditions, effects, constraints, resources, time, dependencies and state spaces.

## Chapter learning sequence

1. **4.1 Problem and Environment Representation:** Covered.
2. **4.2 Current State, Goal State and State Changes:** Planned.
3. **4.3 Actions, Preconditions and Effects:** Planned.
4. **4.4 Constraints, Resources, Time and Dependencies:** Planned.
5. **4.5 State Spaces, Trees and Graphs as Planning Representations:** Planned.

---

## 4.1 Problem and Environment Representation

### Core question

Before an agent can reason about a task or plan actions, how should it describe the problem, the relevant parts of the world, the people and things involved, and the information it actually has?

An agent cannot plan reliably from a vague task description alone. It needs a representation of the problem it is trying to solve and the task-relevant environment in which the problem exists.

**Problem representation** is the structured description of a task: what needs to be achieved, what is known, which entities and relationships matter, what scope applies, and what conditions or limitations shape the work.

**Environment representation** is the structured description of the relevant external world in which the agent operates: the entities, actors, resources, processes, events, information sources and conditions that may affect the task.

These representations are related. The problem specifies what matters for the task; the environment representation describes the relevant context in which the task is being carried out.

They do not need to reproduce the entire real world. They must preserve the aspects that matter for the current task, at a level of detail appropriate to the decisions the agent is allowed to make.

### 1. Why representation matters

Consider the instruction:

> Find out why tomato prices are rising in Plateau State.

This sounds understandable to a person, but it is not yet a sufficiently precise problem representation for a dependable system.

Questions immediately arise:

- Which tomatoes: fresh, processed, a particular variety or grade?
- Which prices: farmgate, wholesale or retail?
- Which locations and markets in Plateau State?
- What period is being compared?
- What does "rising" mean: one unusually high quotation, an increase over several observations, or a measured trend?
- Which sources can be used?
- Are the observations transactions, quotations, estimates or unverified reports?
- What output is expected: a comparison, an explanation, an investigation brief or a forecast?
- What level of evidence is required before the agent can report a cause?

If these dimensions are not represented, the system may compare unlike observations, treat an estimate as a transaction, or make a statewide claim from a few local reports.

A structured representation makes the task explicit, exposes missing information and gives later reasoning and planning steps something concrete to work with.

### 2. The main parts of a problem representation

A practical problem representation can include the following elements:

| Element | What it describes | Example for the agricultural pilot |
|---|---|---|
| **Objective or task** | What work is being requested and why. | Investigate a reported change in tomato wholesale quotations. |
| **Scope** | Which entities, products, places, periods and activities are included. | A defined product form, selected markets and specified observation periods. |
| **Relevant entities** | The real things or organisations involved. | Tomato product, market, trader, source institution, transport route. |
| **Attributes** | Properties used to describe an entity or record. | Market name, product grade, unit, location or observation date. |
| **Relationships** | How relevant entities are connected. | A quotation refers to a product at a market; a source publishes an observation. |
| **Events and processes** | Things that happen and may change the situation. | A quotation is published; a load arrives; a product is processed. |
| **Known information** | Facts or observations currently available, with evidence status. | A dated source displays a particular quotation. |
| **Unknown or unresolved information** | Important details not yet established. | Whether the quotation represents a completed transaction. |
| **Desired result** | What the output or goal should look like. | A bounded, traceable comparison with unresolved causes stated clearly. |
| **Constraints and permissions** | What limits the investigation and what the agent may do. | Permitted sources, data-use conditions and no unauthorised external contact. |
| **Success conditions** | How completion or acceptable quality will be judged. | Original sources retained; comparisons compatible; limitations disclosed. |

These elements connect to earlier lessons on objectives, instructions, goals, constraints and evidence. Chapter 4 does not replace those concepts; it gives them a representation that can be used in problem-solving and planning.

The exact fields needed depend on the task. A simple task may need only a few elements. A complex investigation may need more.

### 3. Representing the environment

The **environment** is the relevant world outside the agent that it may observe, interact with or be affected by.

An environment representation may include:

- **Actors:** people and organisations that perform activities or make decisions.
- **Entities:** objects, places, products, records or resources relevant to the task.
- **Processes:** recurring or organised activities such as production, aggregation, processing, transport or trading.
- **Events:** changes or occurrences such as a harvest, shipment, quotation, transaction or disruption.
- **Information sources:** websites, registries, datasets, documents, APIs, direct observations and human reports.
- **Resources:** time, available data, equipment, services, budget or authorised access.
- **Conditions:** season, geography, market rules, operating conditions or other relevant context.
- **Interfaces:** the permitted ways the agent receives information or interacts with the environment.

For our agricultural intelligence pilot, the environment may include producers, farms, cooperatives, markets, traders, processors, transporters, government institutions, source platforms and relevant physical locations.

Not every task needs every category. A task about comparing two published price quotations may not require a full representation of the entire agricultural supply chain.

The representation should include relevant factors, not every conceivable factor.

### 4. System boundary and environment boundary

The **system boundary** describes what is inside the system being designed or operated and what remains outside it.

For example, a first agricultural research workflow might contain:
- An internal observation register.
- A source-reference store.
- A process for classifying and checking observations.
- A report-generation step.
- A human review point.

Outside that system may be:
- NBS and other data publishers.
- PLACOM and other institutions.
- Traders, producers and market operators.
- External websites and platforms.
- Physical markets and transport routes.

The agent may receive information about an external entity without controlling that entity. A website appearing in the agent's research does not mean the agent owns, operates or has permission to modify the website.

Keep these distinctions clear:

- **Inside the system:** components, records and processes under the system's defined operational control.
- **Outside the system:** people, organisations, services, devices and events that the system does not control.
- **Connected through an interface:** an external service or person from which the system can receive information or to which it may send an authorised request.
- **Not connected or not authorised:** an entity that may be relevant to the environment but that the agent cannot currently access or act upon.

A system boundary is not the same as an information boundary. Public information about an external organisation may be observable without the organisation becoming part of the system.

Similarly, being able to technically access a service does not automatically provide legal, contractual or organisational permission to use all its data or perform every possible action.

### 5. Real-world entities, digital records and claims

One of the most important distinctions for intelligence systems is the difference between a real-world entity and a record that describes it.

Consider a cooperative:

- **Real-world entity:** the actual cooperative organisation.
- **Digital record:** a database entry that describes the cooperative.
- **Source document:** a page, registry file or report from which information was obtained.
- **Claim:** a particular statement, such as "this cooperative produces tomatoes in Village A."
- **Evidence:** the material used to assess that claim.

These are not interchangeable.

A database record does not become the cooperative itself. A source page does not make every statement on the page true. A claim stored in a system is not automatically verified.

For example, if an online directory lists a cooperative's address in Village A and associates it with tomatoes, the system may record exactly that association. It must not silently convert the listing into a verified claim that the cooperative grew tomatoes in Village A during a specified season.

Representations should preserve:
- What the source actually states.
- Which real-world entity the record is believed to describe.
- The source and date of the information.
- Whether the relationship is asserted, inferred, verified or unresolved.
- Any limitations or conflicting records.

This separation helps prevent digital records from creating an unjustified appearance of certainty.

### 6. Entities, attributes, relationships and events

A useful way to structure a problem is to identify four different kinds of information.

#### A. Entities

An **entity** is a distinguishable thing or actor relevant to the problem.

Agricultural examples:
- A named farm.
- A cooperative.
- A market.
- A commodity or product.
- A trader.
- A source institution.
- A storage facility.

An entity may be physical, organisational, digital or conceptual. The important requirement is that the system can distinguish what it refers to.

#### B. Attributes

An **attribute** describes a property of an entity or record.

Examples:
- A market's name and location.
- A product's form or grade.
- A cooperative's registration identifier, if established.
- An observation's original unit or publication date.

Attributes should preserve the meaning and precision of the underlying information. Do not invent a more precise location, product grade or date than the evidence supplies.

#### C. Relationships

A **relationship** describes how two or more entities are connected.

Examples:
- A quotation refers to a product at a market.
- A cooperative is registered at an address.
- A source publishes a price observation.
- A processor processes a particular product.
- A shipment moves from an origin to a destination.

Relationships may need their own evidence, dates, status and source references. The existence of two entities in the same record does not always establish a real-world relationship between them.

For example, a page mentioning a cooperative and a product in the same paragraph may not establish that the cooperative produced that product.

#### D. Events

An **event** is something that happens at a particular time or during a period and may change the situation.

Examples:
- A price quotation is issued.
- A transaction is completed.
- A shipment departs or arrives.
- A product is harvested.
- A market is temporarily closed.
- A report is published or revised.

Events should not be confused with static attributes. A market has a name and location; a quotation is an event or observation associated with that market at a particular time.

Chapter 4.2 will examine how events and actions relate to changes in state.

### 7. Identity, names and avoiding false matches

Two records may refer to the same real-world entity even when their names differ. Conversely, two different entities may share similar or identical names.

Examples:
- A market may have a formal name and a locally used alternative.
- A cooperative may use an abbreviation in one source and its full registered name in another.
- Two villages may share a name in different LGAs.
- Different product forms may be described using the same informal commodity name.

A problem representation should not assume that matching names prove identity.

Where available, use suitable identifiers and supporting attributes such as:
- Registration or official reference numbers.
- Administrative area and geographic coordinates.
- Source-specific identifiers.
- Known aliases and alternative spellings.
- Product codes or clearly defined classifications.

When identity cannot be resolved, retain separate candidate records or mark the match as uncertain. Do not merge records merely because they look similar.

The appropriate identifier and matching method depend on the entity type and available evidence. This lesson does not prescribe a final database schema for the agricultural pilot.

### 8. Choosing the right level of abstraction

**Abstraction** means deliberately leaving out details that are not needed for the current problem while retaining what matters.

A representation that includes every detail may become too complicated to reason about. A representation that omits essential detail may lead to incorrect conclusions.

Consider two levels of a tomato-market investigation:

- **Too broad:** "Agriculture in Plateau State."
- **More useful for a bounded question:** "Fresh tomato wholesale quotations, a specified grade or product description, from selected named markets during two defined observation periods, with original units and sources retained."

The second description is more useful because it identifies what must be compared.

But it may still be too broad if the task concerns one specific market and one trader's quotation. It may be too narrow if the intended decision concerns supply across multiple states.

Choose the representation level according to:
- The question being answered.
- The decisions the output will support.
- The precision of available information.
- The risks of omitting a relevant factor.
- The resources and time available.
- The required level of explanation and auditability.

The goal is not maximum detail. It is sufficient, task-relevant detail.

### 9. Observability and partial knowledge

An agent rarely has direct access to the complete environment. It usually receives observations through sources, sensors, APIs, documents, user instructions or other interfaces.

The real environment and the agent's representation of it are therefore not identical.

For example:
- A physical market exists, but the agent may only see a published price page.
- A transaction may have occurred, but no public record may be available.
- A producer may operate in a village, but the agent may only have a state-level directory entry.
- A dataset may contain a model-estimated price rather than a direct market observation.

A careful representation distinguishes:

- **Known:** supported by the evidence currently available.
- **Observed but not independently verified:** recorded from a source, with its status made explicit.
- **Inferred:** derived by reasoning from other information.
- **Unknown:** not established.
- **Unavailable:** not currently accessible through the system's authorised interfaces.
- **Contradicted or disputed:** relevant sources or observations conflict.

Unknown and unavailable are not the same. A fact may be known to someone or recorded somewhere but unavailable to this agent. Likewise, a missing field does not mean the real-world attribute does not exist.

The representation should preserve uncertainty rather than fill gaps with invented values.

### 10. A candidate representation for the agricultural pilot

Suppose we want to investigate whether tomato wholesale quotations changed in a small set of markets.

A provisional task representation could look like this:

| Representation area | Candidate description |
|---|---|
| Task | Compare selected tomato wholesale quotations across two defined observation periods. |
| Product | Fresh tomatoes; exact grade/form still to be defined from real source examples. |
| Locations | Selected named markets; not assumed to represent all Plateau markets. |
| Time | Two specified periods; observation date retained separately from collection date. |
| Source records | Original pages, reports, files or authorised observations. |
| Observation records | Original quotation, original unit, market, product description and date where available. |
| Relationships | Each observation refers to a particular product description and market, and is attributed to a source. |
| Evidence status | Verified quotation, unverified information or another applicable working evidence level. |
| Unknowns | Missing grade, unclear unit, stale date, uncertain location or unverified source. |
| Output | A traceable comparison showing what is comparable, what is not, and what remains uncertain. |
| Boundaries | No claim about a completed transaction or statewide trend unless separate evidence supports it. |

This is a teaching representation, not an approved data model or a selected pilot scope. We have not yet inspected enough raw source data or validated user needs to finalise these fields.

A simplified conceptual view is:

```text
External market / institution / platform
                  |
                  v
          Source document or feed
                  |
                  v
           Recorded observation
             /           \
            v             v
     Product reference   Market reference
            \             /
             v           v
        Evidence and claim assessment
                  |
                  v
         Reviewed intelligence output
```

This diagram shows a possible information path. It does not claim that any integration or automated process has already been implemented.

### 11. A practical method for representing a new problem

When an agent receives a task, it can build a first representation through the following questions:

1. **What is the task?** State the objective and requested output.
2. **What is the scope?** Identify the relevant entities, locations, products, periods and activities.
3. **What is the environment?** Identify relevant actors, processes, events, sources, resources and conditions.
4. **Where is the system boundary?** Determine what the system controls, what is external and which interfaces are authorised.
5. **What entities matter?** Identify the real-world things and distinguish them from their digital records.
6. **What attributes matter?** Record the properties necessary to understand and compare the entities.
7. **What relationships matter?** Describe the connections needed for the task, including evidence and dates where relevant.
8. **What events matter?** Identify time-dependent occurrences that may affect the problem.
9. **What is actually known?** Separate observations, verified facts, claims, inferences, unknowns and unavailable information.
10. **What level of detail is sufficient?** Avoid both an overly broad description and an unnecessarily complex model.
11. **What is missing?** Identify the information needed to proceed and whether clarification or additional research is necessary.
12. **What must the representation not imply?** Record important boundaries, such as a quotation not proving a transaction or a local sample not representing a whole state.

This is a practical reasoning aid, not a compulsory software architecture or universal data-modelling standard.

### 12. Common representation failures and safeguards

| Failure | What goes wrong | Safeguard |
|---|---|---|
| Vague problem statement | The agent does not know exactly what is being investigated. | Define task, scope, output and time period. |
| Environment overreach | Irrelevant complexity is included. | Represent only task-relevant parts of the environment. |
| Missing boundary | The agent assumes it controls an external system or organisation. | Mark internal, external, connected and unauthorised elements. |
| Entity-record confusion | A database entry is treated as the real-world entity itself. | Keep entity identity, source record and claim distinct. |
| False entity matching | Similar names are merged incorrectly. | Use identifiers and evidence; preserve uncertain matches. |
| Relationship invention | Two entities mentioned together are treated as connected. | Record the source and evidence for each material relationship. |
| Time loss | Observations from different periods are treated as equivalent. | Preserve event/observation dates and collection dates. |
| False precision | Missing locations, units or grades are guessed. | Preserve original precision and mark missing details. |
| Over-abstraction | Important distinctions disappear. | Retain distinctions that affect the decision or evidence. |
| Over-modelling | The representation becomes too complicated to use. | Start with the minimum sufficient representation and expand when justified. |
| Hidden uncertainty | Unknown or inferred details appear as established facts. | Label known, observed, inferred, unknown, unavailable and disputed information. |

### 13. Key principles

- A problem representation structures the task so that reasoning and planning can operate on it.
- An environment representation describes the task-relevant external world, not every detail of reality.
- Define scope and system boundaries explicitly.
- Distinguish real-world entities from digital records, source documents and claims about them.
- Separate entities, attributes, relationships and events.
- Do not infer identity or relationships from similar names or co-occurrence alone.
- Preserve the dates, units, location precision and original meaning of observations.
- An agent's representation is partial and dependent on the observations and authorised interfaces available to it.
- Unknown, unavailable, unverified and false are different states.
- Use the level of abstraction that preserves the distinctions relevant to the task.
- Treat candidate representations as provisional until tested against real requirements and evidence.
- Do not let a structured representation create an appearance of certainty that the underlying sources do not support.

## Lesson checkpoint

A source lists a cooperative in Village A and associates it with tomatoes. Another source lists a tomato quotation in a nearby market. An agent combines the records and reports that the cooperative supplied tomatoes to that market during the current season.

That conclusion is not supported by the representation. The two records may describe relevant entities, but the source material has not established a supply relationship, a transaction or a current-season event.

A better representation keeps the cooperative record, product association, market quotation and their sources separate. It marks the supply relationship as unknown unless suitable evidence is found.

The central discipline of problem and environment representation is to describe what matters accurately, preserve what is known and unknown, and avoid allowing the structure of a model to imply relationships or facts that have not been established.

---

## Chapter 4 progress

Subsection 4.1, Problem and Environment Representation, is covered. Next: **4.2 Current State, Goal State and State Changes**.
