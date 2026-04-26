---
title: "Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems"
domain: EA
series-id: P1
type: position-paper
author: "[[../../../Context/Alexandru Mares/Alexandru Mares|Alexandru Mares]]"
status: draft-v12-rc
priority: foundational
venue: Zenodo → arXiv (cs.AI primary, cs.CY cross-list)
related:
  - "[[../ea-papers|EA Papers Map]]"
  - "[[../../papers-index|Papers Index]]"
tags: [type/paper, domain/EA, status/draft, project/EA]
---

# Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems

> **Paper 1: Position Paper**
> **Title:** Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems
> **Author:** Alexandru Mares, Independent Researcher
> **ORCID:** 0009-0009-6713-9780
> **Version:** 0.12.0
> **Status:** Release candidate
> **Target:** Zenodo (primary, instant DOI) → arXiv (cs.AI primary, cs.CY cross-list)
> **Created:** 2026-04-26
> **Last Modified:** 2026-04-26

---

## Abstract

We argue that many deployed language-model-driven systems are better described as **elastic automation** than as artificial minds. Traditional automation was rigid by design: rules fired when conditions were met, scripts followed predefined branches, and workflows moved only inside the shapes their designers had imagined. Language models did not need to produce minds to change this arrangement. They gave automation a flexible interface to natural language, allowing software to interpret messy input, classify intent, call tools, retry failed steps, and present coherent outputs to human users. None of this requires explaining the system as knowing in the way a human knows; it only requires the system to produce, in coherent sequence, the kind of output a knowing system would produce. The workflow became less brittle. The input boundary became softer. The automation became elastic.

We define an **elastic automator** as a system that uses a language model to turn uncertain human input into executable structure, then loops through generation, evaluation, correction, and presentation until the output appears intelligent. We argue that treating these systems as artificial minds creates a category error with design consequences, and propose a diagnostic frame: five loop questions that replace metaphysical inquiries about what these systems "know" or "decide" with practical engineering ones. Our contribution is not the underlying observation, which is well-established in practitioner literature [Anthropic, 2024; Zaharia et al., 2024]. It is the public-facing vocabulary, the lineage from rigid to elastic, and the diagnostic loop questions as a design framework. Naming changes design.

---

## 1. Introduction

The phrase *artificial intelligence* is a public-relations success story and a category error.

Investors, companies, journalists, and users all use a single phrase for systems that appear to perform tasks once associated with intelligent beings. The phrase is dramatic. It sells. As public vocabulary, it succeeded. But the technical reality is more specific: a complicated family of systems has been compressed into a phrase that already carried cultural weight before these systems existed.

The burden is not to deny that these systems are powerful. The burden is to specify what kind of power they have. In most deployed cases, the behavior can be explained without positing intention, belief, experience, or understanding in the human sense. What we have built are workflows. Workflows that have become flexible enough to negotiate language.

This paper does not argue that nothing has changed. Something has. The shift is genuine and worth naming carefully. We argue that it is best described as a category change *within* automation, from rigid to elastic, rather than as the emergence of a new category called intelligence.

The argument has three points. We start with the technical shift, from rule-based automation to language-model-driven automation. This is a change of *shape*, not of *species* (§2). Then we name **elastic automation** as the more precise vocabulary for this category, with **elastic automator** naming the system class (§3). The third point is that adopting this vocabulary changes the design questions worth asking, thus replacing metaphysical inquiries with diagnostic ones (§4–§5).

### Why Now

Naming things carries design consequences and influences public discourse.

From a design standpoint, engineers and product owners who build on top of large language models inherit a vocabulary. Words like *intelligence*, *understanding*, *agency* carry meaning and philosophical commitments that most of them did not intend to make. This shapes what gets measured, what gets evaluated, and what gets shipped.

Calling a system "intelligent" often pushes evaluation toward answer-level correctness, especially in public and product discourse. Calling a system an elastic automator shifts the evaluation questions to *what loop is running, what tools can it call, what failures does it hide before showing the final answer.*

Naming influences both direction and evaluation regime.

Today we try to attach "AI" to everything. From spam filters to multi-agent code-generation pipelines. This undifferentiated label is no longer benign. It produces inflated capability claims at one end and unwarranted alarm at the other. Both errors are downstream of the same imprecision.

### Contributions

This is a position paper that makes three contributions.

