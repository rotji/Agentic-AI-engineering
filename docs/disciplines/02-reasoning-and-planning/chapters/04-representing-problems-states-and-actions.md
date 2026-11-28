# Chapter 4 — Representing Problems, States and Actions

**Status:** In progress; subsections 4.1–4.2 covered.

## Purpose

Learn how to describe the situation an agent is reasoning about and the possible changes its actions may produce. This chapter begins by representing a problem and its environment, then examines states, actions, preconditions, effects, constraints, resources, time, dependencies and state spaces.

## Chapter learning sequence

1. **4.1 Problem and Environment Representation:** Covered.
2. **4.2 Current State, Goal State and State Changes:** Covered.
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

## 4.2 Current State, Goal State and State Changes

### Core question

How does an agent describe the situation as it stands now, define the situation it is trying to achieve, and track what changes as actions and events occur?

In planning, an agent needs more than a general objective. It needs a description of the relevant starting situation, a clear description of the desired result and a way to recognise changes between them.

A **state** is a representation of the task-relevant conditions at a particular point or stage. It is not necessarily a complete description of the real world. It contains the details needed to understand the task, assess progress and choose what may happen next.

The **current state** represents how things stand now, based on the information available and the system's defined scope.

The **goal state** represents the conditions that should hold for the task to count as achieved.

A **state change** is a change in one or more relevant conditions over time. It may result from an agent action, an external event, another actor's activity or the arrival of new information.

### 1. What does "state" mean?

Imagine that an agricultural intelligence workflow is investigating a tomato quotation.

At a particular moment, relevant information might be:

- The source page has been found.
- The page displays a quotation for tomatoes.
- The market name is given.
- The observation date is stated.
- The quoted unit is unclear.
- The source has not been independently checked.
- No evidence of a completed transaction has been found.

Together, these facts and unresolved conditions describe the task-relevant state of this investigation at that moment.

The state is not simply "tomato prices are high." It records the conditions that matter for the task, including what is known and what remains unresolved.

A state can be represented in prose, a table, a structured record, variables, a database or another suitable form. The representation depends on the problem and how it will be used.

### 2. Current state: where are we now?

The **current state** is the best available representation of the relevant situation at the time of assessment.

It should identify:
- What has already happened.
- What information or resources are currently available.
- Which conditions have been satisfied.
- Which conditions remain unsatisfied.
- What is unknown, unavailable, disputed or outdated.
- What actions or decisions are currently possible or blocked.

The current state must be based on evidence, not on what the agent expects to be true.

For example, a task record may say "source inspected" only when the source has actually been opened and checked. Merely finding a search result is not the same as inspecting the underlying source. Likewise, "data imported" must not be recorded simply because a download link was found.

The current state is also time-sensitive. It may become stale as the external world changes or as new information arrives. A state representation should therefore preserve relevant dates and identify when it was last checked.

### 3. Goal state: what condition are we trying to reach?

The **goal state** describes the conditions that must hold for the intended result to be achieved.

It is different from a list of activities.

Consider this instruction:

"Download five agricultural datasets."

That describes an activity or output target. It does not establish that the datasets are relevant, usable, permitted for the intended purpose or sufficiently understood.

A more meaningful goal state for a bounded source-assessment task might be:

- The selected source has been inspected.
- Its actual coverage and data fields have been recorded.
- The source's access and reuse conditions have been checked to the extent required for the intended use.
- The distinction between direct observations and derived estimates is understood.
- Important limitations and unresolved questions are documented.
- A reviewer can trace the assessment to the source material.

The goal state describes what must be true at completion, not merely what the agent must do along the way.

A goal can have several acceptable final states. For instance, the source may prove suitable, unsuitable or only partly suitable. The task may be complete when its suitability has been assessed and a justified decision recorded—even if the decision is not to use that source.

### 4. Current state versus goal state

The difference between the current state and goal state helps reveal the work that remains.

| Dimension | Current state | Goal state |
|---|---|---|
| Source access | A source is listed but not yet inspected. | The relevant source material has been inspected or the access limitation is documented. |
| Coverage | Geographic and product coverage are uncertain. | Actual coverage and gaps are recorded from the source. |
| Data meaning | It is unclear whether values are quotations, transactions or estimates. | The type and meaning of the data are identified, or explicitly unresolved. |
| Reuse conditions | Licence or terms are not checked. | Relevant access and reuse conditions are assessed before the proposed use. |
| Evidence | Some claims are based on published descriptions. | Each important claim is linked to inspected supporting evidence or marked unresolved. |
| Decision | Suitability is unknown. | A reasoned decision is recorded: reuse, integrate, investigate further, reject or defer. |

The difference is not necessarily a numerical gap. It is a difference in conditions that need to be changed or established.

A useful planning question is:

**What is true now, what must be true at completion, and what needs to change or be learned to get there?**

### 5. State changes: how does the situation change?

A **state change** occurs when a relevant condition becomes different.

