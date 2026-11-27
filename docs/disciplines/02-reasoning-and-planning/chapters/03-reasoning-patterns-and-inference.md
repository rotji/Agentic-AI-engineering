# Chapter 3 — Reasoning Patterns and Inference

**Status:** Complete; subsections 3.1–3.5 covered.

## Purpose

Study how conclusions are drawn from premises, how different reasoning patterns work, and how an agent can distinguish what follows logically from what is merely plausible. This chapter begins with deductive reasoning before moving to induction, abduction, causal reasoning and the assessment of evidence.

## Chapter learning sequence

1. **3.1 Deductive Reasoning:** Covered.
2. **3.2 Inductive Reasoning:** Covered.
3. **3.3 Abductive Reasoning and Explanation:** Covered.
4. **3.4 Causal Reasoning, Correlation and Analogy:** Covered.
5. **3.5 Hypotheses, Evidence, Confidence and Limitations:** Covered.

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

## 3.3 Abductive Reasoning and Explanation

### Core question

When an agent observes something that needs explaining, how can it identify plausible explanations, compare them and decide what evidence to seek next—without mistaking a convincing explanation for a proven fact?

**Abductive reasoning** is inference from an observation or set of observations to a hypothesis that could explain them. It is often described as *inference to the best explanation*.

Abduction is useful when the agent knows that something has happened but does not yet know why. It helps generate and compare possible explanations. It does not prove that the selected explanation is true.

For example, an agricultural intelligence system notices that a tomato quotation is much higher than comparable recent observations. Possible explanations include a supply disruption, higher transport costs, a change in product grade or unit, a demand increase, or an error in the source record. The agent can use abduction to identify which explanations deserve investigation.

### 1. How abduction differs from deduction and induction

The three forms of inference answer different questions:

| Reasoning form | Starts with | Main question | Typical conclusion |
|---|---|---|---|
| **Deduction** | Premises and rules | What must follow if these premises are true? | A conclusion that follows necessarily from valid premises. |
| **Induction** | Individual observations or examples | What wider pattern or likely result do these observations support? | A provisional generalisation or prediction. |
| **Abduction** | An observation or problem to explain | What hypothesis could best explain what we observe? | A candidate explanation that needs further assessment. |

They can work together during one investigation.

For example:
- **Induction:** Several comparable markets show higher quotations over the observed period; a wider upward pattern may exist within the sample.
- **Abduction:** A supply disruption could be one explanation for the observed increases.
- **Deduction:** If the supply-disruption hypothesis is correct in a particular location, and a reliable source reports reduced arrivals there, then the combined premises may support a specific conclusion about that location.

The forms of reasoning are not mutually exclusive stages that must always occur in a fixed order. New evidence may cause an agent to return to an earlier inference.

### 2. The basic abductive pattern

A simple abductive argument can be represented as:

1. An observation or set of facts is present.
2. If a particular hypothesis were true, those observations would be understandable or expected.
3. Therefore, the hypothesis is a possible explanation worth considering.

Example:

- **Observation:** A market's reported tomato quotation is substantially higher than a recent comparable observation.
- **Candidate hypothesis:** The volume of tomatoes arriving at that market has decreased.
- **Reason for considering it:** A reduction in supply could be consistent with higher quotations, other things being equal.
- **Abductive conclusion:** A supply reduction is one possible explanation to investigate.

This is not a deductively valid proof of the hypothesis. Higher quotations might occur for several other reasons. The observation may also be incorrect or not genuinely comparable with the earlier value.

The logical shape can resemble the invalid deductive pattern called *affirming the consequent*:

- If H, then E.
- E is observed.
- Therefore H.

That conclusion does not follow as a deduction. Abduction uses the observation to propose H as a possible explanation, not to prove H. The distinction must remain explicit.

### 3. Generate alternative explanations

A common failure is to settle on the first explanation that sounds plausible. A reliable agent should consider reasonable alternatives, including explanations that challenge its initial interpretation.

Suppose a tomato quotation appears unusually high. Possible hypotheses include:

| Candidate hypothesis | What could make it plausible? | What else should be checked? |
|---|---|---|
| **H1 — Reduced supply or market arrivals** | Fewer comparable products may be reaching the market. | Arrival volumes, trader stock, producer or aggregator reports, and observations from relevant source locations. |
| **H2 — Higher transport or handling costs** | Delivered costs may have increased. | Route-specific transport quotations, fuel and handling information, and whether the price is farmgate or delivered wholesale. |
| **H3 — Different grade, quality or package** | The new quotation may refer to larger, better-quality or differently packaged produce. | Product description, grade, size, packaging and original unit. |
| **H4 — Higher demand** | More buyers or a temporary demand event may be affecting the market. | Buyer activity, quantities traded, orders or other independently sourced demand signals. |
| **H5 — Observation or recording problem** | The source may be stale, duplicated, incorrectly transcribed or not comparable. | Original source, date, unit, calculation, duplicate checks and direct confirmation where authorised. |

The list is not exhaustive. The point is to avoid turning the first plausible story into the answer.

An agent should also consider whether more than one explanation may contribute. For example, higher transport costs and a smaller volume of arrivals could occur together.

### 4. What makes one explanation better than another?

The "best explanation" is not simply the most interesting, familiar or detailed story. It is the hypothesis that is best supported relative to the alternatives and the evidence available.

Useful considerations include:

- **Fit with observations:** Does the hypothesis account for the important observations, rather than just one convenient detail?
- **Independent support:** Is there evidence from sources that are genuinely independent, or are they repeating the same claim?
- **Consistency:** Does the hypothesis fit established facts and relevant background knowledge without contradicting stronger evidence?
- **Discriminating predictions:** Does it imply something observable that would help distinguish it from competing explanations?
- **Testability:** Can the proposed explanation be investigated with accessible, permitted evidence?
- **Scope:** Does it explain only the case under consideration, or is the agent improperly extending it to other locations, products or periods?
- **Assumptions:** How many unsupported assumptions does it require?
- **Consequences of error:** What harm could follow if the explanation is wrong, and how much verification is needed before acting on it?

Simplicity can be useful when comparing explanations, but the simplest explanation is not automatically correct. A complicated explanation may be justified by strong evidence; a simple one may fail to account for important facts.

The agent should avoid assigning numerical probabilities or confidence scores unless it has a defensible method and suitable data. A ranked list such as "more supported", "less supported" and "unresolved" may be more honest than invented percentages.

### 5. Seek evidence that distinguishes between explanations

Evidence is especially useful when it helps distinguish competing hypotheses, rather than merely being consistent with all of them.

