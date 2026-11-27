# Chapter 3 — Reasoning Patterns and Inference

**Status:** In progress; subsection 3.1 covered.

## Purpose

Study how conclusions are drawn from premises, how different reasoning patterns work, and how an agent can distinguish what follows logically from what is merely plausible. This chapter begins with deductive reasoning before moving to induction, abduction, causal reasoning and the assessment of evidence.

## Chapter learning sequence

1. **3.1 Deductive Reasoning:** Covered.
2. **3.2 Inductive Reasoning:** Planned.
3. **3.3 Abductive Reasoning and Explanation:** Planned.
4. **3.4 Causal Reasoning, Correlation and Analogy:** Planned.
5. **3.5 Hypotheses, Evidence, Confidence and Limitations:** Planned.

---

## 3.1 Deductive Reasoning

### Core question

When an agent has accepted premises, rules or conditions, how can it determine what must follow from them—and how can it avoid claiming more than those premises support?

**Deductive reasoning** is a form of inference in which a conclusion follows necessarily from a set of premises if the argument's logical form is valid. It moves from stated premises to a conclusion that is already implied by them.

Deduction is especially useful when an agent must apply explicit definitions, rules, permissions, constraints or conditions consistently. It does not, by itself, establish that the premises describe the real world correctly.

### 1. The basic parts of a deductive argument

A deductive argument contains:

- **Premises:** statements taken as the starting points for the argument. They may be facts, definitions, policies, rules or assumptions.
- **Conclusion:** the statement claimed to follow from the premises.
- **Inference:** the logical step connecting the premises to the conclusion.

For example:

1. All records that lack a required observation date must be classified as having an unknown observation date.
2. Record A has no observation date.
3. Therefore, Record A must be classified as having an unknown observation date.

The conclusion follows from the stated rule and the stated information about Record A.

The argument does not prove that the observation never happened, that the price is false or that the source is dishonest. It establishes only the classification supported by those premises.

### 2. Logical validity and soundness

Two important concepts must be separated.

**Validity** concerns the structure of the argument. An argument is logically valid when it is impossible for all its premises to be true while its conclusion is false.

**Soundness** requires both:
1. The argument is logically valid.
2. Its premises are actually true under the relevant definitions and circumstances.

A valid argument can still lead to an untrue conclusion if one or more premises are false.

Consider:

1. All farms in LGA X grow Product Y.
2. Farm Z is in LGA X.
3. Therefore, Farm Z grows Product Y.

The reasoning form is valid. But unless the first premise is actually true, the conclusion is not established. A plausible generalisation must not be treated as a verified rule.

This distinction is central to agent engineering:

- Check whether the inference follows from the premises.
- Separately check where the premises came from, whether they are current, and whether they apply to the case.
- State the conclusion at the same level of certainty the premises support.

### 3. Common deductive patterns

#### A. Categorical reasoning

A categorical argument uses statements about classes or groups.

**Pattern:**

- All A belong to group B.
- Item X belongs to group A.
- Therefore, item X belongs to group B.

Example:

- All entries that meet the project's stated minimum evidence conditions qualify for submission to verification review.
- Entry P meets those minimum conditions.
- Therefore, Entry P qualifies for submission to verification review.

Notice the limited conclusion: it qualifies for review. The reasoning does not say that the entry has already passed review or is approved for public release.

Words such as **all**, **none**, **some** and **only** matter. Do not turn “some producers grow Product Y” into “all producers grow Product Y,” or treat a statement about one product, location or period as a rule for every product, location or period.

#### B. Conditional reasoning: Modus Ponens

A conditional rule has an “if … then …” form.

**Pattern:**

- If P is true, then Q is true.
- P is true.
- Therefore, Q is true.

Example:

- If a report has passed the required review and approval checks, it may be released through the approved publication process.
- Report R has passed those checks.
- Therefore, Report R may enter the approved publication process.

The conclusion is bounded by the rule. It does not authorise publication through a different channel or remove any other applicable restriction.

#### C. Conditional reasoning: Modus Tollens

This pattern reasons from the absence of a required result.

**Pattern:**

- If P is true, then Q must be true.
- Q is not true.
- Therefore, P is not true.

Example:

- If a report is approved for public release under this procedure, it must have a recorded approval decision.
- Report S has no recorded approval decision.
- Therefore, Report S is not approved for public release under this procedure.