In an agentic task, state changes may arise from several sources:

- **Agent action:** the agent performs an authorised operation, such as saving an inspected source record.
- **External event:** something happens outside the system, such as a market closing or a new price being published.
- **Another actor's action:** a data provider updates a dataset or a reviewer approves a record.
- **New observation or information:** the agent receives additional evidence about a condition.
- **Correction:** an existing record is amended after an error is discovered.
- **Time passing:** information becomes older, a deadline approaches or a previously valid status expires.

The agent needs to understand which kind of change occurred because they do not all have the same meaning or cause.

For example, saving a market quotation to a database changes the system's stored records. It does not change the price in the physical market. Discovering a new report may change what the agent knows without changing the real-world event being described.

### 6. Real-world state versus the agent's information state

This is a crucial distinction.

The **real-world state** is how the external situation actually stands, whether or not the agent knows it.

The **information state** (or knowledge/belief state, depending on the system) is what the agent currently has recorded or considers possible based on its observations and evidence.

These may differ.

Example:

- **Real-world situation:** A trader completed a tomato transaction in a market.
- **Agent's information state:** The system has no record of that transaction.
- **Later observation:** An authorised transaction receipt is provided.
- **Updated information state:** The system now has evidence of the transaction, subject to checks on the receipt and its meaning.

The observation changed the agent's information state. It did not cause the earlier transaction to happen.

Similarly:
- A market price can change while the agent's stored record remains unchanged.
- A new dataset can be downloaded while the real-world market condition remains unknown.
- A source can be corrected without the underlying historical event changing.
- A record can be marked "verified" after review, even though the real-world event occurred earlier.

An agent must not confuse a change in what it knows with a change in the world itself.

For partially observable environments, the agent's internal representation may contain uncertainty or multiple possible states. The available evidence does not always identify one definitive real-world state.

### 7. State, task progress and workflow status are related but different

These concepts are sometimes mixed together, but it is useful to distinguish them.

- **World state:** task-relevant conditions in the external environment.
- **Information state:** what the agent's records or evidence currently support.
- **Task state:** the current condition of the problem being worked on, including relevant facts and unresolved requirements.
- **Workflow status:** where the process is in its execution, such as not started, in progress, awaiting review, blocked or complete.

For example, a source assessment may have the workflow status "awaiting review." The underlying information state may already contain the source URL, extracted fields and evidence notes. The real-world data publisher may have made no change at all.

A process being marked "complete" is not proof that its intended outcome was achieved. The result must be checked against the goal conditions.

### 8. A worked agricultural example

Suppose the pilot is assessing whether a candidate source can support a particular agricultural market-information task.

**Starting current state:**
- The source's public page has been located.
- Its description claims to provide agricultural market prices.
- The actual downloadable data has not been inspected.
- Market coverage, units and observation dates are not established.
- The data's reuse conditions are not yet checked.
- The source has not been approved for the intended use.

**Desired goal state:**
- The relevant data or source material has been inspected, or an access failure is documented.
- The actual products, markets, units and dates are recorded where available.
- Direct observations, estimates and other data types are distinguished where the source permits.
- Data access and reuse conditions are assessed for the proposed use.
- Limitations and gaps are documented.
- A justified suitability decision is recorded and reviewable.

**Possible state changes during the investigation:**

| Event or action | What changes? | What does not automatically change? |
|---|---|---|
| The agent opens the source page. | Its information state gains an inspected page and metadata. | The underlying market conditions do not change. |
| A data file is downloaded. | The system now possesses a copy of the file. | The data is not thereby verified or permitted for every use. |
| The file is inspected. | Its recorded knowledge of fields, coverage and structure changes. | The source's underlying collection method is not proven merely by reading the file. |
| A reviewer checks the licence. | The assessment of permitted use becomes more informed. | The reviewer does not grant rights that the provider has not granted. |
| A provider publishes a new dataset version. | The external source and potentially the available data change. | The system's local copy remains unchanged until refreshed. |
| A reviewer approves the assessment. | The workflow status may change to approved for the stated scope. | That approval does not establish suitability for every other purpose. |

This example shows why states need to be defined carefully: actions, observations, external events and decisions can change different parts of the overall situation.

### 9. Progress does not necessarily mean goal achievement

A task can make progress without reaching its goal state.

For example:
- Finding five source websites is progress.
- Downloading a dataset is progress.
- Creating a spreadsheet is progress.
- Running an automated process is progress.

None of these alone proves that the data is accurate, relevant, permitted, representative or useful.

Likewise, a goal can be achieved through an outcome other than the one initially expected.

A source assessment may conclude that a provider is unsuitable. If the task was to assess the provider and make a justified decision, that may satisfy the goal state.

The system should distinguish:
- **Not started**
- **In progress**
- **Awaiting evidence**
- **Awaiting review or approval**
- **Blocked**
- **Completed successfully**
- **Completed with limitations**
- **Rejected or determined unsuitable**
- **Cancelled or superseded**

