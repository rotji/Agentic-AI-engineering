# Chapter 1 — Foundations of Reasoning and Planning

**Status:** In progress.

## Purpose

Establish what reasoning and planning mean in an agentic system, how they contribute to goal-directed behaviour, and why a system needs to distinguish forming an understanding from deciding how to proceed.

## Chapter learning sequence

1. **1.1 What Reasoning and Planning Mean in Agentic Systems:** Covered.
2. **1.2 Reasoning vs Planning vs Decision-Making vs Execution:** Planned.
3. **1.3 How Reasoning and Planning Fit into an Agent's Operation:** Planned.
4. **1.4 Deliberative and Reactive Behaviour:** Planned.

---

## 1.1 What Reasoning and Planning Mean in Agentic Systems

### Core question

When an agent receives an objective, how does it work out what the situation means and what it should do to make progress?

Two important capabilities are involved: reasoning and planning.

- **Reasoning** helps an agent interpret information, examine relationships, draw or assess conclusions, identify uncertainty and work through a problem.
- **Planning** helps an agent formulate a possible course of action: what needs to happen, in what order, under which conditions and toward what intended result.

They are related, but they answer different questions.

**Reasoning asks:** What do we know, what does it mean, what can we infer, and what remains uncertain?

**Planning asks:** Given the objective and what we currently understand, what steps could move us toward the desired result?

These are engineering descriptions of system capabilities. They do not imply that an AI agent has human consciousness or experiences thought in the human sense.

### 1. Why does an agent need reasoning?

An agent often receives incomplete, variable or ambiguous information. It may need to interpret the objective, examine supplied information, identify relevant facts, recognise contradictions, consider possible explanations and determine what information is missing.

Reasoning supports activities such as:

- Interpreting the task and its context.
- Identifying relevant information.
- Comparing observations.
- Recognising relationships and inconsistencies.
- Drawing conclusions from available evidence.
- Forming possible explanations or hypotheses.
- Identifying assumptions and information gaps.
- Assessing whether there is enough basis to continue or whether clarification is needed.

Reasoning does not guarantee that a conclusion is correct. An agent may misunderstand an instruction, overlook evidence, rely on a weak assumption or produce a convincing but unsupported explanation. Its conclusions therefore need to be assessed against evidence, constraints and the consequences of error.

### 2. Why does an agent need planning?

Understanding a problem does not automatically solve it.

An agent may conclude that a market price observation appears unusual, but it still needs to determine what should happen next.

Planning helps organise possible actions into a course of work. Depending on the problem, a plan may identify:

- The objective to be achieved.
- The current situation as understood.
- The steps or actions that may be required.
- The order in which those steps should happen.
- Dependencies and preconditions.
- Required information or resources.
- Expected results.
- Constraints and authority limits.
- What to do if an important step cannot be completed.
- What condition would mean the plan is complete or should stop.

A plan is a proposed course of action, not proof that the actions have been carried out or that they will succeed. Its feasibility and authority must be checked before execution.

### 3. A simple example: investigating an unusual agricultural price

Imagine an agricultural intelligence system receives a report that the price of a 50-kilogram basket of tomatoes has increased sharply in one market.

The agent should not immediately announce that tomatoes are becoming scarce or that prices are rising across the state. It first needs to understand what the report actually establishes.

#### Reasoning: understand the situation

The agent may examine questions such as:

1. What market and location does the observation refer to?
2. Is the price expressed per basket, kilogram or another unit?
3. When was the price observed?
4. What is the source, and what evidence supports the report?
5. Is there a comparable earlier observation?
6. Are other sources reporting a similar change?
7. Could the difference be explained by quality, quantity, season or another factor?
8. What remains unknown?

The agent may conclude that the reported increase is worth investigating, but that the evidence is not yet sufficient to establish its cause or whether it applies to other markets.

That is reasoning: examining information and establishing what can and cannot be concluded.

#### Planning: determine a suitable investigation

The agent may then formulate a plan:

1. Check that the original observation contains the required market, date, unit and source details.
2. Seek comparable observations from the same market.
3. Compare relevant observations from other approved sources.
4. Check whether the products and units are genuinely comparable.
5. Investigate possible explanations if the evidence supports further inquiry.
6. Prepare findings that distinguish confirmed observations, hypotheses and unresolved questions.
7. Escalate if important evidence is missing or the conclusion would require a decision beyond its authority.

That is planning: arranging possible steps to address the problem.

The example does not mean the agent has already collected the additional evidence or completed the investigation. It has only formed a proposed course of work.

### 4. Reasoning and planning influence each other

Reasoning and planning are not always two isolated stages where one ends permanently before the other begins.

A plan may reveal that the agent needs information it does not have. It may then reason about how to obtain that information and revise the plan.

For example:

- The agent plans to compare prices across three markets.
- It discovers that one market's observation has no reliable date.
- It reasons that the comparison may be misleading.
- It revises the plan to seek a dated observation or mark that comparison as unresolved.

Likewise, new evidence obtained during work may change the agent's understanding and require a different plan.

This means a sound agentic system must allow conclusions and plans to be revised when relevant information changes. Detailed operational feedback and execution loops will be studied in Discipline 5.

### 5. What reasoning and planning do not guarantee

Neither capability automatically makes an agent reliable.

An agent can:
- Reason from incorrect or incomplete information.
- Make an unjustified assumption.
- Overlook a relevant constraint.
- Form a plan whose steps are impossible.
- Propose an action it is not authorised to take.
- Fail to recognise when it should ask for clarification or stop.

A well-written explanation is not proof that the conclusion is correct. A detailed plan is not proof that the plan is feasible, safe or authorised.

Reasoning and planning must therefore be connected to evidence, problem constraints, the agent's assigned authority and later validation.

### 6. The engineering view

For this discipline, we will examine reasoning and planning as capabilities that can be described, designed and assessed.

We do not need to assume that every agent uses the same reasoning method or that every task requires a long plan. A simple, predictable task may need very little deliberation. A complicated task with uncertain information may need deeper reasoning and a more careful plan.

The appropriate level of reasoning and planning depends on the task, available information, constraints, risk and consequences of error.

No particular model, framework or planning technology is assumed at this stage.

### Principles established

- Reasoning helps interpret information, assess evidence, draw conclusions and identify uncertainty.
- Planning formulates a possible course of action toward an objective.
- Understanding a problem and deciding how to address it are related but different activities.
- A plan is proposed work, not completed execution.
- Reasoning and planning can influence and revise one another as new information becomes available.
- Neither a convincing explanation nor a detailed plan guarantees correctness or success.
- Plans must remain consistent with requirements, constraints and the agent's assigned authority.
- Use the simplest level of reasoning and planning sufficient for the task.
- Treat these as engineered system capabilities; do not assume human consciousness.

## Continuation point

Continue with **1.2 Reasoning vs Planning vs Decision-Making vs Execution**. Subsections 1.2–1.4 remain planned and have not yet been taught.