1. We define **elastic automation** as the category that contains language-model-driven workflow systems, and **elastic automator** as the name for instances of that category. We trace the lineage from rigid automation to clarify what changed and what did not (§2–§3).
2. We argue that treating these systems as artificial minds creates a category error with observable design consequences (§4).
3. We propose a simple diagnostic frame consisting of five loop questions that replace metaphysical inquiries with practical engineering ones (§5).

The position is not novel in its underlying observation, which is well-established in practitioner literature [Anthropic, 2024; Zaharia et al., 2024; IBM, n.d.] and increasingly named in the deflationary terminology literature [Shanahan, 2024; Bender & Hanna, 2025]. Nor in its philosophical lineage, which descends from Searle [1980] and Dreyfus [1972]. The contribution is the *terminological packaging* (a short adjective–noun pair with a clean lineage that travels well outside specialist contexts) and the *diagnostic loop questions* as a design framework.

---

## 2. From Rigid to Elastic

Traditional automation was rigid by design.

A rule fired when a condition was met. A script followed predefined branches. A workflow moved from step to step, but only inside the shape its designer had already imagined. Robotic Process Automation (RPA), enterprise workflow engines, and rule-based expert systems all share this property: they execute decisions made elsewhere, by humans, encoded in advance. Under this approach, the system has no capacity to interpret novel input. Anything outside the predetermined shape produces an error or a default.

Language models changed that shape because they gave automation a flexible interface to natural language. This allowed software to interpret messy input, rewrite instructions, classify intent, call tools, summarize results, retry failed steps, and present a response that feels coherent to a human reader. All the old machinery still ran underneath: rules still fired, branches still resolved, decisions still moved from step to step; but now the rules were soft enough to be argued with, and the decisions resilient enough to be revised mid-stream.

The workflow became less brittle. The input boundary became softer. The system did not need to become a mind for the automation to become elastic.

This is not a small change. The flexibility is real, and the systems built on top of it can do work that older automation could not. They discover patterns, compress knowledge, write code, coordinate tools, and adapt across tasks. Power is not in question. The question is what to call it. And calling these systems automation does not make them harmless; it makes their harms easier to locate.

The price of this softness is that the language model's outputs are no longer deterministic. The same input can produce different candidates across runs. The Evaluation step is therefore not optional decoration; it is the mechanism by which non-deterministic generation is contained inside a workflow that still needs to behave reliably.

We argue the answer is *elastic automation*. The lineage is direct: rigid automation hardened the workflow's shape; elastic automation softens it. Same family, but with a different shape. The adjective tells you what changed.

---

## 3. Definitions

We define the field and the system class.

**Elastic automation.** The practice of building workflow systems whose control flow, input interpretation, and output generation are mediated by a language model rather than by predefined rules or scripts. The defining property is *shape elasticity*: the workflow can accommodate inputs whose form was not anticipated by its designer. Operationally, shape elasticity is observable when the same workflow accepts semantically equivalent inputs in different forms, repairs partial or malformed input, routes ambiguous requests to plausible next steps, and uses evaluation gates to recover from failed intermediate outputs. The term names not composition alone, but *tolerance of shape*: the ability of a workflow to accept, repair, route, and re-present inputs whose form was not pre-enumerated.

**Elastic automator.** A system that uses a language model to turn uncertain human input into executable structure, then loops through generation, evaluation, correction, and presentation until the output appears intelligent.

The five components of the loop:

1. **Generation.** The language model produces a candidate output: a parsed structure, a tool call, a draft response.
2. **Evaluation.** The system checks the candidate against criteria. The criteria may be rule-based (schema validation), model-based (a second pass with different framing), or external (a tool returns success or failure).
3. **Correction.** Failed evaluations trigger revision: re-prompting, repair, re-routing.
4. **Presentation.** When the output passes evaluation, it is formatted for the human consumer or downstream system.
5. **Repeat.** The loop continues across the session, accumulating context and adapting to evolving input.

This loop is the architectural feature that distinguishes elastic automators from rigid automation, where behavior is pre-enumerated, and from stronger cognitive claims, where the question would be whether such loops are intrinsic to the cognitive architecture rather than externally scaffolded.

The four neighboring categories sit on different axes:

| Category | Control flow | Input handling | Failure mode | Diagnostic question |
|---|---|---|---|---|
| **Rigid automation** | Pre-enumerated branches | Schema-conformant only | Rejects out-of-shape input | What rules fire when? |
| **Elastic automation** | LLM-mediated loop inside developer-bounded control flow | Natural language; accommodates form variation | Silent retry exhaustion; hides discarded candidates | What loop is running? |
| **Agentic systems** | Runtime synthesis or selection of execution paths | Natural language | Runtime drift; goal/tool mis-specification | What is it optimizing for? |
| **Stronger cognitive systems** *(hypothetical)* | Integrated adaptive control | Possibly situated; persistent self-model | Belief/action revision under persistent commitments | What cognitive architecture is being claimed? |

Elastic automation sits between rigid automation and agentic systems. It inherits the loop-with-evaluation discipline that rigid automation enforces through code, but mediates that loop through a language model. The boundary with agentic systems is the predictability of the state space. In elastic automation, the developer enumerates the bounds of the workflow; the loop tolerates shape variation in inputs and outputs, but the set of possible execution paths is fixed in advance. In agentic systems, the system is permitted to synthesize execution paths that were not explicitly hardcoded into the scaffold's routing logic. Both architectures involve scaffolds. The difference is whether the control-flow graph is enumerated by the developer or generated at runtime.

The output *appears* intelligent. Note that we use the word *appears* deliberately. The appearance is the achievement. It is not a deception in the moral sense (the systems are doing real work), but it is not a mind, either. We call this automation that has learned to negotiate language.

Elastic automation is not a downgrade. And it may actually be the more precise achievement, because it names what was built rather than what was hoped for.

---

## 4. The Category Error

Does the name actually matter? The claim of this section is that calling these systems *intelligence* produces concrete and observable design consequences.

Three consequences in particular.

**Inflated evaluation.** When a system is positioned as intelligence in public and product discourse, evaluation often collapses toward *answer-level correctness* on open-ended tasks where ground truth is contested or absent. When the same system is positioned as elastic automation, it tends to be evaluated for *behavior under conditions*. What happens when input is malformed? Or when a tool fails? Or when memory drifts across turns? The first regime rewards systems that produce confident-sounding output; the second rewards systems whose loops are observable and whose failures are graceful. These two regimes select for different engineering choices.

**Misallocated trust.** A user interacting with "an AI" and a user interacting with "an elastic automation system that wraps a language model" do not extend the same epistemic credit to the output. The first vocabulary produces a tendency to treat the output as a judgment from a mind; the second produces a tendency to ask what the loop did. The first is the more widely encountered framing in 2026.

**Poorly-suited diagnostic questions.** When we mistake elastic automation for intelligence, we ask whether the system *knows*, *wants*, *understands*, or *decides*. These questions are interesting in their own right. But they are poorly suited as engineering diagnostics, because they cannot be answered by inspecting ordinary system traces in the way loop, tool, memory, and evaluation questions can. Searle [1980] argues directly that the mind-question, applied to a system that produces text, cannot be settled by examining the text; adjacent critiques from different angles [Dreyfus, 1972; Bender et al., 2021] reach compatible conclusions about the limits of text-only inference. The questions are not unanswerable in principle. They are not the most tractable diagnostic questions to ask about a workflow system from the outside.

**Anthropomorphic technical debt.** When developers treat the system as a mind that "understands" the user, they tend to skip the validators, edge-case tests, retry policies, and gating logic that elastic automation actually requires. The vocabulary of intelligence borrows trust the architecture has not earned. The cost shows up later, as fragile systems that fail in the gap between expected reasoning and actual loop behavior. The category error is not only a public-discourse problem; it is a software-engineering one.

The category error is the cost of using a word that imports a philosophical framework the underlying system was never built to satisfy.

---

## 5. A Diagnostic Frame

We propose replacing the metaphysical questions with five loop questions. Each names a concrete property of the elastic automator's architecture and admits an answer.

1. **What loop is running?** The control structure: how often the system iterates, what triggers a retry, what the termination condition is.
2. **What tools can it call?** The action surface: external systems, APIs, internal functions, the boundary between text generation and effect on the world.
3. **What state does it retrieve and mutate?** The context window's contents at each step (retrieved documents, conversation history, stored state, retrieval policy) AND the writes back to that state (profile updates, sub-task summaries, memory-store appends, cache invalidations).
4. **What criteria does it optimize?** The objective the loop pursues: explicit reward functions, implicit prompt-engineered preferences, evaluation gates between steps.
5. **What failures does it hide before showing the final answer?** The discarded candidates: failed tool calls suppressed in the user-facing output, retried generations whose intermediate state is not surfaced, errors smoothed by formatting.