These are possible workflow labels for a system, not universal required values. Their definitions should be explicit so that different agents and users do not interpret them inconsistently.

### 10. Representing a state over time

A state representation should preserve enough temporal information to make changes understandable.

For an agricultural observation, relevant times may include:
- **Event time:** when a real-world event occurred, such as a transaction.
- **Observation time:** when the price or condition was observed.
- **Publication time:** when a source published the information.
- **Collection time:** when the system retrieved or recorded it.
- **Review time:** when a person or process checked it.
- **Update time:** when the local record was last changed.

These times may be different. Do not use one timestamp as a substitute for another.

Where records are updated, preserve the history needed to understand what changed, when it changed and why. A current value without history may be inadequate for analysing trends or explaining earlier decisions.

A state representation should also distinguish:
- A value that is genuinely zero.
- A value that is missing.
- A value that is unknown.
- A value that is unavailable.
- A value that is estimated.
- A value that is stale or expired.

These conditions have different meanings and should not be collapsed into one empty field or a guessed default.

### 11. How an agent can compare current and goal states

A practical method is:

1. **Define the task and scope.** State what problem is being addressed and which parts of the environment matter.
2. **Describe the current state.** Record relevant conditions and their evidence, dates and uncertainty.
3. **Define the goal state.** Specify the conditions that must hold for the task to count as achieved.
4. **Compare them.** Identify which goal conditions are already satisfied, which are not, and which cannot yet be assessed.
5. **Identify possible changes.** Determine what actions, external events or new observations could change the relevant state.
6. **Check authority and feasibility.** Do not treat a possible state change as permission to perform an action.
7. **Track actual results.** After an action or event, observe the result rather than assuming the intended change occurred.
8. **Update the representation.** Record what changed, what remained the same and what is newly uncertain.
9. **Reassess the goal.** Determine whether the goal conditions are satisfied, partially satisfied, blocked or no longer appropriate.
10. **Preserve history.** Keep relevant prior states and reasons for changes where traceability matters.

The next subsection will examine actions, preconditions and effects more directly. Here, the important idea is that a plan must be based on a representation of the current situation and the conditions it is trying to reach.

### 12. Common state-representation failures and safeguards

| Failure | What goes wrong | Safeguard |
|---|---|---|
| Current state assumed rather than observed | The agent plans from a false starting point. | Record the evidence and date supporting the current state. |
| Goal described as an activity | The system tracks work performed instead of the intended result. | Define observable completion conditions. |
| World state confused with information state | Learning new information is reported as though the world changed. | Track external conditions and agent knowledge separately. |
| Workflow completion confused with success | A process is marked complete without satisfying the goal. | Check the result against the goal conditions. |
| Intended effects assumed to have happened | An action attempt is treated as a successful state change. | Observe and verify the actual result. |
| Time dimensions collapsed | Publication, observation and collection dates are mixed. | Preserve distinct timestamps where relevant. |
| Missing values guessed | Unknown or unavailable information appears as fact. | Preserve explicit missingness and uncertainty. |
| Stale state | External conditions change but the representation is not refreshed. | Define freshness requirements and review triggers. |
| History overwritten | Earlier values and decision context disappear. | Preserve change history proportionate to the task. |
| Goal conditions become obsolete | The task continues toward an outdated result. | Reassess goals when requirements or external conditions change. |

### 13. Key principles

- A state is a task-relevant representation of conditions at a particular point or stage.
- The current state describes how things stand now, according to the available evidence and scope.
- The goal state describes the conditions that must hold for the intended result to be achieved.
- Goals should describe outcomes or conditions, not merely activities.
- State changes may result from agent actions, external events, other actors, corrections or new observations.
- A change in the agent's information state is not necessarily a change in the real world.
- World state, information state, task state and workflow status should not be confused.
- Attempted actions do not guarantee their intended effects.
- Progress does not automatically mean goal achievement.
- Preserve relevant event, observation, publication, collection, review and update times.
- Missing, unknown, unavailable, estimated, zero and stale values are different.
- Current and goal states should be compared repeatedly as the task evolves.
- Preserve history when it is needed to explain changes, assess evidence or audit decisions.

## Lesson checkpoint

An agent finds a new public dataset and downloads it. The dataset contains an estimate suggesting that tomato prices in a particular market changed during the previous month.

Which state changed when the file was downloaded?

**The system's information state changed:** it now possesses a new file. The real-world market price did not change as a result of the download. The estimated value also does not automatically become a verified transaction or a direct observation.

The task goal may still be incomplete until the agent checks the dataset's provenance, date, unit, market definition, estimation method and permitted use.

This is the central discipline of subsection 4.2: represent where things stand, define what must be true at completion, and track actual changes without confusing actions, observations, information and real-world events.

## Chapter 4 progress

Subsections 4.1, Problem and Environment Representation, and 4.2, Current State, Goal State and State Changes, are covered. Next: **4.3 Actions, Preconditions and Effects**.