This is useful for enforcing mandatory conditions. It depends on the rule being genuinely necessary: the procedure must require a recorded approval decision for every report in the category.

### 4. Two common invalid patterns

An argument can sound reasonable while its conclusion does not logically follow.

#### A. Affirming the consequent

**Invalid pattern:**

- If P, then Q.
- Q is true.
- Therefore, P is true.

Example:

- If an organisation is accepted as a verified producer, its record must contain evidence linking it to a product and production location.
- Organisation A's record contains a product and location link.
- Therefore, Organisation A is a verified producer.

This conclusion does not follow. The link may be necessary for verified status, but it may not be sufficient. Other requirements—such as evidence of the relevant production period, source quality or review approval—may still be missing.

The valid conclusion is only that one stated requirement appears to be present, subject to checking the actual evidence.

#### B. Denying the antecedent

**Invalid pattern:**

- If P, then Q.
- P is not true.
- Therefore, Q is not true.

Example:

- If a producer entry has an official registry source, it has a source reference.
- Entry B does not have an official registry source.
- Therefore, Entry B has no source reference.

This is invalid. Entry B might have a different acceptable source, such as a documented cooperative record or another source permitted by the evidence policy. The original rule did not say that an official registry is the only possible source of a source reference.

The lesson is to preserve the exact direction and scope of a rule. Do not reverse a one-way condition or assume it is an “if and only if” relationship.

### 5. Necessary and sufficient conditions

Deductive reasoning often depends on whether a condition is necessary, sufficient or both.

- A **necessary condition** must be present for a result to qualify. If it is absent, that result cannot qualify under the rule.
- A **sufficient condition** is enough, under the stated rule, to establish the result.
- A condition can be both necessary and sufficient when the rule explicitly defines it that way.

For example, a recorded approval decision may be necessary for public release, but it may not be sufficient on its own. Publication might also require a valid publication channel, current content and an authorised publisher.

Be careful with everyday wording:
- “A verified record must contain a source” makes a source a necessary condition.
- “Any record with this complete set of checks is approved” declares those checks sufficient under the rule.
- “A record is approved if and only if these conditions are met” declares the conditions both necessary and sufficient.

An agent should not silently strengthen a necessary condition into a sufficient one.

### 6. A practical agricultural intelligence example

Suppose the agricultural pilot adopts the following working classification rule:

> A record may be labelled **verified production-location link** only when its evidence explicitly connects a named producer, a specified product, a specific production location and the relevant production period.

Now consider a discovered cooperative entry. The available source names the cooperative, lists a product and gives a village address, but the material inspected does not establish that the cooperative produced that product at that location during a particular period.

The deductive analysis is:

1. **Rule:** If a record is approved as a verified production-location link, it must contain evidence connecting the producer, product, location and relevant period.
2. **Observation about the record:** The currently inspected evidence does not establish the production-period link.
3. **Conclusion:** The record cannot currently be approved as a verified production-location link under this rule.

This conclusion is deliberately narrow. It does **not** establish that the cooperative did not produce the product, that the address is false or that no additional evidence exists. It means the required link has not been demonstrated in the evidence currently available.

The same method can apply to market observations:

- If an observation is classified as a verified transaction, the evidence standard may require evidence of a completed transaction.
- A post that only advertises an asking price does not demonstrate a completed transaction.
- Therefore, that post alone cannot support the verified-transaction classification.

It does not follow that no transaction occurred. It follows only that this source, by itself, does not establish one.

These are examples of possible project rules for learning. They are not yet approved evidence policies for the full agricultural programme; real criteria must be agreed, documented and tested.

### 7. A practical method for using deduction in an agent

When an agent needs to apply a rule, use a traceable sequence:

1. **Identify the question.** What exact classification, decision or conclusion is being considered?
2. **State the premises.** Separate facts observed in the current case from definitions, policies, rules and assumptions.
3. **Check the rule's source and status.** Is it approved, current, applicable to this scope and authoritative for this decision?
4. **Clarify terms and scope.** Check entities, locations, products, periods, units, exceptions and the meaning of words such as “all,” “must,” “only” and “may.”
5. **Choose the inference pattern.** Determine whether the conclusion follows from the premises or whether the reasoning is accidentally reversing a conditional.
6. **Derive a bounded conclusion.** Do not add claims that are not implied by the premises.
7. **Check the premises independently.** A logically valid argument is not sound if its premises are false, stale, unsupported or inapplicable.
8. **Record the reasoning where it matters.** Preserve the rule, relevant evidence, conclusion, unresolved conditions and the applicable rule version.

