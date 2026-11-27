# Chapter 2 — Goals, Instructions and Problem Formulation

**Status:** In progress.

## Chapter learning sequence

1. **2.1 Objectives, Goals and Desired Outcomes:** Covered.
2. **2.2 Interpreting Instructions and Identifying Intent:** Planned.
3. **2.3 Goal States and Conditions for Success:** Planned.
4. **2.4 Constraints, Priorities and Conflicting Objectives:** Planned.
5. **2.5 Ambiguity, Missing Requirements and Clarification:** Planned.

---

## 2.1 Objectives, Goals and Desired Outcomes

### Core question

When an agent or system is given a broad purpose, how do we express what it is actually expected to achieve, what specific targets it should pursue and what useful change should result?

The terms **objective**, **goal** and **desired outcome** are closely related. In practice, organisations and methodologies sometimes use them differently or interchangeably. For this project, we will use a consistent working vocabulary so that our designs, instructions and records remain clear.

- **Objective:** the broader result or direction the system is intended to pursue.
- **Goal:** a more specific target state or result that contributes to an objective.
- **Desired outcome:** the useful change or value expected for a user, organisation or environment when the goal is achieved.
- **Task:** a bounded unit of work assigned to a person, agent or component in pursuit of a goal.

These definitions are a project working convention, not a claim that every engineering framework uses the words identically.

### 1. Objective — the broader intended result

An objective describes what a system or activity is ultimately trying to accomplish at a particular level.

It gives direction and helps determine which goals and tasks are relevant.

An objective should describe the intended result or value, not merely name a technology or feature.

For example:

- Weak: "Build an AI agent for agriculture."
- Better: "Improve the availability and traceability of useful intelligence about agricultural products, production, processing and markets so that people can make better-informed decisions."

The first statement describes a proposed solution. It does not explain which problem the agent should solve or what value the system should produce.

The second describes an intended result. It still needs to be translated into more specific goals and requirements, but it provides a clearer direction.

### 2. Goal — a specific target that contributes to an objective

A goal makes the objective more concrete. It describes a result the system or a particular activity should reach.

A goal should be bounded sufficiently that we can later determine whether it has been achieved.

For example, one operational goal within an agricultural intelligence pilot might be:

"Produce a traceable evidence record for a defined set of agricultural product observations in an agreed pilot scope, preserving product form, location, observation date, unit where relevant, source and evidence status."

This goal is more specific than the broader objective. It identifies a result that can be examined.

A goal can belong to different levels:
- A project-level goal may establish what the overall initiative should accomplish.
- A system-level goal may describe what a system capability should deliver.
- An operational goal may define a particular result within a work cycle.
- An agent-level goal may define the bounded result assigned to an agent.

The goal assigned to an agent must remain within its role, responsibility and authority. A broad organisational objective does not give an individual agent permission to pursue every possible means of achieving it.

### 3. Desired outcome — the value or change that should result

A desired outcome describes why achieving a goal matters.

It focuses on the useful change, not only the system's output.

Consider an agricultural information process:

- **Output:** a structured record showing a producer, product, location, source and observation date.
- **Desired outcome:** an analyst can trace the information, understand what is known and identify what needs further verification.
- **Possible wider impact:** better-informed decisions about sourcing, supply, market access or investment.

The system can produce the record. It can help enable better decisions. It cannot guarantee that a buyer will purchase the produce, that a business will make a profit or that market conditions will improve. Those results depend on many factors beyond the system's control.

This distinction prevents us from confusing the delivery of software outputs with the achievement of real-world value.

### 4. Distinguish objective, goal, outcome and task

| Concept | What it describes | Example in agricultural intelligence |
|---|---|---|
| Objective | Broader intended result | Improve traceable understanding of the agricultural ecosystem and relevant opportunities. |
| Goal | Specific target result | Produce an evidence-backed record for a defined pilot scope. |
| Desired outcome | Useful change or value | Users can inspect the evidence and identify what is known or still needs verification. |
| Task | Bounded work to perform | Collect and classify available observations for the agreed scope. |

