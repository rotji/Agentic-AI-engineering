# Chapter 1 — Foundations of Reasoning and Planning

**Status:** In progress.

## Purpose

Establish what reasoning and planning mean in an agentic system, how they contribute to goal-directed behaviour, and why a system needs to distinguish forming an understanding from deciding how to proceed.

## Chapter learning sequence

1. **1.1 What Reasoning and Planning Mean in Agentic Systems:** Covered.
2. **1.2 Reasoning vs Planning vs Decision-Making vs Execution:** Covered.
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

## 1.2 Reasoning vs Planning vs Decision-Making vs Execution

### Core question

When an agent receives an objective and begins working, four activities are involved: understanding the situation, organising a course of action, selecting what to do and carrying out the selected action. How are these activities different, and how do they work together?

The four concepts are:

- **Reasoning:** interpreting information and assessing what follows from it.
- **Planning:** formulating a possible course of action to reach an objective.
- **Decision-making:** choosing among available options or determining what should happen next.
- **Execution:** carrying out an authorised action in the environment.

They are closely connected, but they are not interchangeable. Treating them as if they mean the same thing makes it harder to design, evaluate and control an agentic system.

### 1. Reasoning — understand and assess

Reasoning helps the agent work out what the available information means and what conclusions are supported.

It may involve:
- Interpreting instructions and observations.
- Identifying relevant facts.
- Comparing evidence.
- Recognising contradictions or missing information.
- Forming possible explanations.
- Assessing assumptions and uncertainty.
- Working out implications of different conditions.

**Main question:** What do we know, what can we reasonably conclude, and what remains uncertain?

Example: A market report shows a higher tomato price than an earlier record. The agent reasons that the observations may not be directly comparable because the dates or basket sizes may differ. It should not conclude that a general price increase has been established until those issues are examined.

Reasoning produces an interpretation, an assessment or a set of possible conclusions. It does not itself carry out an external action.

### 2. Planning — organise a possible course of action

Planning develops a structured approach for reaching an objective.

A plan may specify:
- The intended outcome.
- Tasks or actions that may be needed.
- The order and dependencies among those tasks.
- Required information and resources.
- Preconditions and constraints.
- Alternative paths if a condition changes.
- Expected results and completion conditions.

**Main question:** What steps could achieve the objective, and how should they be organised?

Example: The agent proposes to validate the tomato observation, locate comparable records, compare relevant markets, investigate plausible explanations and prepare an evidence-based report.

Planning produces a proposed course of action. It does not prove that every step is feasible, permitted or already completed.

### 3. Decision-making — select among options

Decision-making is the process of choosing an option, action or course of action from the alternatives available.

It may take account of:
- The objective and priorities.
- Available evidence and uncertainty.
- Constraints and permissions.
- Expected benefit.
- Cost, time and resource use.
- Risk and possible consequences.
- Whether to proceed, defer, ask, escalate or take no action.

**Main question:** Given the available options and constraints, which option should be selected now?

Example: The agent discovers that the tomato report has no observation date. It could:
- Request a dated observation from the source.
- Search for another approved source.
- Mark the comparison as unresolved.
- Stop the investigation if there is no permitted way to obtain sufficient evidence.

Choosing one of these options is a decision. The reasoning process helps assess the evidence and implications; the plan provides possible routes; decision-making selects which route or next action is appropriate.

Decision-making can occur before a plan is finalised and throughout the work. A plan may also contain conditional decision points, such as "if the source is unavailable, use an approved alternative; otherwise continue." Planning describes the structure of those branches; a decision at runtime selects the branch that applies.

### 4. Execution — carry out the selected action

Execution is the performance of an action in the system or its environment.

It may include:
- Requesting information from an approved source.
- Reading or writing an authorised record.
- Running a calculation.
- Sending an approved notification.
- Creating a report.
- Invoking an authorised tool or service.

**Main question:** What action is actually being carried out?

Example: After deciding to seek a dated observation, the system actually sends the permitted request to the approved source or invokes the authorised collection process.

Execution changes the state of the system or its environment, or attempts to do so. A proposed action is not an executed action. An execution attempt is also not proof of success; the system may need to observe and verify the result. Detailed execution cycles and runtime feedback belong to Discipline 5.

### 5. Compare the four activities