For a high-impact outcome, the agent should not rely only on a language model's explanation. The actual rule should be explicit and, where possible, checked by a deterministic validation mechanism or an authorised reviewer. The model may help interpret the case or explain a result, but fluent wording is not proof of logical correctness.

### 8. Where deduction is useful in agentic systems

Deduction is particularly valuable when an agent must apply stable, explicit requirements, such as:

- Checking mandatory fields in a record.
- Enforcing permission and approval conditions.
- Applying an agreed classification definition.
- Determining whether prerequisites for a workflow step are satisfied.
- Checking whether an action is prohibited by an explicit rule.
- Explaining why a candidate record does not yet meet a stated acceptance condition.

It is less suitable for discovering a new pattern from observations, guessing the most likely explanation for an event or predicting an uncertain market outcome. Those tasks require other forms of reasoning, which the next subsections will examine.

### 9. Common failure modes and safeguards

| Failure mode | What goes wrong | Safeguard |
|---|---|---|
| False premise | The conclusion may be validly derived from an inaccurate rule or fact. | Verify the premise, its source, scope and date. |
| Invalid inference | The conclusion does not follow from the stated premises. | Check the logical form; watch for affirming the consequent and denying the antecedent. |
| Reversed condition | A one-way “if” rule is treated as an “if and only if” rule. | Identify whether conditions are necessary, sufficient or both. |
| Overgeneralisation | A rule for one product, location, time or class is applied too broadly. | Preserve qualifiers, exceptions and scope. |
| Hidden premise | An unstated assumption is used to reach the conclusion. | Make material assumptions explicit and test them. |
| Evidence-to-reality leap | A record's lack of evidence is treated as proof that an event did not happen. | Distinguish “not established by current evidence” from “did not occur.” |
| Stale rule | A formerly valid policy or definition is applied after it has changed. | Check the current approved version and effective date. |

### 10. Key principles

- Deduction derives conclusions that must follow if the premises are true and the argument is valid.
- Logical validity does not establish that the premises themselves are true.
- A sound argument is valid and has true premises.
- Rules must be applied within their actual scope and with their exceptions.
- Necessary conditions must not be mistaken for sufficient conditions.
- A missing record or missing evidence does not automatically prove that the underlying event did not happen.
- The conclusion must not claim more than the premises establish.
- Explicit rules can support repeatable validation, but the origin and current validity of those rules still matter.
- A plan, policy or conclusion does not create authority beyond the system's assigned permissions.

## Lesson checkpoint

Consider this rule:

> Every entry approved as a verified production-location link must contain evidence connecting the producer, product, location and relevant production period.

An entry names a producer, product and village, but the available evidence does not connect the producer to production at that village during a relevant period.

A careful conclusion is:

**The entry does not currently meet the stated requirement for approval as a verified production-location link.**

It would be incorrect to conclude that the producer never produced the product, that the village information is false or that no other evidence exists. Those claims are not established by the premises.

The checkpoint demonstrates the central discipline of deduction: derive what follows, and stop where the premises stop.

---

## 3.2 Inductive Reasoning

### Core question

When an agent observes individual cases, examples or repeated patterns, how can it form a broader conclusion without pretending that the observations prove more than they actually do?

**Inductive reasoning** moves from particular observations to a broader pattern, generalisation or prediction. It can make a conclusion more plausible or better supported, but the conclusion does not follow with logical necessity from the observations.

For example:
- A market observation shows that the wholesale price of a particular grade of tomatoes increased this week.
- Comparable observations from several other markets show increases over the same period.
- The agent concludes that there may be a broader upward movement in the observed markets.

This is inductive reasoning. The observations support the conclusion, but do not guarantee that prices increased in every market, for every grade or in every transaction.

### 1. How induction differs from deduction