For example:

- A report that fuel prices increased may be consistent with the transport-cost hypothesis, but does not establish that transport costs on the relevant route increased or that they explain the tomato quotation.
- Evidence that arrivals at the specific market fell during the relevant period would be more directly relevant to the supply hypothesis.
- Discovering that the new quotation is for a different grade or package may show that the apparent price jump was a comparability problem rather than a market change.
- Finding that several accounts copied one original post would weaken the appearance of independent confirmation.

The agent should ask: **What evidence would I expect to find if this hypothesis were true, and what evidence would make me reconsider it?**

This question reduces confirmation bias and turns explanation into an investigation plan.

### 6. A practical abductive investigation

Assume the pilot receives an unusually high tomato price observation.

A careful investigation might proceed as follows:

1. **Describe the observation without explaining it.** Record the source, value, currency, unit, product form, market, market level and observation date.
2. **Check whether the observation is genuine and comparable.** Review the original source, unit, grade, package, date and possible duplication.
3. **Generate plausible explanations.** Consider supply, transport, demand, product quality, market conditions and recording error where relevant.
4. **Identify expected evidence for each explanation.** State what should be observable if each hypothesis were true.
5. **Choose discriminating checks.** Prefer checks that can distinguish hypotheses rather than simply collect more of the same claim.
6. **Gather evidence within permitted access and authority.** Do not contact external parties, access restricted information or spend money without the required permission.
7. **Compare the evidence with the alternatives.** Record which hypotheses are supported, weakened or unresolved.
8. **Update the explanation.** Retain more than one hypothesis if the evidence does not distinguish them.
9. **Report the conclusion carefully.** Separate the original observation, candidate explanations, evidence found, unresolved questions and any recommended next investigation.
10. **Do not claim causation prematurely.** Abduction helps formulate explanatory hypotheses; stronger causal analysis requires additional methods, which are introduced in subsection 3.4.

### 7. Abduction in practical agent engineering

Abductive reasoning can support:
- Diagnosing why a workflow or tool call failed.
- Investigating unusual data and anomalies.
- Explaining conflicting observations.
- Identifying possible reasons for a market or operational change.
- Generating hypotheses for further research.
- Prioritising which evidence to collect next.
- Helping a human reviewer understand alternative interpretations.

For an agentic system, a useful output is not merely "the reason is X". It can be a structured explanation record:

| Field | Example content |
|---|---|
| Observation | A quotation is higher than the previous comparable observation. |
| Hypothesis | Supply arriving at the market may have decreased. |
| Supporting evidence | Evidence that arrivals declined, if independently observed. |
| Contradicting evidence | Evidence that arrivals remained stable or increased. |
| Alternative explanations | Different grade, transport costs, demand or recording error. |
| Missing evidence | No reliable arrival-volume record for the observation period. |
| Current assessment | Possible explanation; not established. |
| Next test | Seek comparable arrival information from an authorised source. |

This format is a proposed learning aid, not a prescribed universal schema. The information captured should be proportionate to the importance and consequences of the investigation.

### 8. Common abductive reasoning failures

| Failure | What happens | Safeguard |
|---|---|---|
| First-story bias | The first plausible explanation is accepted too quickly. | Generate and compare alternatives. |
| Confirmation bias | Only evidence supporting the preferred hypothesis is sought. | Identify disconfirming evidence and tests before deciding. |
| Post hoc explanation | An event occurring before another is treated as its explanation. | Do not infer causation from sequence alone. |
| Single-cause assumption | Several contributing factors are ignored. | Consider combined explanations where appropriate. |
| Circular explanation | A hypothesis merely restates the observation. | Require an independent mechanism or prediction that can be checked. |
| Overfitting | A detailed story explains one observation but does not generalise or survive further checks. | Prefer explanations that account for relevant evidence without invented detail. |
| False certainty | A plausible hypothesis is reported as a confirmed fact. | Label hypotheses and confidence limits explicitly. |
| Evidence neglect | The agent ignores an observation that contradicts the preferred explanation. | Preserve conflicting evidence and revise the assessment. |

### 9. Key principles

- Abduction proposes hypotheses that could explain observed facts.
- A plausible explanation is not a proven explanation.
- Several hypotheses may explain the same observation.
- Compare alternatives rather than accepting the first plausible story.
- Seek evidence that distinguishes between hypotheses.
- Look for both supporting and contradicting evidence.
- Distinguish the observation from the interpretation placed on it.
- Keep the scope of an explanation aligned with the evidence.
- More than one factor may contribute to an observed result.
- Report unresolved explanations honestly and revise them when new evidence arrives.
- Abductive reasoning can guide an investigation, but it does not by itself prove causation or authorise consequential action.

## Lesson checkpoint

An agricultural intelligence process observes that one market's tomato quotation is unusually high compared with a recent observation.

It proposes three possible explanations:
1. Fewer tomatoes may be arriving at the market.
2. The quotation may refer to a different grade or package.
3. The source may have copied an old or incorrect value.

The responsible next step is not to announce a shortage. It is to check product comparability, inspect the original source and seek evidence about market arrivals. If the available evidence cannot distinguish the explanations, the conclusion must remain unresolved.

This is the central discipline of abduction: use observations to generate the best explanations worth testing, while remembering that an explanation remains a hypothesis until adequate evidence supports it.

## 3.4 Causal Reasoning, Correlation and Analogy

### Core question

When two things appear to change together, how can an agent decide whether one may influence the other, what else could explain the relationship, and whether a principle or solution from one situation can reasonably transfer to another?

This subsection covers three related but distinct ideas:

- **Correlation or association:** two variables or events vary together in some observed way.
- **Causal reasoning:** examining whether a change in one factor produces or contributes to a change in another, and what evidence supports that claim.
- **Analogical reasoning:** using relevant similarities between two situations to suggest that an explanation, method or design pattern from one may be useful in the other.

Each helps an agent investigate and reason, but each can also mislead when used carelessly.

### 1. Correlation does not establish causation

A **correlation** is an observed association or pattern of co-variation between variables. For example, two measurements may tend to increase together, one may increase while the other decreases, or no clear relationship may appear.

A correlation can be useful: it can identify a pattern worth investigating. But it does not, by itself, tell us why the pattern exists.

Suppose tomato prices and transport fuel prices both increase during a particular period. The observations show that the two variables moved together. They do not, on their own, prove that the rise in fuel prices caused the tomato-price increase.

Other possibilities include:
- The price of tomatoes and fuel were both affected by a wider economic or seasonal development.
- Tomato supply decreased for a separate reason.
- Demand increased.
- The observations refer to different market levels, grades, units or periods.
- One or both measurements are inaccurate or not comparable.