An output is also distinct from an outcome:

- **Output:** what the system directly produces, such as a registry entry, report, map, notification or analysis.
- **Outcome:** the change or benefit that the output helps a user achieve.
- **Impact:** a broader, often longer-term effect to which several activities and external factors may contribute.

A dashboard is an output. Better visibility and more informed decisions may be outcomes. Improved livelihoods or market efficiency may be longer-term impacts, but they should not be claimed merely because a dashboard exists.

### 5. Objectives and goals operate at different levels

A complex initiative usually has several connected levels of objectives and goals.

For this project, the hierarchy can be understood as:

**Project purpose**
Why are we undertaking Agentic AI Engineering?

↓  

**Sector pilot objective**
What practical capability are we trying to establish in the first domain?

↓  

**System or capability objectives**
What useful results should particular parts of the pilot deliver?

↓  

**Operational goals**
What bounded results must be achieved in a particular activity or period?

↓  

**Tasks**
What work must a person, agent or component perform?

This hierarchy helps prevent an individual agent from interpreting an extremely broad purpose as an unrestricted instruction.

The hierarchy is not necessarily a rigid one-way structure. A goal may contribute to more than one objective, and a practical discovery may require us to revise a proposed goal. Such changes should be recorded rather than silently assumed.

### 6. Apply this to our agricultural pilot

Agriculture is our first practical pilot path, but the intended scope is the wider agricultural ecosystem, not just a single commodity or price-monitoring activity.

A candidate pilot objective, for discussion and refinement, is:

"Develop and validate a practical agricultural intelligence capability that discovers, organises, assesses and connects evidence about agricultural products, producers, production locations, processing, movement, markets and opportunities, so that users can investigate the ecosystem and make better-informed decisions."

This is a **working draft**, not a final approved system specification. It expresses the broad direction while leaving the actual priorities, coverage, evidence standards, users and operating requirements to be established through practical discovery.

The objective could support several families of goals:

- Discover and organise agricultural products and their relevant forms, including raw produce, processed products and commercially useful by-products.
- Identify producers, production locations, cooperatives, facilities and relevant ecosystem participants.
- Connect products and production origins to processing, distribution and market destinations where evidence is available.
- Collect and compare market observations while preserving source, date, location, unit and evidence status.
- Identify changes, gaps, risks and potential opportunities for further investigation.
- Produce traceable intelligence that supports human decisions.

These are candidate goal areas. They do not imply that every capability must be built immediately, that every data source is available or that all information has already been verified.

### 7. Convert a broad goal into a bounded operational goal

The long-term agricultural objective is broad. A practical pilot still needs bounded goals that can be attempted and evaluated.

For example, an operational goal could be:

"Within an agreed test scope, create and review a set of agricultural information records that preserve the required identity, location, source, date and evidence-status fields, and identify incomplete or conflicting records instead of presenting them as verified."

This is deliberately bounded. The test scope might specify a set of products, locations, sources or an observation period. Defining a test scope does not permanently narrow the wider agricultural programme; it makes a particular experiment manageable.

A second goal might focus on connecting information:

"Within an agreed pilot scope, link a discovered product to its documented production origin, processing stage and market destination where supporting evidence exists, and leave unsupported links explicitly unresolved."

This prevents the system from inventing supply-chain connections simply to make a registry look complete.

### 8. From goals to tasks without jumping to tools

Once a goal is clear, it can be translated into work.

For the information-record goal, possible tasks include:

1. Agree which fields are necessary for the selected record type.
2. Identify the relevant information sources.
3. Determine what access and reuse conditions apply.
4. Collect available observations.
5. standardise terms, units and location references where appropriate.
6. Record source details and evidence status.
7. Identify missing, conflicting or outdated information.
8. Review whether the records satisfy the agreed acceptance conditions.