| Feature | Deductive reasoning | Inductive reasoning |
|---|---|---|
| Direction | Applies premises or rules to derive a conclusion. | Uses particular observations to infer a wider pattern or likely result. |
| Conclusion | Must follow if the argument is valid and its premises are true. | Is supported to some degree, but may still be false. |
| Main question | What must follow from these premises? | What pattern or likely conclusion is supported by these observations? |
| Main risk | Invalid logic or false premises. | Unrepresentative, incomplete, biased or misleading observations. |
| Example | If every approved record must contain a source, a record without a source is not approved under that rule. | If comparable observations across several markets show increasing prices, prices may be rising across the sampled markets. |

A deductive conclusion can be certain relative to true premises and a valid inference. An inductive conclusion is provisional: additional observations may strengthen it, weaken it or overturn it.

### 2. Generalisation from observed cases

One common form of induction is **generalisation**: observing a number of individual cases and using them to form a conclusion about a larger group.

Suppose an agricultural intelligence process observes that several sampled tomato traders in Market A are quoting higher prices than in the previous observation period. After checking product form, grade, unit and market level, the agent infers that quotations in the sampled part of Market A may be increasing.

The conclusion must retain the limits of the sample. It does not automatically establish that every trader in the market is quoting more, every tomato grade has increased, or farmgate, wholesale and retail prices have all moved in the same direction. It certainly does not establish a statewide or national trend.

The conclusion should be no broader than the observations and the method justify.

### 3. Statistical induction and samples

An agent often cannot inspect every member of a population. It uses a sample and considers what that sample may indicate about the wider group.

The strength of the resulting inference depends on the quality of the sample and how it was collected.

Important questions include:

- **Coverage:** Which locations, market levels, product forms and time periods are represented?
- **Selection:** Why were these observations included? Were some types of cases systematically excluded?
- **Representativeness:** Does the sample resemble the wider group about which the agent wants to make a claim?
- **Sample size:** Are there enough observations for the intended conclusion? A larger sample can help, but size alone does not remove bias.
- **Comparability:** Are observations measuring the same product, unit, quality, market level and time period?
- **Independence:** Are sources genuinely independent, or are multiple posts repeating one original report?
- **Missingness:** Which locations or observation types are absent, and could their absence distort the picture?

A large but biased sample may produce a misleading generalisation. A smaller, carefully selected sample can sometimes be more informative for a narrowly defined question.

### 4. Patterns and predictions

Induction can help identify recurring patterns and form cautious expectations about future events.

For example, an agent observes repeated increases in comparable wholesale quotations over several reporting periods. It may infer that the upward pattern could continue in the near term. However, past patterns do not guarantee future results. Market conditions can change, observations may be delayed and a pattern may be temporary.

Distinguish:
- A pattern observed in historical data.
- A generalisation about a wider group.
- A prediction about what may happen next.

These are related but not interchangeable. Predictions require care about time horizon, data quality and changing conditions.

### 5. Repetition is not necessarily independent evidence

An agent may encounter many reports that appear to confirm one another. Repeated statements do not necessarily provide independent evidence.

Imagine six social media accounts repeating the same market-price claim. If all six copied one original post, they may represent one underlying report rather than six independent observations.

Similarly, several websites may reproduce the same dataset, a summary may repeat an old report, or different sources may describe different product grades using the same general name.

An agent should preserve source provenance and investigate whether evidence is independent before treating repetition as corroboration.

### 6. Bias and misleading patterns

| Risk | What happens | Example safeguard |
|---|---|---|
| Selection bias | Collected cases do not fairly represent the group. | Record how observations were selected and identify missing locations or groups. |
| Small sample | Too few observations support a broad conclusion. | Narrow the claim or gather more observations. |
| Survivorship bias | Only visible or successful cases are considered. | Look for missing, failed or unreported cases where relevant. |
| Duplicate evidence | Copies of one claim look like multiple confirmations. | Trace reports to their original sources. |
| Measurement inconsistency | Different units, grades or market levels are combined. | Preserve and compare only compatible observations. |
| Time mismatch | Different periods are treated as simultaneous. | Retain observation dates and compare appropriate time windows. |
| Overgeneralisation | A local pattern is presented as universal. | State the actual geographic, product and temporal scope. |
| Confirmation bias | Attention is given mainly to supporting evidence. | Search for disconfirming observations too. |

An absence of online reports is not proof that no activity occurred. It may simply reflect gaps in source coverage.

### 7. Agricultural price example