The safe conclusion is that the two observed series moved together in the sample. A causal explanation requires additional investigation.

### 2. Three important causal traps

#### A. A common cause or confounding factor

A **confounder** is a factor that influences, or is associated with, both the proposed cause and the outcome, making their relationship difficult to interpret.

Illustrative structure:

```
              Shared factor C
                /       \
               v         v
          Factor A ---> Outcome B
```

For example, a seasonal disruption might affect both fuel logistics and the volume of tomatoes reaching a market. Fuel prices and tomato prices may then rise together, even if the observed relationship is partly or mainly explained by the shared disruption.

If the agent does not consider the common factor, it may attribute too much influence to A.

#### B. Reverse causality

The proposed direction may be wrong, or influence may operate in both directions.

For example, higher demand for transport services could affect transport prices, while higher transport costs could also affect the delivered prices of agricultural products. Observing that two values move together does not establish which direction of influence is operating.

#### C. Coincidence, selection effects or a shared time trend

Two unrelated variables can move together by chance, or because both follow a wider time pattern. A relationship may also appear because the agent selected only certain locations, periods or successful cases.

A correlation found in a small or selectively collected sample may disappear when broader evidence is examined.

These traps show why a chart, pattern or statistical correlation is a starting point for investigation—not a causal conclusion.

### 3. What makes a causal explanation more credible?

Causal reasoning examines more than whether two variables move together. It asks whether the proposed cause could plausibly produce the outcome and whether the evidence is consistent with that mechanism.

Useful questions include:

1. **Temporal order:** Did the proposed cause occur before the outcome it is supposed to influence? This is generally necessary for a direct cause, but it is not sufficient proof.
2. **Mechanism:** Is there a credible process through which the cause could affect the outcome?
3. **Alternative explanations:** Could another factor, including a common cause, explain the observed relationship?
4. **Consistency:** Does the relationship appear in other relevant settings or periods, or is it confined to one unusual sample?
5. **Dose or exposure pattern:** Where relevant, does a larger exposure to the proposed cause correspond to a stronger or different outcome in a way consistent with the proposed mechanism?
6. **Counterfactual comparison:** What would likely have happened to the outcome under comparable conditions if the proposed cause had not occurred?
7. **Disconfirming evidence:** What observations would weaken or contradict the causal explanation?

No single question automatically proves causality. The appropriate evidence depends on the domain, available data, assumptions and consequences of being wrong.

### 4. Counterfactual thinking and comparison

A **counterfactual** asks what would have happened under an alternative condition.

For example:

- Observed situation: transport costs increased on a particular supply route and delivered tomato prices later increased.
- Counterfactual question: what would the tomato price have been over the same period if transport costs on that route had not increased, with other relevant conditions held comparable?

We cannot directly observe both outcomes for the exact same market, product and time under both conditions. The counterfactual must be estimated using a suitable comparison or research design.

Possible approaches include:

- Comparing similar markets with different exposure to the transport-cost change.
- Comparing periods before and after a change while checking for other developments occurring at the same time.
- Using a comparison group or location that was not exposed to the same change.
- Examining a natural or policy-driven event that creates a meaningful difference in exposure.
- Conducting a controlled experiment where it is ethical, lawful and feasible.

A simple before-and-after comparison is not automatically causal. Other changes may have occurred between the two periods. Likewise, two locations are not valid comparison groups merely because they are nearby; their products, supply routes, demand, seasonality and other relevant conditions may differ.

Randomised controlled experiments can provide strong causal evidence in suitable contexts, but many market and social questions cannot be randomly assigned. Observational studies can still provide useful causal evidence when their assumptions and limitations are carefully examined.

### 5. A practical agricultural example

Suppose the pilot observes:
- Higher tomato quotations in a market.
- Higher transport fuel prices over a similar period.
- Reports that fewer tomato loads arrived at the market.

The agent should not immediately say that fuel prices caused tomato prices to rise.

It should separate the evidence:

| Item | What is currently observed or proposed |
|---|---|
| Tomato quotations | Increased in the sampled observations, subject to comparability checks. |
| Fuel prices | Increased over a similar period, subject to source and location checks. |
| Market arrivals | Some reports suggest a reduction; the quantity and evidence quality need verification. |
| Proposed explanation | Higher transport costs may have contributed to delivered prices. |
| Other explanations | Reduced production, road disruption, seasonality, demand, grade differences or inaccurate observations. |
| What is missing | Route-specific transport costs, arrival volumes, comparable market observations and evidence about timing. |

A stronger investigation would determine whether transport costs actually rose on the relevant supply routes, whether they materially affected the delivered cost of tomatoes, and whether competing factors could explain the price movement.

Even if transport costs contributed, they may not be the only cause. A careful report may conclude that transport costs are a plausible contributing factor supported by specified evidence, while other causes remain unresolved.

### 6. Analogy: reasoning from relevant similarities

**Analogical reasoning** compares two situations that share relevant features and uses those similarities to suggest a possible conclusion, explanation or design approach.

An analogy can help an engineer reuse a known pattern, but similarities do not prove that the same result will occur in both situations.

Consider a possible comparison between agricultural and mineral supply-chain intelligence:

| Agricultural supply chain | Possible mining/mineral counterpart |
|---|---|
| Producer or cooperative | Mine operator, licence holder or mining cooperative |
| Farm or production location | Mine site or mineral production location |
| Commodity and variety/grade | Mineral type, ore grade and specification |
| Aggregation and processing | Mineral aggregation, beneficiation and processing |
| Weighing, packaging and dispatch | Weighing, grading, custody and dispatch |
| Transport and buyer destination | Transport route, processor, buyer or export destination |
| Source and evidence provenance | Source, assay, licence, inspection and transaction evidence |

The structural similarity suggests that certain engineering capabilities may be reusable:
- Entity and location registries.
- Source and evidence provenance.
- Event and movement records.
- Classification and quality checks.
- Workflow and approval tracking.
- Reporting and audit trails.

But it would be unsafe to copy agricultural rules into mining. Mining has different legal permissions, licensing, environmental requirements, mineral classifications, assay standards, custody controls, stakeholders and risks. The analogy suggests what to investigate; it does not establish that the same data model, evidence standard or workflow is fit for mining.

The same principle applies to healthcare. Reusing a general idea such as traceable records does not mean agricultural data permissions, autonomy settings or evidence rules can be transferred to patient information or clinical decisions.

### 7. Strong versus weak analogies

A useful analogy depends on relevant structural similarities, not superficial resemblance.