| Activity | Primary purpose | Main question | Typical output |
|---|---|---|---|
| Reasoning | Understand and assess | What do we know and what follows? | Interpretation, conclusion, hypothesis or identified uncertainty |
| Planning | Organise a route to the goal | What steps could achieve it? | Proposed sequence, dependencies and alternatives |
| Decision-making | Select an option | Which option should be chosen now? | Selected action, plan, deferral, escalation or no-action choice |
| Execution | Perform the selected action | What is actually being done? | Action attempt and resulting state or outcome |

A simple memory aid:

- Reasoning: **understand**.
- Planning: **organise**.
- Decision-making: **choose**.
- Execution: **do**.

The memory aid is useful, but real agentic systems may interleave these activities rather than perform them in one fixed sequence.

### 6. A complete worked example

Suppose the Agricultural Intelligence System receives an unusual tomato-price observation.

**Stage A — Reasoning**

The agent examines the observation, checks the source details it has, identifies missing date information and concludes that the apparent increase is not yet established.

Output: an evidence assessment and a description of what remains uncertain.

**Stage B — Planning**

The agent formulates possible investigation steps: obtain a dated observation, seek an independent comparable source, compare the same unit and market, then prepare a report if the evidence is sufficient.

Output: a proposed investigation plan with dependencies and a completion condition.

**Stage C — Decision-making**

The agent considers the available next options. It selects an approved alternative source because the original source has not supplied a date and the alternative is within its permitted scope.

Output: the selected next action and the reason for selecting it.

**Stage D — Execution**

The system carries out the authorised request to the alternative source. The request is actually sent; the agent does not yet assume a response has arrived.

Output: an execution record showing that the request was attempted, together with the result when it becomes available.

If the alternative source returns a usable observation, the agent may reason about the new evidence, revise the plan, select another action and execute it. If no usable source is available, it may decide to mark the matter unresolved or escalate it.

This demonstrates that the activities can form a repeating, connected process.

### 7. Why the distinctions matter in engineering

Confusing the four activities can create practical design problems.

- If a plan is mistaken for execution, a system may report that work is complete when it has only proposed the steps.
- If reasoning is mistaken for verification, an unsupported conclusion may be treated as an established fact.
- If decision-making is hidden inside a broad planning description, it may be unclear who or what selected a consequential action and why.
- If execution is not distinguished from a successful outcome, a tool call or request may be reported as successful even when it failed.
- If planning is treated as permission, an agent may attempt an action that is outside its authority.

Clear distinctions make it easier to record what the agent understood, what it proposed, what it selected, what it attempted and what actually happened.

### 8. They are connected, not necessarily separate modules

These are conceptual functions. They do not have to be implemented as four separate software components or four separate AI agents.

A single agent may reason, plan and make decisions within one operating process, while an execution environment performs or mediates the actual actions. In another architecture, some of these functions may be split across components.

The distinction is about the kind of work being performed, not a mandatory software structure.

The activities also influence one another:
- Reasoning may reveal that more information is needed before planning.
- Planning may expose missing prerequisites and trigger further reasoning.
- Decision-making may select a plan, revise it or choose not to proceed.
- Execution may produce results that require new reasoning and replanning.

A useful conceptual cycle is:

**Understand → Organise → Choose → Act → Examine the result**

The final examination may begin another round of reasoning and planning. The detailed runtime loop will be developed in Discipline 5.

### 9. Important distinctions to preserve

- A conclusion is not the same as a selected action.
- A plan is not the same as a decision to execute every step.
- Selecting an action is not the same as carrying it out.
- Attempting an action is not the same as confirming its success.
- A plan may contain future decision points without making those decisions in advance.
- An agent's ability to plan or decide does not grant it authority to act.
- A person or external policy may reserve certain decisions or approvals.

### Principles established

- Reasoning interprets information and assesses conclusions.
- Planning organises a possible course of action toward an objective.
- Decision-making selects among available options under goals, evidence, constraints, priorities and risk.
- Execution carries out an authorised action and produces an attempt or outcome that may need verification.
- The four activities are connected and may interleave; they are not necessarily four separate modules or a rigid one-way sequence.
- Record the difference between what an agent concluded, planned, selected, attempted and confirmed.
- A plan does not grant authority, and an action attempt does not prove success.
- New information or execution results may trigger further reasoning, decisions and plan revision.


Continue with **1.3 How Reasoning and Planning Fit into an Agent's Operation**. Subsections 1.3–1.4 remain planned and have not yet been taught.