The diagnostic frame is meant to be used during architecture review, incident analysis, and capability evaluation. Each question maps to an inspectable surface in the running system:

| Loop question | Evidence to inspect |
|---|---|
| What loop is running? | Orchestration code, traces, retry policy, termination condition |
| What tools can it call? | Tool registry, permissions, API logs |
| What state does it retrieve and mutate? | Retrieval logs, context payloads, memory policy, write-back logs, cache invalidations |
| What criteria does it optimize? | Prompts, validators, reward/eval functions, gates |
| What failures does it hide? | Failed candidates, suppressed tool errors, retries, discarded drafts |

Consider a concrete case. A customer-support agent retrieves the most relevant documentation page, drafts a reply, runs the draft past a tone classifier, regenerates if the classifier rejects the draft, and returns the surviving version. Now run the five questions against it. The loop has executed somewhere between one and three times. The tools were a documentation index and a tone-gate classifier. The state retrieved was the user's last five turns plus the matched page; the state mutated was a one-line summary appended to the conversation memory after each turn. The criterion was tone-gate pass-or-fail. The hidden failures were the drafts the gate rejected. Five questions, five answers. None of those answers settles whether the agent "understood" the user's request. All five describe what the agent actually did. Concretely: the team evaluating this agent stops treating a model-rated "empathy score" as the primary signal and starts asking for "tone-gate pass rate" and "number of retry loops triggered". The metric set changes because the questions changed.

These questions transfer cleanly to design and evaluation. They are answerable in principle, by inspection of the system's code, traces, and prompts. The benefit is that they do not require resolving the philosophical question of machine consciousness. These are the questions an engineer evaluating an elastic automator should ask, regardless of whether the system is also "intelligent" in some deeper sense.

We do not claim this list is complete. We claim it is a better starting point than the metaphysical alternatives.

---

## 6. Related Work

Is the conceptual space empty? Far from it.

Existing terms describe composition (compound AI systems), implementation pattern (LLM workflows), or autonomy claims (agentic systems). *Elastic automation* names the specific design change — from brittle pre-enumerated workflow shape to language-mediated shape tolerance — that the other terms describe but do not name directly. Below we acknowledge the prior and adjacent work explicitly, organized by what each contributes relative to the position taken here.

**Workflows versus agents.** Anthropic's "Building Effective Agents" essay [Anthropic, 2024] distinguishes *workflows* (LLMs in predefined orchestration) from *agents* (LLMs that decide control flow at runtime). The workflow side maps closely to elastic automation. Our contribution is the broader category and a public-facing vocabulary; their distinction is calibrated for engineers already inside the practitioner discourse.

**Compound AI systems.** Zaharia et al. [2024] describe the shift from monolithic models to systems with multiple components (retrieval, tools, control logic) wrapped around language models. Theirs emphasizes composition. Ours emphasizes lineage from rigid automation and the resulting design vocabulary.

**Agentic workflows.** Industry framings under *agentic workflows* [IBM, n.d.] make the rigid-versus-flexible distinction explicitly. We agree with the technical content but argue that *agentic* imports the same philosophical baggage as *intelligent* (the system is positioned as having agency), where *elastic* does not.

**LLM as operating system.** Karpathy [2023] proposes thinking of language models as a new kind of operating system. The framing emphasizes the LLM as substrate. Elastic automation emphasizes the workflow built on top of that substrate. The two are compatible.

**Modern terminology critique.** The most direct precedent is Shanahan [2024], who argues that the everyday vocabulary applied to these systems (*believes*, *knows*, *thinks*) does conceptual work and should be policed. Bender [2024] develops a parallel argument from a psychological-science angle. Bender and Hanna [2025] argue at book length that "AI is automation technology" — a thesis directly adjacent to ours. Their treatment is critical and broad. Ours is constructive and narrow: a specific term, a system definition, and a diagnostic frame for engineers.

**Critiques of agentic capability claims.** Kambhampati et al. [2024] argue that LLMs cannot plan but can serve as components inside external scaffolds that do — what they call LLM-Modulo frameworks. The architecture they describe is structurally identical to an elastic automator: a language model embedded in a loop of generation, evaluation, and correction. Kapoor et al. [2024] further argue that current "AI agent" benchmarks confuse engineering achievement with model capability, supporting the case for vocabulary that names the system rather than projecting agency onto it.