A **stronger analogy**:
- Identifies the specific function or problem being compared.
- Shows how the relationships or constraints are similar.
- Identifies which features differ.
- States what is proposed for transfer and what still needs validation.
- Tests the proposed transfer in the destination domain.

A **weaker analogy**:
- Relies on a shared label or appearance.
- Ignores important domain differences.
- Assumes that a solution successful in one setting will work in another.
- Treats a possible transfer as proven without testing.

For engineering, an analogy should generate a candidate design principle or hypothesis, not replace requirements analysis and validation.

### 8. How agents should use causal reasoning

When an agent observes a relationship and is asked to explain it, it should:

1. State the observations and their provenance separately from interpretations.
2. Define the proposed cause and outcome precisely.
3. Check whether the variables refer to comparable entities, locations, units and time periods.
4. Establish the sequence of events where temporal order matters.
5. Identify possible mechanisms linking the proposed cause and outcome.
6. Generate alternative explanations and possible confounders.
7. Identify what comparison or additional evidence could distinguish the hypotheses.
8. Assess whether the available data and method support a causal conclusion or only an association.
9. Limit the conclusion to the population, locations, products and periods actually studied.
10. State uncertainty, assumptions and what evidence would change the conclusion.

For high-impact decisions, the agent should not make causal claims solely from a language model's narrative or a chart showing two trends. It should use suitable analytical methods, transparent evidence and appropriate expert review.

### 9. How agents should use analogy

When an agent proposes transferring a method or design from one domain to another, it should:

1. Define the exact function or problem the existing method solves.
2. Identify the important entities, relationships, constraints and risks in the original setting.
3. Identify the corresponding entities and relationships in the destination setting.
4. Separate structural similarities from surface similarities.
5. List important differences, including regulation, permissions, terminology, data rights, evidence standards and consequences of error.
6. State which principles appear reusable and which elements must be redesigned.
7. Test the adapted method in the destination context.
8. Record the validation evidence and remaining limitations.

This is the method behind the project's sector-transfer approach: transfer candidate principles, then validate them independently in each sector.

### 10. Common failure modes and safeguards

| Failure mode | What goes wrong | Safeguard |
|---|---|---|
| Correlation treated as causation | Co-movement is reported as proof that one factor caused another. | Examine mechanisms, time order, confounders and alternative explanations. |
| Confounding ignored | A shared factor explains some or all of the observed association. | Identify and assess plausible common causes. |
| Reverse causality | The direction of influence is assumed rather than examined. | Consider both directions and the timing of changes. |
| Before-and-after overclaim | A change after an event is automatically attributed to that event. | Check comparison groups and other changes over the same period. |
| Selective comparisons | Only locations or cases supporting the preferred explanation are examined. | Define comparison criteria and inspect contrary cases. |
| Surface analogy | Superficial similarities hide important structural differences. | Compare relationships, requirements and constraints. |
| Unvalidated transfer | A design from one sector is copied unchanged into another. | Adapt and independently test the destination-domain version. |
| Causal overstatement | A contributing factor is presented as the sole cause. | Allow multiple contributing factors and report limits. |

### 11. Key principles

- Correlation describes an observed association; it does not by itself establish causation.
- A proposed cause should generally precede the outcome, but temporal order alone is not proof.
- Mechanisms, confounders, reverse causality, alternative explanations and counterfactual comparisons matter.
- Before-and-after observations need careful interpretation because other factors may change at the same time.
- Causal conclusions depend on evidence and research design, not merely plausible stories or charts.
- Analogy uses relevant similarities to suggest a possible explanation or transferable approach.
- Structural similarities matter more than superficial resemblance.
- Every analogy has limits; important differences must be identified explicitly.
- A design principle that works in one sector remains a candidate for another until independently validated there.
- Agents must distinguish observations, associations, causal hypotheses, supported causal conclusions and proposed analogies.

## Lesson checkpoint

An agricultural intelligence system notices that tomato quotations and transport fuel prices rose during the same period.

It is not justified in concluding that fuel prices caused the tomato-price increase. It should investigate timing, route-specific transport costs, supply arrivals, product comparability and alternative explanations.

Now suppose the team proposes reusing an agricultural traceability workflow in mineral supply chains. The analogy may identify reusable ideas such as source provenance, location records, custody events and audit trails. It does not justify copying agricultural data rules, classifications or permissions into mining.

This is the central discipline of subsection 3.4: distinguish association from causation, and use analogy to generate carefully bounded transfer hypotheses rather than assume that similar-looking situations are identical.

## 3.4 Causal Reasoning, Correlation and Analogy

### Core question

When two things appear to change together, how can an agent decide whether one may influence the other, what else could explain the relationship, and whether a principle or solution from one situation can reasonably transfer to another?

This subsection covers three related but distinct ideas:

- **Correlation or association:** two variables or events vary together in some observed way.
- **Causal reasoning:** examining whether a change in one factor produces or contributes to a change in another, and what evidence supports that claim.
- **Analogical reasoning:** using relevant similarities between two situations to suggest that an explanation, method or design pattern from one may be useful in the other.

Each can help an agent investigate and reason, but each can also mislead when used carelessly.

### 1. Correlation does not establish causation

A **correlation** is an observed association or pattern of co-variation between variables. For example, two measurements may tend to increase together, one may increase while the other decreases, or no clear relationship may appear.

A correlation can be useful: it can identify a pattern worth investigating. But it does not, by itself, tell us why the pattern exists.

Suppose tomato prices and transport fuel prices both increase during a particular period. The observations show that the two variables moved together. They do not, on their own, prove that the rise in fuel prices caused the tomato-price increase.

Other possibilities include:
- The price of tomatoes and fuel were both affected by a wider economic or seasonal development.
- Tomato supply decreased for a separate reason.
- Demand increased.
- The observations refer to different market levels, grades, units or periods.
- One or both measurements are inaccurate or not comparable.

The responsible conclusion is that the two observed series moved together in the sample. A causal explanation requires additional investigation.

### 2. Three important causal traps

#### A. A common cause or confounding factor

A **confounder** is a factor that influences, or is associated with, both the proposed cause and the outcome, making their relationship difficult to interpret.

A simplified structure is:

```text
              Shared factor C
                /       \
               v         v
          Factor A ---> Outcome B
```

For example, a seasonal disruption might affect both fuel logistics and the volume of tomatoes reaching a market. Fuel prices and tomato prices may then rise together, even if the observed relationship is partly or mainly explained by the shared disruption.

If the agent does not consider the common factor, it may attribute too much influence to A.