These are task descriptions, not a choice of tools or an implementation architecture. Some may later be handled by existing platforms, conventional software, agents or people.

The important order is: understand the result first, then identify the work and the capabilities required to perform it.

### 9. A goal must not become an unlimited instruction

Consider the objective:

"Discover agricultural opportunities."

Taken literally, an agent might attempt to contact businesses, publish claims, recommend purchases or commit resources in the name of discovering opportunities.

That would be unsafe and poorly specified.

A bounded goal could instead be:

"Identify candidate agricultural opportunities from approved information sources and prepare an evidence-backed assessment for human review."

This defines the expected result while leaving consequential decisions and external commitments under the proper authority.

The agent's goal must always be consistent with:
- Its assigned role and responsibilities.
- Its permitted data and action authority.
- The available evidence.
- Relevant constraints and policies.
- Required human approvals.
- The conditions under which it must stop or escalate.

Goals guide behaviour; they do not create permissions.

### 10. Avoid confusing activity with achievement

A system can be very busy without achieving its objective.

Examples:

- Collecting thousands of records does not necessarily create useful intelligence.
- Producing many reports does not prove that users understand the market better.
- Listing potential suppliers does not establish that they are active or reliable.
- Identifying a possible opportunity does not prove commercial viability.
- Creating a map does not prove that the mapped relationships are accurate.

We must evaluate the result against the goal and the desired outcome, not merely count activity or outputs.

This lesson introduces the distinction. Detailed goal states, acceptance conditions and success measures are developed in subsection 2.3.

### 11. A practical objective-and-goal formulation worksheet

For any proposed system capability, answer:

1. **Purpose:** Why does this capability matter?
2. **Objective:** What broader result should it contribute to?
3. **Goal:** What specific target result must be achieved?
4. **Beneficiary:** Who should receive value from the result?
5. **Desired outcome:** What useful change should occur for that beneficiary?
6. **Output:** What will the system actually produce?
7. **Scope:** What is included and excluded in this particular goal?
8. **Evidence:** What would allow us to judge whether the result is real?
9. **Authority:** What may the responsible agent or component do, and what requires approval?
10. **Unknowns:** What must be clarified before the goal can be finalised?

The worksheet is a thinking aid, not a substitute for the detailed goal-state and success-condition work in subsection 2.3.

### 12. Common mistakes

Avoid:
- Defining the objective as "build an AI agent" without stating the intended value.
- Writing goals so broadly that nobody can determine whether they have been achieved.
- Confusing a system output with a real-world outcome.
- Treating long-term impact as something the system can guarantee.
- Assigning an agent an organisation-wide objective without giving it a bounded responsibility.
- Assuming an objective grants permission to take any action that might help.
- Making the pilot scope so broad that no practical test can be completed.
- Permanently narrowing the entire programme merely because an initial experiment uses a limited test scope.
- Treating candidate goals as approved requirements before they have been examined.

### Principles established

- An objective gives broader direction; a goal defines a more specific target result.
- A desired outcome describes the useful change or value expected from achieving a goal.
- A task is a bounded unit of work; an output is what the system produces.
- Outputs, outcomes and longer-term impacts must not be confused.
- Terms may vary across methodologies, so this project uses explicit working definitions.
- Goals should be specific and bounded enough to guide work and later evaluation.
- Broad objectives must be translated into goals and tasks appropriate to each system component or agent.
- An agent's goal must remain within its assigned responsibility and authority.
- The agricultural pilot's broad objective is a working draft to be refined through practical discovery.
- A bounded test scope does not permanently narrow the wider agricultural programme.
- Measure achievement by the intended result and evidence, not merely by activity or volume of outputs.
- Do not select tools or build components before understanding the goal and required capability.

## Continuation point

Continue with **2.2 Interpreting Instructions and Identifying Intent**. Subsections 2.2–2.5 remain planned.