**Labeling and the category problem.** Narayanan and Kapoor [2024] (*AI Snake Oil*) argue at book length that *AI* as a label collapses heterogeneous techniques into a singular thing, with downstream cost to public understanding. Suchman [2023] argues from a science-and-technology-studies perspective that the "thingness" of *AI* — the move that treats a label as if it named a coherent referent — is itself the operation worth resisting. Both support the case that re-labeling parts of the *AI* category is not pedantry. It is a precondition for clearer thought.

**Philosophical critiques of machine intelligence.** Searle [1980], Dreyfus [1972], Bender et al. [2021], Marcus [2022], and Mitchell [2019, 2024] all argue, from different traditions, that systems producing text are not therefore minds. Mitchell [2024] argues that *intelligence* itself, as applied across human and machine systems, lacks the scientific specification its rhetorical use implies. Our position is not original on this critique. Our contribution is bringing it into a constructive vocabulary engineers can use without committing to any particular philosophical school.

The position summarized: the conceptual space is well-mapped in technical literature [Anthropic, 2024; Zaharia et al., 2024], in philosophical literature [Searle, 1980; Dreyfus, 1972; Bender et al., 2021], and increasingly in deflationary terminology literature [Shanahan, 2024; Bender & Hanna, 2025]. What is missing is the public-facing vocabulary that bridges them: short enough to travel outside specialist contexts, precise enough to do design work.

---

## 7. Limitations

What does this paper not do? Several limitations bear acknowledgment.

**The boundary case.** This paper takes elastic automation as the dominant present case but does not establish where the boundary lies between elastic automation and systems that may genuinely warrant a stronger description. Reasoning models, planning agents, and systems with long-horizon adaptation may sit at or beyond that boundary. We leave the boundary question open.

**Linguistic prescriptivism.** Coining a term does not displace an established label. *AI* is deeply embedded in commerce, regulation, and media. We do not predict that *elastic automation* will replace it. But we argue that *elastic automation* is a more precise term where precision matters: in design discussions, in evaluation methodology, and in technical communication that aims to clarify rather than market.

**Domain scope.** This paper addresses language-model-driven workflow systems. It does not address perception models, generative-art models, or single-purpose classifiers, all of which are also called *AI* in common usage but whose architecture differs.