#### B. Reverse causality

The proposed direction may be wrong, or influence may operate in both directions.

For example, higher demand for transport services could affect transport prices, while higher transport costs could also affect the delivered prices of agricultural products. Observing that two values move together does not establish which direction of influence is operating.

#### C. Coincidence, selection effects or a shared time trend

Two unrelated variables can move together by chance, or because both follow a wider time pattern. A relationship may also appear because the agent selected only certain locations, periods or successful cases.

A correlation found in a small or selectively collected sample may disappear when broader evidence is examined.

These traps show why a chart, pattern or statistical relationship is a starting point for investigation—not a causal conclusion.

### 3. What makes a causal explanation more credible?

Causal reasoning examines more than whether two variables move together. It asks whether the proposed cause could plausibly produce the outcome and whether the evidence is consistent with that mechanism.

Useful questions include:

1. **Temporal order:** Did the proposed cause occur before the outcome it is supposed to influence? This is generally necessary for a direct cause, but it is not sufficient proof.
2. **Mechanism:** Is there a credible process through which the cause could affect the outcome?
3. **Alternative explanations:** Could another factor, including a common cause, explain the observed relationship?
4. **Consistency:** Does the relationship appear in other relevant settings or periods, or is it confined to one unusual sample?
5. **Exposure pattern:** Where relevant, does a larger exposure to the proposed cause correspond to a different outcome in a way consistent with the proposed mechanism?
6. **Counterfactual comparison:** What would likely have happened to the outcome under comparable conditions if the proposed cause had not occurred?
7. **Disconfirming evidence:** What observations would weaken or contradict the causal explanation?

No single question automatically proves causality. The appropriate evidence depends on the domain, available data, assumptions and consequences of being wrong.

### 4. Counterfactual thinking and comparison

A **counterfactual** asks what would have happened under an alternative condition.

For example:

- Observed situation: transport costs increased on a particular supply route and delivered tomato prices later increased.
- Counterfactual question: what would the tomato price have been over the same period if transport costs on that route had not increased, with other relevant conditions held comparable?

We cannot directly observe both outcomes for the exact same market, product and time under both conditions. The counterfactual must be estimated using a suitable comparison or research design.

Possible approaches include:
- Comparing similar markets with different exposure to the transport-cost change.
- Comparing periods before and after a change while checking for other developments occurring at the same time.
- Using a comparison group or location that was not exposed to the same change.
- Examining a natural or policy-driven event that creates a meaningful difference in exposure.
- Conducting a controlled experiment where it is ethical, lawful and feasible.

A simple before-and-after comparison is not automatically causal. Other changes may have occurred between the two periods. Likewise, two locations are not valid comparison groups merely because they are nearby; their products, supply routes, demand, seasonality and other relevant conditions may differ.

Randomised controlled experiments can provide strong causal evidence in suitable contexts, but many market and social questions cannot be randomly assigned. Observational studies can still provide useful causal evidence when their assumptions and limitations are carefully examined.

### 5. A practical agricultural example

Suppose the pilot observes:
- Higher tomato quotations in a market.
- Higher transport fuel prices over a similar period.
- Reports that fewer tomato loads arrived at the market.

The agent should not immediately say that fuel prices caused tomato prices to rise.

It should separate the evidence:

| Item | What is currently observed or proposed |
|---|---|
| Tomato quotations | Increased in the sampled observations, subject to comparability checks. |
| Fuel prices | Increased over a similar period, subject to source and location checks. |
| Market arrivals | Some reports suggest a reduction; the quantity and evidence quality need verification. |
| Proposed explanation | Higher transport costs may have contributed to delivered prices. |
| Other explanations | Reduced production, road disruption, seasonality, demand, grade differences or inaccurate observations. |
| What is missing | Route-specific transport costs, arrival volumes, comparable market observations and evidence about timing. |

A stronger investigation would determine whether transport costs actually rose on the relevant supply routes, whether they materially affected the delivered cost of tomatoes, and whether competing factors could explain the price movement.

Even if transport costs contributed, they may not be the only cause. A careful report may conclude that transport costs are a plausible contributing factor supported by specified evidence, while other causes remain unresolved.

### 6. Analogy: reasoning from relevant similarities

**Analogical reasoning** compares two situations that share relevant features and uses those similarities to suggest a possible conclusion, explanation or design approach.

An analogy can help an engineer reuse a known pattern, but similarities do not prove that the same result will occur in both situations.

Consider a possible comparison between agricultural and mineral supply-chain intelligence:

| Agricultural supply chain | Possible mining/mineral counterpart |
|---|---|
| Producer or cooperative | Mine operator, licence holder or mining cooperative |
| Farm or production location | Mine site or mineral production location |
| Commodity and variety/grade | Mineral type, ore grade and specification |
| Aggregation and processing | Mineral aggregation, beneficiation and processing |
| Weighing, packaging and dispatch | Weighing, grading, custody and dispatch |
| Transport and buyer destination | Transport route, processor, buyer or export destination |
| Source and evidence provenance | Source, assay, licence, inspection and transaction evidence |

The structural similarity suggests that certain engineering capabilities may be reusable:
- Entity and location registries.
- Source and evidence provenance.
- Event and movement records.
- Classification and quality checks.
- Workflow and approval tracking.
- Reporting and audit trails.

But it would be unsafe to copy agricultural rules into mining. Mining has different legal permissions, licensing, environmental requirements, mineral classifications, assay standards, custody controls, stakeholders and risks. The analogy suggests what to investigate; it does not establish that the same data model, evidence standard or workflow is fit for mining.

The same principle applies to healthcare. Reusing a general idea such as traceable records does not mean agricultural data permissions, autonomy settings or evidence rules can be transferred to patient information or clinical decisions.

### 7. Strong versus weak analogies

A useful analogy depends on relevant structural similarities, not superficial resemblance.

A **stronger analogy**:
- Identifies the specific function or problem being compared.
- Shows how the relationships or constraints are similar.
- Identifies which features differ.
- States what is proposed for transfer and what still needs validation.
- Tests the proposed transfer in the destination domain.

A **weaker analogy**:
- Relies on a shared label or appearance.
- Ignores important domain differences.
- Assumes that a solution successful in one setting will work in another.
- Treats a possible transfer as proven without testing.

For engineering, an analogy should generate a candidate design principle or hypothesis, not replace requirements analysis and validation.

### 8. How agents should use causal reasoning

When an agent observes a relationship and is asked to explain it, it should:

1. State the observations and their provenance separately from interpretations.
2. Define the proposed cause and outcome precisely.
3. Check whether the variables refer to comparable entities, locations, units and time periods.
4. Establish the sequence of events where temporal order matters.
5. Identify possible mechanisms linking the proposed cause and outcome.
6. Generate alternative explanations and possible confounders.
7. Identify what comparison or additional evidence could distinguish the hypotheses.
8. Assess whether the available data and method support a causal conclusion or only an association.
9. Limit the conclusion to the population, locations, products and periods actually studied.
10. State uncertainty, assumptions and what evidence would change the conclusion.

For high-impact decisions, the agent should not make causal claims solely from a language model's narrative or a chart showing two trends. It should use suitable analytical methods, transparent evidence and appropriate expert review.

### 9. How agents should use analogy

When an agent proposes transferring a method or design from one domain to another, it should:

1. Define the exact function or problem the existing method solves.
2. Identify the important entities, relationships, constraints and risks in the original setting.
3. Identify the corresponding entities and relationships in the destination setting.
4. Separate structural similarities from surface similarities.
5. List important differences, including regulation, permissions, terminology, data rights, evidence standards and consequences of error.
6. State which principles appear reusable and which elements must be redesigned.
7. Test the adapted method in the destination context.
8. Record the validation evidence and remaining limitations.

This is the method behind the project's sector-transfer approach: transfer candidate principles, then validate them independently in each sector.

### 10. Common failure modes and safeguards

| Failure mode | What goes wrong | Safeguard |
|---|---|---|
| Correlation treated as causation | Co-movement is reported as proof that one factor caused another. | Examine mechanisms, time order, confounders and alternative explanations. |
| Confounding ignored | A shared factor explains some or all of the observed association. | Identify and assess plausible common causes. |
| Reverse causality | The direction of influence is assumed rather than examined. | Consider both directions and the timing of changes. |
| Before-and-after overclaim | A change after an event is automatically attributed to that event. | Check comparison groups and other changes over the same period. |
| Selective comparisons | Only locations or cases supporting the preferred explanation are examined. | Define comparison criteria and inspect contrary cases. |
| Surface analogy | Superficial similarities hide important structural differences. | Compare relationships, requirements and constraints. |
| Unvalidated transfer | A design from one sector is copied unchanged into another. | Adapt and independently test the destination-domain version. |
| Causal overstatement | A contributing factor is presented as the sole cause. | Allow multiple contributing factors and report limits. |

### 11. Key principles

- Correlation describes an observed association; it does not by itself establish causation.
- A proposed cause should generally precede the outcome, but temporal order alone is not proof.
- Mechanisms, confounders, reverse causality, alternative explanations and counterfactual comparisons matter.
- Before-and-after observations need careful interpretation because other factors may change at the same time.
- Causal conclusions depend on evidence and research design, not merely plausible stories or charts.
- Analogy uses relevant similarities to suggest a possible explanation or transferable approach.
- Structural similarities matter more than superficial resemblance.
- Every analogy has limits; important differences must be identified explicitly.
- A design principle that works in one sector remains a candidate for another until independently validated there.
- Agents must distinguish observations, associations, causal hypotheses, supported causal conclusions and proposed analogies.

## Lesson checkpoint

An agricultural intelligence system notices that tomato quotations and transport fuel prices rose during the same period.

It is not justified in concluding that fuel prices caused the tomato-price increase. It should investigate timing, route-specific transport costs, supply arrivals, product comparability and alternative explanations.

Now suppose the team proposes reusing an agricultural traceability workflow in mineral supply chains. The analogy may identify reusable ideas such as source provenance, location records, custody events and audit trails. It does not justify copying agricultural data rules, classifications or permissions into mining.

This is the central discipline of subsection 3.4: distinguish association from causation, and use analogy to generate carefully bounded transfer hypotheses rather than assume that similar-looking situations are identical.

## 3.5 Hypotheses, Evidence, Confidence and Limitations

### Core question

When an agent makes a claim, proposes an explanation or draws a conclusion from incomplete information, how can it show what supports that conclusion, how strong the support is, what remains uncertain and where the conclusion must stop?

This subsection brings together the reasoning methods in Chapter 3. An agent must not only produce a conclusion. It must be able to distinguish observations from interpretations, identify the hypothesis being considered, assess the supporting and contradicting evidence, express confidence proportionately and state the limitations of what it knows.

A useful result is not necessarily a certain answer. Sometimes the most reliable result is a clear account of what is known, what is plausible, what is unresolved and what evidence is needed next.

### 1. What is a hypothesis?

A **hypothesis** is a proposed statement or explanation that can be examined against evidence.

It may describe:
- A possible explanation for an observation.
- A suspected relationship between variables.
- A possible pattern in a group of observations.
- A prediction about what may happen under stated conditions.
- A claim about an entity, place, event or process that still needs verification.

Agricultural examples:
- "Tomato arrivals at Market A decreased during the reported period."
- "Higher transport costs may have contributed to the increase in delivered tomato quotations."
- "The cooperative listed in this source produced Product B at the stated location during the 2026 dry season."
- "The available observations suggest that wholesale prices increased in the sampled markets."

These statements are not all the same kind of hypothesis. Some are factual claims, some are explanatory, and some are generalisations. The agent should identify what kind of claim it is assessing and what evidence could support or weaken it.

A useful hypothesis should be sufficiently clear and bounded to examine. Specify, where relevant:
- The entity or variables involved.
- The claimed relationship, event or explanation.
- The geographic and organisational scope.
- The relevant product, category or population.
- The period or conditions.
- What observations would support it.
- What observations would weaken it.

Avoid vague claims such as "the agricultural market is changing" when the actual issue concerns one product, one market level, a limited sample and a particular period.

### 2. Observation, evidence, hypothesis and conclusion are different

These terms should not be used interchangeably.

| Term | Meaning | Agricultural example |
|---|---|---|
| **Observation** | Something recorded or directly noticed. | A published page displays a tomato wholesale quotation for Market A on a stated date. |
| **Evidence** | Information used to assess a particular claim. | The original dated quotation, its source and any independent corroborating record. |
| **Hypothesis** | A proposed statement or explanation being examined. | The quotation increased because market arrivals declined. |
| **Inference** | The reasoning that connects the evidence to a conclusion. | Comparable dated quotations are higher; separate arrival information also suggests a reduction. |
| **Conclusion** | The assessment reached from the evidence and reasoning. | The quotations increased in the observed sample; reduced arrivals remain a possible contributing explanation, not established as the cause. |

A source may contain an observation without providing adequate evidence for every claim someone wants to make from it.