Suppose the pilot collects comparable wholesale price quotations for a specified form and grade of tomatoes from four markets during two observation periods. In the later period, three of the four sampled markets show higher quotations.

A careful inductive conclusion is:

> Three of the four sampled markets show higher comparable wholesale quotations in the later observation period. This provides some evidence of an upward movement within the sampled markets, but it is not enough by itself to establish a statewide price increase.

Before strengthening that conclusion, the agent should check whether:
- The quotations refer to the same product form and grade.
- Units are comparable.
- Both periods are correctly dated.
- The observations are asking prices or completed transactions.
- Markets and sources were selected in a way that creates bias.
- Further observations support or contradict the pattern.

This is an illustrative example, not a claim about actual current tomato prices.

### 8. The four agricultural evidence levels

The pilot has a working evidence vocabulary:

1. **Verified transactions:** evidence supports that a transaction was completed.
2. **Verified quotations:** evidence supports that a price was quoted, without treating it as a completed transaction.
3. **Unverified information:** a claim has been encountered but has not met the required verification standard.
4. **Market signals:** indirect indications that may point to a development worth investigating.

These categories describe evidence status or type. They do not automatically make a sample representative.

Ten verified transactions from one market may be strong evidence about those transactions, but they do not necessarily establish prices in all markets. Several unverified reports may point to a useful signal, but should not be presented as confirmed facts.

Evidence status must therefore be considered separately from sample coverage, source reliability, freshness and comparability.

### 9. A practical method for using induction in an agent

1. **Define the question and target group.** Specify the product, entity, geography, market level and period.
2. **Identify the observations.** Keep original sources, observation dates, collection dates and relevant details.
3. **Check provenance.** Identify copied reports, common origins, unknown sources and conflicting evidence.
4. **Check comparability.** Do not combine unlike products, grades, units, market levels or periods without a justified method.
5. **Check sample coverage and bias.** Identify which cases are present, absent or systematically easier to observe.
6. **Look for supporting and disconfirming observations.** Do not search only for information that confirms the expected pattern.
7. **Form a bounded conclusion.** State exactly which observations support the pattern and which wider claims remain uncertain.
8. **Express confidence proportionately.** Do not invent precise confidence percentages when the data and method do not justify them.
9. **Identify the next useful evidence.** Determine what observations could strengthen, weaken or test the conclusion.
10. **Revise when new evidence arrives.** Inductive conclusions remain open to correction.

### 10. Where induction is useful in agentic systems

Induction is useful when an agent needs to:
- Identify recurring patterns in collected information.
- Detect possible changes in markets or operating conditions.
- Infer likely characteristics of a wider group from a sample.
- Prioritise locations or subjects for further investigation.
- Form cautious expectations from historical observations.
- Identify unusual observations that deserve additional verification.

Induction must not bypass mandatory rules or evidence requirements. A likely pattern does not give an agent permission to publish an unverified claim or take an otherwise prohibited action.

An inductive pattern also does not by itself establish causation. Causal reasoning will be examined in subsection 3.4.

### 11. Key principles

- Induction moves from particular observations to broader patterns, generalisations or predictions.
- Inductive conclusions are supported by evidence but are not logically guaranteed by it.
- Strength depends on source quality, sample coverage, representativeness, comparability and independence.
- A larger sample does not automatically remove selection bias or duplicated evidence.
- A pattern in one location or period does not automatically apply elsewhere or later.
- Evidence status and sample representativeness are separate questions.
- Search for disconfirming information as well as confirming information.
- State what was observed, what is inferred and what remains unresolved.
- Treat inductive conclusions as revisable when new evidence arrives.

## Lesson checkpoint

Suppose an agent finds higher wholesale quotations for the same product form and grade in three of four sampled markets during a later observation period.

A careful conclusion is:

**The sampled observations suggest an upward movement in the three markets where higher comparable quotations were recorded. The available sample does not by itself establish a statewide increase or explain why the quotations changed.**

The agent should preserve the scope of the sample, investigate its representativeness, check source independence and seek additional observations before making a broader claim.

This is the central discipline of induction: use observed patterns to form useful conclusions, but keep those conclusions proportional to the evidence.

## Chapter 3 progress

Subsections 3.1, Deductive Reasoning, and 3.2, Inductive Reasoning, are covered. Next: **3.3 Abductive Reasoning and Explanation**.