**Naming collision.** The adjective *elastic* has prior associations with Elastic N.V. (the Elasticsearch company) and with cloud autoscaling. We retain the term because it communicates the relevant property (shape elasticity, the workflow's capacity to accommodate inputs whose form was not anticipated) more cleanly than any neighboring adjective we considered. The collision with Elastic N.V.'s product line is brand-adjacency at the lexical level rather than definitional overlap; we disambiguate in a footnote.[^1]

**Empirical validation.** This is a position paper. The claim that the diagnostic loop questions improve evaluation outcomes, or that the *elastic automation* vocabulary changes design behavior in practice, is not tested here. Companion empirical work is left to subsequent papers.

---

## 8. Conclusion

We do not need to treat most deployed language-model-driven workflow systems as artificial minds to explain their behavior. We can explain them more precisely as automation made elastic by language models.

We have proposed *elastic automation* as the field, *elastic automator* as the system class, and a five-question diagnostic frame as the design tool that follows from naming the category correctly. This position depends on a category claim: that flexible language-model-wrapped workflows are often better classified as a *kind of automation* than as a *kind of intelligence*. It also depends on the further claim that classification has design consequences.

Both claims are testable, in different ways. The first is testable by argument and by the slow pull of vocabulary across a discipline. The second is testable by examining whether teams that adopt the loop-question diagnostic accumulate less anthropomorphic technical debt, track more mechanistic metrics (retry exhaustion rates, tone-gate pass rates, hidden-failure counts) rather than model-rated proxy scores, and produce systems that fail more gracefully.

For the systems addressed here, *elastic automator* is the more precise achievement, and the more useful name.

---

## Acknowledgments

Portions of this manuscript were drafted with AI assistance. The author retains full intellectual ownership and responsibility for all claims, terminology, and conclusions presented in this work. The category framing, the specific definition of *elastic automation*, the *elastic automator* system class, and the five loop questions are the original contributions of the author.

---

## Ethics Statement

This paper proposes terminological precision in a domain (*artificial intelligence*) where vocabulary carries significant commercial, regulatory, and social weight. We acknowledge that arguing against the dominant label has commercial implications for systems marketed as AI. And that the deflationary direction of this argument could be taken up in ways the author does not intend (for instance, to dismiss legitimate concerns about language-model-driven systems on the grounds that they are "merely" automation). We argue the opposite. Calling these systems elastic automation makes their behavior *more* legible, not less. And legibility is a precondition for serious public discussion of their effects. What this paper resists is not the AI conversation but its current shape: a debate that asks whether the systems are minds, when the more useful question, asked in plain words, is what these systems actually do when no one is watching the loop. The argument is for precision, not dismissal.

---

## Notes

[^1]: This paper proposes *elastic automation* as a category label for LLM-mediated workflow systems whose control flow is shape-elastic (§3). Elastic N.V., independently and concurrently, ships a product line called Elastic Workflows (technical preview 2025) and Elastic Agent Builder (general availability January 2026), which combine YAML-defined workflow execution with optional language-model reasoning steps. Elastic N.V. does not use *elastic automation* as a defined term in their literature; they use *Elastic Workflows*, *Agent Builder*, *native automation*, and *intelligent automation*. Specialist readers in the Elastic N.V. ecosystem may translate as follows: an Elastic Workflows deployment is one possible *instance* of an elastic automator under our definition; the converse does not hold.

---

## References

- Anthropic. (2024). *Building Effective Agents.* anthropic.com/news/building-effective-agents. December 19, 2024. Accessed April 2026.
- Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On the Dangers of Stochastic Parrots: Can Language Models Be Too Big? *Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency (FAccT '21)*, 610–623. https://doi.org/10.1145/3442188.3445922.
- Bender, E. M. (2024). Resisting Dehumanization in the Age of "AI." *Current Directions in Psychological Science*, 33(2). https://doi.org/10.1177/09637214231217286.
- Bender, E. M., & Hanna, A. (2025). *The AI Con: How to Fight Big Tech's Hype and Create the Future We Want.* New York: Harper.
- Dreyfus, H. L. (1972). *What Computers Can't Do: A Critique of Artificial Reason.* New York: Harper & Row.
- IBM. *What are Agentic Workflows?* ibm.com/think/topics/agentic-workflows. Accessed April 2026.
- Kambhampati, S., Valmeekam, K., Guan, L., Verma, M., Stechly, K., Bhambri, S., Saldyt, L., & Murthy, A. (2024). Position: LLMs Can't Plan, But Can Help Planning in LLM-Modulo Frameworks. *Proceedings of the 41st International Conference on Machine Learning (ICML)*. arXiv:2402.01817.
- Kapoor, S., Stroebl, B., Siegel, Z. S., Nadgir, N., & Narayanan, A. (2024). AI Agents That Matter. *arXiv preprint*. arXiv:2407.01502.
- Karpathy, A. (2023). *[1hr Talk] Intro to Large Language Models* (lecture). YouTube. November 2023. https://www.youtube.com/watch?v=zjkBMFhNj_g. Accessed April 2026.
- Marcus, G. (2022). Deep Learning Is Hitting a Wall. *Nautilus*, March 10, 2022.
- Mitchell, M. (2019). *Artificial Intelligence: A Guide for Thinking Humans.* New York: Farrar, Straus and Giroux.
- Mitchell, M. (2024). Debates on the Nature of Artificial General Intelligence. *Science*, 383(6689), eado7069. https://doi.org/10.1126/science.ado7069.
- Narayanan, A., & Kapoor, S. (2024). *AI Snake Oil: What Artificial Intelligence Can Do, What It Can't, and How to Tell the Difference.* Princeton: Princeton University Press.
- Russell, S., & Norvig, P. (2021). *Artificial Intelligence: A Modern Approach* (4th ed.). Pearson.
- Searle, J. R. (1980). Minds, Brains, and Programs. *Behavioral and Brain Sciences*, 3(3), 417–457. https://doi.org/10.1017/S0140525X00005756.
- Shanahan, M. (2024). Talking About Large Language Models. *Communications of the ACM*, 67(2), 68–79. https://doi.org/10.1145/3624724.
- Suchman, L. (2023). The Uncontroversial "Thingness" of AI. *Big Data & Society*, 10(2). https://doi.org/10.1177/20539517231206794.
- Zaharia, M., Khattab, O., Chen, L., Davis, J. Q., Miller, H., Potts, C., Zou, J., Carbin, M., Frankle, J., Rao, N., & Ghodsi, A. (2024). The Shift from Models to Compound AI Systems. *Berkeley AI Research Blog (BAIR)*, February 18, 2024. Accessed April 2026.