For example, a page showing an indicative price may support the statement that the page displayed that quotation at the time it was inspected. It does not automatically support the statement that a transaction occurred at that price, that the price represents the entire market, or that the quoted value is still current.

### 3. Evidence must be assessed in relation to a claim

Evidence is not simply "good" or "bad" in the abstract. Its usefulness depends on the exact claim being assessed.

Suppose we want to establish that a cooperative produced tomatoes at a named village during a specified season.

A source that merely lists the cooperative's address may be relevant to its location, but it may not establish production there. A directory entry listing tomatoes may establish that tomatoes are associated with the cooperative in that directory, but it may not establish actual production during the stated season.

For each claim, ask:

1. **Relevance:** Does the information address the exact claim?
2. **Directness:** Is it direct evidence of the event or only an indirect indication?
3. **Provenance:** Who created it, and can the original source be identified?
4. **Reliability:** What is known about the source's methods, competence, incentives and possible errors?
5. **Independence:** Is this separate corroboration or a copy of another report?
6. **Freshness:** Does the date fit the period the claim concerns?
7. **Completeness:** Are important details missing?
8. **Comparability:** Are products, units, definitions, locations and periods sufficiently alike?
9. **Consistency:** Does the evidence agree with other relevant information, or are there conflicts?
10. **Reproducibility:** Can another reviewer inspect the source and follow the assessment?

A source's reputation does not make every claim it publishes automatically true. Likewise, a less formal source may provide a useful direct observation, but its limitations must be understood and its claims checked proportionately.

### 4. Source reliability is not the same as claim verification

Several related dimensions should be kept separate:

- **Source reliability:** how dependable the source generally is for the type of information in question.
- **Claim verification:** whether the specific claim has been checked against adequate evidence.
- **Evidence status:** what kind of evidence is available and what it establishes.
- **Freshness:** whether the information is current enough for the intended use.
- **Representativeness:** whether the observations support a claim about a wider population or area.
- **Comparability:** whether observations can legitimately be compared.
- **Inference strength:** how strongly the evidence supports the conclusion being drawn.

For example, an official national statistical report may be a reliable source for its published state-level average. It may still be unsuitable for establishing today's price at one named local market.

Similarly, a verified transaction in one market can establish something about that transaction. It does not automatically establish the average price across Plateau State.

A record's evidence status must therefore not be used as a shortcut for all the other dimensions.

### 5. Supporting, contradicting and missing evidence

An agent should look for three kinds of information:

- **Supporting evidence:** information consistent with the hypothesis.
- **Contradicting evidence:** information that conflicts with the hypothesis or weakens it.
- **Missing or unavailable evidence:** information needed to assess the claim but not currently available.

These should be recorded distinctly.

Suppose the hypothesis is: "Tomato prices increased in all major Plateau markets during the observation period."

- Higher comparable quotations from several markets support part of the hypothesis.
- Comparable observations showing stable or falling quotations in another major market contradict the universal wording.
- Missing observations from several LGAs leave the coverage incomplete.

The responsible conclusion may be that prices increased in the sampled markets, but there is not enough evidence to establish an increase in all major Plateau markets.

Do not ignore contradictory observations or silently remove them because they complicate the story.

### 6. Absence of evidence is not always evidence of absence

This distinction is essential for intelligence systems.

If a search does not find a record of a cooperative producing a particular commodity, several explanations are possible:
- The cooperative did not produce it.
- The activity occurred but was not published.
- The relevant source is offline or not indexed.
- The source uses another name or classification.
- The record exists but could not be accessed.
- The search method or geographic coverage was incomplete.

Therefore:

**"We did not find evidence that the cooperative produced tomatoes" is not automatically equivalent to "the cooperative did not produce tomatoes."**

Absence can become meaningful evidence when the search or monitoring process is known to have sufficiently complete coverage and the claim implies that a record should exist. Even then, the conclusion must be limited to that system, scope and period.

For example, if a complete, authoritative register is known to list every currently licensed operator in a defined jurisdiction, absence from that register may support a narrower conclusion about licensing status. The completeness and authority of the register must themselves be established.

### 7. Confidence: how strongly is the conclusion supported?

**Confidence** describes how strongly the available evidence and reasoning support a particular conclusion or hypothesis.

It should not be confused with:
- The agent's fluency or persuasiveness.
- How familiar or plausible the explanation sounds.
- The number of times a claim has been repeated.
- A source's general reputation alone.
- A numeric probability invented without a defensible method.

Confidence is claim-specific. An agent may have strong confidence that a webpage displayed a particular figure when inspected, while having low confidence that the figure represents a completed transaction or the current market price.

A simple qualitative vocabulary can be useful as a project working convention:

| Label | Meaning for reporting |
|---|---|
| **Strongly supported** | Multiple relevant checks support the specific claim; important alternatives or conflicts have been examined; remaining limitations do not undermine the bounded conclusion. |
| **Moderately supported** | Relevant evidence supports the claim, but material gaps, source limitations or unresolved alternatives remain. |
| **Weakly supported** | Some information is consistent with the claim, but it is indirect, incomplete, poorly corroborated or affected by important uncertainty. |
| **Unresolved** | Available evidence is insufficient, conflicting or unsuitable for choosing between the claim and credible alternatives. |
| **Contradicted by available evidence** | Relevant evidence conflicts with the claim within the stated scope. This does not prove every possible alternative claim. |

These labels are provisional reporting categories, not universal statistical confidence levels. Their use should be accompanied by a short explanation of the evidence and limitations. Do not assign percentages such as 80% or 95% merely to make an answer appear precise.

Where a statistical model or formal probability method is used, its assumptions, calibration, data and validation should be documented separately.

### 8. Confidence should change when evidence changes

An agent must be willing to revise a conclusion.

For example:

1. A single unverified post reports a sudden tomato-price increase.
2. The agent marks the claim as weakly supported and seeks the original source.
3. The original post is found to be several weeks old and does not identify the product grade.
4. The apparent current price signal is weakened.
5. A separate, dated quotation from the relevant market is obtained.
6. The agent can now support the narrower claim that a particular quotation was published for that market and date.
7. It still cannot claim a completed transaction or a statewide price increase without the relevant evidence.

New evidence does not always increase confidence. It can reduce it, reveal that two sources were duplicates, or show that the original question was framed too broadly.

A reliable agent updates the assessment rather than defending its first answer.

### 9. Limitations must be explicit

A conclusion should identify the limits that affect how it can be used.

Common limitations include:

- Geographic coverage is narrower than the claimed area.
- Only selected commodities or product forms are included.
- Observation dates are old, missing or inconsistent.
- A quotation is being compared with a transaction.
- A dataset combines observed and model-estimated values.
- Sources are duplicated or share the same upstream source.
- The sample is small or selected in a biased way.
- Important locations or population groups are missing.
- A causal mechanism has not been established.
- A hypothesis remains one of several plausible explanations.
- Access restrictions prevent examination of the underlying evidence.
- A source's methodology or data rights are not known.

Limitations are not decorative disclaimers. They determine what the system can responsibly claim and what decisions the information can support.

### 10. Applying the full method to the agricultural pilot

Consider the provisional hypothesis:

> There may be value in connecting locally grounded Plateau market observations to transparent source provenance, dates, product definitions, units, evidence status and comparable market-level records.

The five candidate sources in our discovery register provide different kinds of information:

- NBS describes broad LGA-level price collection but state/national weighted-average public outputs.
- The World Bank publishes selected market-level modeled estimates, but the newest indexed file and the accessible detailed pages have a version discrepancy, and actual Plateau market rows remain to be checked.
- FAO describes extensive price series and national-system integration capabilities, but Nigeria-specific coverage remains uninspected.
- PLACOM advertises local indicative prices, but the actual observation methodology and record detail remain unverified.
- Agromate distinguishes nearby surveyed FEWS NET/WFP markets from its own Plateau pilot estimates.

This evidence makes the local traceability/coverage hypothesis worth investigating. It does not prove that no suitable service exists or that users experience an unmet need.

A disciplined assessment would be:

| Assessment field | Current position |
|---|---|
| Hypothesis | A locally grounded, traceable Plateau market-information workflow may have value. |
| Supporting evidence | Existing source descriptions show different coverage and data forms; PLACOM advertises indicative local prices; Agromate distinguishes nearby surveys from Plateau pilot estimates. |
| Contradicting or alternative considerations | PLACOM may already satisfy some local needs; other offline or institutional channels may exist; the apparent gap may not matter to users. |
| Missing evidence | PLACOM's actual data methodology; current World Bank market rows; NBS workbook details; FAO Nigeria series; Agromate CSV lineage; actual user needs and workarounds. |
| Current confidence | **Weakly supported as an opportunity hypothesis; not yet a validated user problem or market gap.** |
| Next evidence | Inspect raw data and methods, identify existing channels, and gather evidence about specific user decisions and difficulties. |
| Decision | Continue discovery; do not build or announce a market gap yet. |

This is an example of how evidence, abductive reasoning, induction, causal caution and limitation reporting work together.

### 11. A practical claim-assessment record for agents

For claims that materially influence an intelligence output or decision, a structured record may include:

| Field | What it captures |
|---|---|
| Claim ID | Stable identifier for the claim. |
| Exact claim | The specific statement being assessed. |
| Claim scope | Entity, product, location, period and relevant conditions. |
| Claim type | Observation, classification, generalisation, explanation, prediction or causal claim. |
| Hypothesis | The proposition being tested, where applicable. |
| Supporting evidence | Source references and the specific facts they establish. |
| Contradicting evidence | Sources or observations that weaken or challenge the claim. |
| Missing evidence | Important information not yet available. |
| Source assessment | Provenance, reliability, freshness and access limitations. |
| Independence | Whether corroborating sources are genuinely independent. |
| Reasoning method | Deduction, induction, abduction, causal reasoning or a combination. |
| Confidence assessment | Qualitative strength with a short rationale, or a validated quantitative method where appropriate. |
| Limitations | Scope, sample, measurement, method and domain restrictions. |
| Current status | Supported, partially supported, unresolved, contradicted or another defined state. |
| Reviewer and date | Who assessed it and when. |
| Reassessment trigger | New evidence, expiry, source change or another event requiring review. |

This is a proposed record structure for the pilot, not yet an approved production schema. We should test it against real claims and simplify or extend it only when justified.

### 12. A practical reasoning and evidence workflow

For a material claim, an agent can follow this sequence:

1. State the exact claim and its scope.
2. Identify whether it is an observation, rule application, generalisation, explanation, prediction or causal claim.
3. Collect the relevant original evidence under permitted access conditions.
4. Check provenance, date, source reliability, independence and relevance.
5. Check comparability, coverage, definitions and missing information.
6. Identify supporting and contradicting evidence.
7. Consider alternative hypotheses and the possibility of confounding or bias.
8. Apply the appropriate reasoning method and make the inference explicit.
9. Assess how strongly the evidence supports the bounded claim.
10. Record limitations and unresolved questions.
11. Decide whether to report, gather more evidence, ask for clarification or defer.
12. Set a review trigger where the claim may become stale or new evidence may change it.

Not every low-risk task needs a lengthy record. Apply proportionate evidence handling: more scrutiny is needed where the decision is more consequential, the source is uncertain or the claim may affect people, money, safety or public reporting.

### 13. Key principles

- A hypothesis is a proposition to examine, not an established fact.
- Observation, evidence, hypothesis, inference and conclusion are distinct.
- Evidence must be assessed against the precise claim it is intended to support.
- Source reliability, claim verification, evidence status, freshness, representativeness and inference strength are different dimensions.
- Seek supporting, contradicting and missing evidence.
- The absence of a record does not automatically prove that an event did not occur.
- Confidence should reflect the evidence and reasoning, not the agent's fluency or familiarity.
- Do not invent precise confidence percentages without a defensible statistical method.
- Conclusions must remain within the scope supported by evidence.
- Limitations must be explicit enough to guide use and decision-making.
- Reassess conclusions when new, contradictory or more current evidence arrives.
- Increase verification and oversight in proportion to the consequences of error.

## Lesson checkpoint

An agent finds several online reports suggesting that tomato prices are rising in Plateau State. It later discovers that many reports repeat the same original post, some have no observation date, and the available verified quotations are concentrated in two markets.

A defensible report would say that repeated reports indicate a possible upward price signal, but much of the material is not independent and the verified observations cover only two markets. The agent should not conclude that prices have risen across Plateau State. It should seek additional independent, dated and comparable observations.

The central discipline of subsection 3.5 is to make the strength and limits of knowledge visible: state what the evidence supports, how strongly it supports it, what contradicts it, what is missing and what should happen next.

## Chapter 3 progress

Subsections 3.1, Deductive Reasoning; 3.2, Inductive Reasoning; 3.3, Abductive Reasoning and Explanation; 3.4, Causal Reasoning, Correlation and Analogy; and 3.5, Hypotheses, Evidence, Confidence and Limitations, are covered. **Chapter 3 is complete.** Next: **Chapter 4.1 Problem and Environment Representation**.
