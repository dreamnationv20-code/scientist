# From research agents to autonomous scientific programmes

**Anonymous authors**

## Abstract

Research agents can retrieve literature, generate hypotheses, run code and prepare manuscripts, yet they often cease to be autonomous at the transitions that determine a research programme. A person reconstructs state after interruption, decides whether a failure is technical or scientific, chooses the next causal representation, or judges whether evidence warrants a claim. We define **autonomy closure** as the ability of a research system to carry a human-specified objective through goal selection, discovery, prospective testing, recovery and evidence-governed resolution without unrecorded scientific intervention. We implement six closure conditions: an evolving causal goal graph, information-controlled search, prospective evidence rules, typed recovery, independent claim authority and replayable scientific state. A model-independent kernel controls state transitions while replaceable models and tools retain proposal authority. The reference discovery policy isolates incremental, de novo and delayed-hybrid search before common evaluation. A frozen implementation audit exercises 151 targeted controls. In two committed development panels, the system remained operational across null, ambiguous, nonlinear and fault-injected research worlds and made no false promotions; these panels are excluded from confirmatory inference. We specify two prospective tests: a frozen matched-model experiment that isolates claim and recovery authority, and a separate end-to-end study of autonomy closure on unseen research objectives. The resulting framework makes autonomous science a falsifiable property of a complete research programme rather than a label attached to an agent that automates selected steps.

## Research agents do not yet close research programmes

Systems described as AI scientists now automate a substantial part of computational research. They formulate hypotheses, retrieve evidence, write programs, operate simulators, compare candidates and produce manuscripts [1-9]. The AI Scientist demonstrates an end-to-end path from idea generation to paper production [1,2]. Google’s Co-Scientist coordinates specialized generation, reflection, ranking, evolution, proximity and meta-review agents to improve research proposals [4]. Other systems emphasize empirical software, benchmark replication, sequential falsification or verifiable chains of evidence [5-9]. These results establish that language models can coordinate demanding scientific work.

They do not establish that a system can govern a research programme after its initial task has been specified. The difficult failures often occur between otherwise competent steps. A local experiment succeeds but does not answer the parent question. A null result triggers another variation of an exhausted idea. A restart restores the conversation but loses which assumptions were rejected. A model proposes an experiment, interprets its output and decides that its own stopping rule has been satisfied. In our development history, the autonomous system progressed reliably until such transitions required Codex or a human to reconstruct state, revise the goal or authorize the next experiment. The missing capability was not another proposal generator. It was closure of the decisions that connect proposals into a defensible programme.

We use **autonomy closure** for this systems-level property. Given a root objective, admissible resources and stopping conditions, a closed system can determine which subproblem is live, choose among competing causal decompositions, run prospective tests, recover or stop according to the meaning of a failure, integrate local evidence upward and emit a bounded terminal conclusion. Every scientific intervention must either occur through the declared interface or appear in the permanent record. A request for genuinely unavailable authority is a valid terminal dependency; silent human repair is not.

Autonomy closure is distinct from task completion. A system may complete many assigned experiments while depending on a person to select the next scientific target. It is also distinct from scientific advantage. A closed system could autonomously reach poor conclusions. We therefore separate two empirical questions. The first asks whether the system reaches valid terminal states without out-of-band scientific intervention. The second asks whether it produces more valid scientific progress than the same model operating as a matched standalone research agent. Closure is a prerequisite for the stronger claim, not evidence for it.

## Six conditions for autonomy closure

We operationalize closure through six conditions. **Goal closure** requires the system to translate a root objective into falsifiable leaves and to revise its decomposition without losing the parent decision. **Search closure** requires it to originate and compare materially different candidate mechanisms without allowing one lineage to determine every alternative. **Epistemic closure** requires questions, predictions, admissible evidence and decision rules to be fixed before target outcomes are exposed. **Recovery closure** requires failures to cause class-specific retry, repair, amendment, recalibration, theory update or representation change. **Claim closure** requires proposal, validation and promotion authority to remain separate. **Operational closure** requires the full scientific state, resource use and external effects to survive interruption and exact replay.

These conditions define observable failure tests rather than aspirations. A programme lacks goal closure if a human must choose its successor mission. It lacks search closure if a purported alternative inherits the incumbent mechanism through an unrecorded channel. It lacks epistemic closure if the success rule changes after the result. It lacks recovery closure if every failure produces generic retry. It lacks claim closure if the candidate can waive its own validation. It lacks operational closure if a restart changes the evidence, budget or set of completed actions. End-to-end closure requires all six because a gap in any one condition returns scientific control to an unrecorded external actor.

## Architecture for autonomy closure

The architecture connects programme reasoning, executable scientific leaves and evidence authority (Fig. 1). A human supplies the root objective, metric, resource budget and stopping conditions. A programme manager maintains an evolving AND/OR goal graph rather than a fixed task list. It selects a falsifiable executable leaf, assigns a finite campaign budget and records how the leaf could change its parent decision. The leaf follows a prospective scientific lifecycle and dispatches replaceable models, agents, instruments or deterministic workers.

The Autonomous Research Kernel sits outside the proposal model. It checks the actor's jurisdiction, information exposure, resource use, artifact schema and evidence references. An action first executes against a disposable copy of state. The kernel commits the transition only when the resulting trace satisfies the action contract. A malformed artifact, an over-budget tool call or an uncertified interpretation leaves canonical state unchanged. The same rule governs upward integration: local success does not resolve a parent unless the registered parent experiment passes.

This allocation separates adaptive intelligence from scientific authority. Models remain responsible for open-ended work such as explanation, analogy, experiment proposals, code and interpretation. The kernel performs narrower operations: preserving the mission, admitting plans, controlling information exposure, validating cited evidence, classifying failure, enforcing budgets and authorizing promotion. A Co-Scientist-style coalition, evolutionary search or another research-agent system can operate inside a discovery channel without acquiring permission to certify its own output.

[[FIGURE_1]]

## Goal closure through an evolving causal graph

The outer control structure is a directed acyclic AND/OR graph. Parent rules state whether resolution requires all children, any one alternative, a minimum number of children or a complementary Pareto set. Typed edges state whether one result requires, supports or invalidates another. A node may participate in several decompositions, but each incoming edge has its own integration test. The graph therefore represents scientific dependence rather than execution order.

Decomposition stops at an executable leaf contract. A valid leaf names a falsifiable hypothesis, the parent decision that its result could change, the root metric, success and falsification conditions, a testbed, an integration rule and a finite budget. An inexpensive experiment with no declared consequence for its parent is inadmissible. After local evaluation, the frozen candidate enters the parent experiment. Failure may return the leaf to search or kill the branch; success contributes evidence to the parent's composition rule. Root resolution is derived from registered child evidence rather than from a model's narrative summary of progress.

The programme manager can maintain competing decompositions while evidence remains incomplete. Budget allocation uses registered uncertainty, dependency position, remaining cost and prospective value. Revision creates a successor rule while preserving the superseded decomposition and its evidence. A negative result can therefore change the causal account without erasing why the earlier account failed. This is the mechanism by which a programme moves beyond a sequence of local tasks.

## Search closure through isolated discovery

The implemented reference policy uses three discovery channels for an executable leaf. Incremental ancestry receives the incumbent implementation, rationale, error traces and dead-idea history. De novo search receives the problem contract, closed literature facts and novelty exclusions, but not incumbent code, mechanisms or ancestry. A delayed-hybrid channel opens after an isolation period and receives selected survivors from both channels. Hybrid candidates must demonstrate behavioral use of both parents on different diagnostic states.

Every proposal records its channel, ancestry, literature context and information exposure. The control plane rejects de novo candidates that saw incumbent mechanisms, incremental candidates without ancestry, hybrids created before the exchange boundary and cross-channel lineage laundering. Channel identity supplies no novelty bonus or evaluation advantage. All finalists face the same semantic, behavioral, replication and parent-integration tests under matched budgets.

This three-channel portfolio is a reference strategy, not a claim that every domain has exactly three useful modes of discovery. A domain pack may substitute theorem families, experimental platforms or other problem-specific channels. The universal requirement is controlled diversity: the system must state what each search process knew, prevent a single incumbent from defining every alternative and compare survivors under common authority.

## Epistemic and claim closure

Each executable leaf advances through twelve prospective stages: mission definition, prior-art closure, incumbent reproduction, phenomenon mapping, causal diagnosis, concept invention, prospective concept validation, discriminating experiment design, mechanism compilation, multi-horizon evaluation, programme decision and terminal reporting. A proposed explanation begins as a diagnostic concept. It must predict disjoint cases before solution synthesis. A compiled intervention must introduce a new executable primitive, differ behaviorally from the strongest incumbent and preserve the declared fallback. A claimed improvement must then survive independent, oracle-free evaluation across the registered horizons.

Prospective artifacts connect these stages. An experiment records the competing mechanisms, predicted outcomes, decision rule, cost and held-out partition before target outcomes become available. The public validator checks identifiability, evidence coverage, contradictions and resource integrity without reading hidden task truth. The promotion authority can issue advance, supported null, justified abstention, kill or reframe only when the cited evidence satisfies the applicable certificate. Correct guesses without evidence do not change scientific state.

The distinction between proposal and authority applies recursively. A model may propose a goal decomposition, but graph policy determines whether it is admissible. It may propose an experiment, but the design validator determines whether the experiment discriminates among live alternatives. It may interpret a result, but a separate evidence path determines whether the claim is supported. Additional reflection can improve a proposal, but reflection by the same actor does not substitute for independent jurisdiction.

## Recovery and operational closure

The meaning of a failed step determines the next scientific action. A network interruption may permit exact retry. A malformed interface may permit bounded repair without changing the hypothesis. A protocol defect requires a prospective amendment. Weak measurement may permit recalibration or a different instrument. A genuine null updates the causal account. Exhaustion of an intervention family requires a materially different representation rather than another nominal variant of the same test.

The kernel encodes these cases as typed failures: external dependency, infrastructure, implementation, interface, protocol, measurement, scientific null and representation exhaustion. Each class has a bounded transition authority. Repeated local repair cannot become an indefinite series of renamed milestones. A terminated branch and the reason for termination remain in causal memory.

Two linked records make these rules durable. A hash-chained authority ledger records the active action, actor, jurisdiction, model and tool calls, input and output artifact identities, resource charges, human interventions and resulting state transition. Causal memory stores hypotheses, assumptions, prospective predictions, contradictions, representation signatures, experiment fingerprints, exhausted intervention families and evidence status. Semantically equivalent experiments are blocked after their intervention family is exhausted unless the representation, target contrast or evidence channel changes materially.

Interruption is represented as a scientific event. Each expected unit of external work has an immutable receipt. On restart, completed units are rediscovered, only pending units are reissued and aggregate usage is reconstructed from receipts. A changed response for an already completed unit is rejected. An external invocation without a corresponding state commit remains visible as an orphaned effect and enters failure adjudication. Exact replay therefore restores the scientific boundary, not merely the conversation.

During development, a proposed concept intended to predict whether additional computation would repair a reasoning failure performed above chance but below the frozen incumbent and failed its prospective gate. The kernel preserved the result, killed the branch and withheld promotion. A succession controller then used the failed certificate, unchanged root objective and causal memory to produce materially different successor missions. Proposal-only reviewers assessed novelty and methodological validity, and a deterministic controller selected the sole eligible mission. This episode does not establish scientific superiority, but it demonstrates the intended transition from failed representation to explicit successor without retrospective repair of the parent claim.

## Development qualification

We evaluated whether the integrated architecture remained operational under conditions designed to expose false certainty, state loss and inappropriate retry. The development environment contains finite causal decision worlds with public candidate hypotheses and private generating authority. Tasks include signed moderation, two-variable interactions, three-variable rules, genuine nulls and cases that remain underdetermined within the measurement budget. Faults include retryable infrastructure errors, malformed observations, permanently unavailable actions, invalid requests and measurement ambiguity. A deterministic scorer evaluates the immutable terminal record.

In a prospectively committed 18-task development panel, the authority-separated system produced 13 valid root advances (72.2%). The same model with an equivalent scientific-method prompt produced 7 of 18 (38.9%), and the free monolithic model produced 6 of 18 (33.3%). Across the 54 arm episodes, no arm made a false promotion. A deliberately uninformed policy remained below 10%, an answer-aware reference policy exceeded 95%, and the monolithic controls were neither at floor nor ceiling. Every scientific state contained both a success and a failure among the non-oracle arms.

After the final recovery, runtime and transport components were installed, a separately committed six-task regression panel produced valid advances on 6 of 6 authority-separated runs, 4 of 6 prompt-equated runs and 3 of 6 free-model runs. No run ended in an unhandled runner exception and no arm falsely promoted a claim. The retained development history includes implementation and interface defects, including an experimental plan that made two causal candidates observationally identical and an adjudicator that compared the wrong source sets. These defects were corrected before freeze and remain visible in the audit record.

These numerical differences are not treatment-effect estimates. The tasks informed implementation and are permanently excluded from the confirmatory namespace. They show that the assay has operating range, that null and ambiguity outcomes can be scored, that the integrated loop remained live after its final extensions and that failure evidence was retained. The implementation is frozen under a content identity that binds generators, prompts, schemas, tools, recovery policy, scorers, statistical programs and development evidence. A clean automated replay reproduces the qualifications and passes 151 targeted tests.

[[FIGURE_2]]

## Prospective test of separated scientific authority

The first confirmatory study isolates claim and recovery authority within the larger architecture. Each unseen task will run in three arms. A free monolithic model controls its experiment sequence, optional validation, recovery and terminal certification. A prompt-equated monolithic model receives the same methodological obligations enforced by the kernel but decides for itself whether those obligations were met. The authority-separated system uses the same foundation model for proposals while external components own state, plan admissibility, evidence validation, recovery and promotion. All arms receive byte-identical public tasks, tools and output schemas and are matched on model snapshot, reasoning effort, token ceiling, wall time and attempted-measurement budget.

The primary outcome is valid root advance within budget. A positive claim counts only if the exact hypothesis and held-out intervention policy are correct, every evidence reference exists, every failure has the required disposition and all resource accounting reconciles. A supported null and a justified abstention under irreducible ambiguity also count as advances. This definition prevents a conservative system from winning by refusing to answer and prevents an unsupported correct label from being counted as scientific progress.

The primary panel contains 180 matched tasks and 540 model episodes balanced across scientific states, structural complexity and fault class. Hidden task authority remains with an independent provider until all three terminal records in a matched block are immutable. The prespecified analysis estimates paired valid-advance differences using exact McNemar tests, stratified paired bootstrap intervals and multiplicity correction. Mechanistic panels separately remove causal memory, plan admissibility, candidate validation, typed recovery and independent promotion. Transport and independent replication occur only after the preceding gates pass.

This frozen study tests whether enforceable authority improves decisions under a matched model and budget. It does not isolate the value of the goal graph or the reference discovery portfolio, and it does not by itself establish end-to-end autonomy closure. The independent pre-execution audit therefore authorizes only this bounded experiment.

## Prospective test of end to end autonomy closure

A separate study will test the complete programme on broad, previously unseen research objectives. It will be preregistered and frozen before task provision. Each episode begins with a root objective, measurable success criterion, resource envelope, admissible domain instruments and stop conditions. The system must choose and revise subgoals, conduct discovery, design and execute tests, integrate local findings and issue a defensible terminal boundary. No person or external model may supply unregistered scientific decisions after launch. Requests for legitimate external authority are recorded and scored according to the episode contract.

The primary comparison is between the complete Scientist and a persistent standalone research agent instantiated with the same foundation model, public information, tools, token budget, wall time and evaluator access. A prompt-equated standalone arm will receive the same scientific obligations in natural language. Historical Codex-assisted campaigns will provide a descriptive process baseline, with human and Codex intervention minutes counted explicitly, but will not substitute for randomized prospective controls.

The primary endpoint is independently validated root advance within budget and without out-of-band scientific intervention. Secondary endpoints include false promotion, unsupported claims, exact resume after interruption, correct failure disposition, repeated-equivalent experiments, orphaned effects, human intervention time, information gain, total cost and time to resolution. Blinded evaluators will judge whether each terminal conclusion changes the registered root state and whether every supporting artifact exists. Activity, manuscript production and locally improved metrics do not count unless they satisfy the parent integration rule.

Targeted ablations will remove the evolving goal graph, controlled search diversity, causal memory, typed recovery or independent claim authority one at a time. The full system must outperform the matched standalone agent on the preregistered primary endpoint, preserve false-promotion safety and require no out-of-band intervention in at least 90% of episodes. The planned broad scientific-advantage claim additionally requires a positive confidence interval, an improvement of at least 15 percentage points, no negative domain-level point estimate and an independent replication in a disjoint task set. If only individual mechanisms improve reliability or recovery, the claim will be narrowed to those mechanisms.

The evaluation will combine fresh generated causal worlds with prospective computational research in distinct domains, initially formal compiler optimization, database or systems optimization and small-model learning or tool-use mechanisms. Domain packs may change instruments and local validators but cannot alter the universal kernel, memory semantics, recovery policy or promotion rules after outcomes are exposed. Results will be reported by domain before any pooled estimate.

## Current evidence boundary

Figure 2 separates completed development evidence from the claims that remain prospective. The present evidence supports implementation readiness, replayability and assay operation. It does not support a causal advantage for separated authority, an end-to-end autonomy advantage, cross-domain generality or superiority to Codex. Those claims require, in order, a passed independent audit, the frozen matched study, mechanism and transport tests, the separately frozen autonomy-closure study and independent replication.

This ordering prevents a successful later result from repairing a failed earlier gate. A failed audit requires a new identified freeze. Failure of the matched authority experiment limits the architecture claim even if selected naturalistic cases look successful. Failure of the end-to-end comparison permits component-level or case-study conclusions but not a general claim of autonomous scientific advantage. Failure of replication blocks the broad Nature claim.

The evidence boundary is also an architectural requirement. The manuscript compiler may promote positive causal language only when the deterministic evidence integrator identifies the required artifacts and returns the corresponding authorization. Before that point, architecture, development behavior and prospective hypotheses must remain grammatically distinct from confirmed effects.

## Discussion

Autonomous science is often evaluated through the quality of a final answer, code artifact or manuscript. Those outcomes can conceal who selected the decisive experiment, repaired the state after interruption or waived a failed validation. Autonomy closure moves the unit of analysis from an isolated agent action to the complete chain from root objective to evidence-authorized resolution. It also makes negative outcomes meaningful: a supported null, justified abstention or correctly killed representation can advance a programme when the result constrains the next decision.

The architecture does not assume that deterministic control can replace scientific judgment. Models and domain workers remain necessary for explanation, analogy, invention and interpretation. The claim is narrower: generative judgment should alter canonical scientific state only through explicit interfaces whose authority, evidence and resource effects can be audited. The goal graph, discovery channels and lifecycle organize where generative work occurs; the kernel determines whether it changes the programme.

Several limitations remain. The development worlds are deliberately finite and cannot represent the open texture of laboratory science. The three-channel search strategy may not fit every domain. Formal separation of authority may add cost or reject unconventional but valuable evidence. Objective scoring is easier in computational domains than in fields that depend on slow, contested or embodied measurements. Most importantly, the confirmatory data do not yet exist. The architecture should be judged by the prospective comparisons and downgrade rules reported here, not by the development effect sizes.

If the programme succeeds, the contribution will be evidence that scientific autonomy depends on the composition of goal selection, search, evidence, recovery, claims and state, even when the underlying model remains fixed. If it fails, the same design will locate which closure conditions do not improve scientific outcomes and where human authority remains necessary. Either result replaces an ambiguous claim of agent autonomy with a testable account of who controls the research programme.

## Methods

### Kernel and transaction semantics

The Autonomous Research Kernel owns canonical episode state. Actions declare an actor, authority scope, input artifact identities, output schema, resource ceiling, allowed information exposure and transition predicate. Execution occurs against a copy-on-write state. The kernel commits only after schema, evidence, policy and accounting checks pass. Failed transactions leave canonical state unchanged but append a typed failure record and any observable external effect. Content hashes bind artifacts, transition records and prospective commitments.

Model outputs are untrusted proposals. Model and deterministic workers use the same typed exchange: request identity, visible artifact list, allowed tools, budget, expected output schema and receipt policy. Jurisdiction is capability-specific. A proposal actor cannot call promotion operations; a validator cannot generate the candidate it judges; an independent task provider cannot modify public terminal records.

### Goal graph representation

Goal nodes contain the scientific question, parent consequence, root metric, live hypotheses, uncertainty, budget, terminal conditions and evidence state. Edge records contain relation type, composition rule and integration-test identity. Expansion requires at least one falsifiable leaf whose possible outcomes change a parent decision. Revision appends a successor decomposition and preserves the prior graph. Root status is computed from registered edges and certificates rather than assigned by a free-form model output.

### Scientific lifecycle

Mission definition fixes the root objective, metric, constraints and terminal uncertainty. Prior-art closure records the search protocol and establishes that named comparators were obtained or genuinely unavailable. Incumbent reproduction verifies executable parity within tolerance. Phenomenon mapping requires counterfactual contrasts across regimes and horizons. Causal diagnosis must cover each failure cluster with replay-supported models. Concept invention proposes a measurable variable with prospective discriminating predictions. Concept validation tests disjoint cases before solution synthesis.

Experiment design records competing mechanisms, predicted outcomes, decision rules, cost and held-out partitions before target outcomes are exposed. Mechanism compilation requires a new executable primitive, non-collapse relative to the incumbent and parity of the fallback path. Multi-horizon evaluation is independent, oracle-free and full-trajectory. Programme decision permits continue, repair, kill, reframe or promote only from registered evidence. Terminal reporting derives its claim boundary from knowledge records rather than from the proposal transcript.

### Discovery channel controls

Each proposal carries a lineage manifest containing its discovery channel, visible artifacts, ancestry hashes and exchange time. Incremental proposals must identify incumbent ancestry. De novo proposals fail admission if their context includes incumbent mechanisms or derived representations. Hybrid proposals are unavailable before the registered exchange boundary and must identify survivors from both permitted parent channels. Finalists receive identical validation and integration tests. Domain-specific channel substitutions must publish equivalent exposure and comparison contracts before execution.

### Causal memory and experiment equivalence

Causal memory records each hypothesis, assumptions, prospective predictions, contradictions, evidence references, intervention family, representation signature and status. Experiment fingerprints identify repeated tests at the level of scientific contrast rather than command string. Equivalent experiments are blocked after their intervention family is exhausted under a fixed representation. A new attempt becomes admissible when it changes the relevant representation, target contrast or evidence channel and states the expected discriminating observation.

### Failure adjudication

Failures are classified in dependency-to-science order. External dependency requests outside authority. Infrastructure permits exact retry. Implementation and interface faults permit bounded repair of code or schema without altering the scientific target. Protocol faults require an identified prospective amendment. Measurement faults permit recalibration or an alternate instrument. Scientific null updates the causal theory. Representation exhaustion requires a materially different representation. Attempts, failures and repairs remain in the ledger and are charged to the episode. Missing or invalid terminal episodes are scored as failures in evaluation.

### Development worlds and outcome

Each development task is a finite causal decision world with binary public context variables, named interventions, bounded noisy observations and a public set of executable candidate policies. Private authority fixes the generating hypothesis or null state, nuisance parameters, fault schedule and held-out contexts. The shared public validator checks design coverage, empirical contradiction, ambiguity, prediction completeness and resource integrity without accessing the hidden generating identity.

Valid root advance equals one when an episode promotes the exact generating hypothesis with correct held-out intervention predictions, kills a genuine null with the required equivalence evidence, or abstains in an underdetermined world with a valid ambiguity certificate. Every cited observation must exist in the immutable trace; failure dispositions and resource accounts must reconcile. A correct label without these conditions equals zero. False promotion is any unsupported positive terminal claim.

### Development panels

Task specifications, seeds and arm order were committed before model calls. Every task was run once in three matched arms. The 18-task qualification panel crossed five scientific states, structural widths and fault types. The six-task post-extension panel was separately committed after the final runtime changes and before its outcomes. Both carry explicit development-only and permanently-excluded markers. Neither contributes to confirmatory effect estimation or threshold selection.

### Frozen matched study

The confirmatory panel contains 180 task triples. All arms use `gpt-5.6-sol` with low reasoning effort, a maximum of 128,000 input-plus-output tokens including cached tokens, a 900-second wall-time ceiling, no more than three probe batches and tier-specific ceilings of 24, 30 or 36 attempted measurements. The public task, schema and tool surface are byte-identical. Hidden authority opens only after all three terminal records are immutable. An interrupted matched block cannot be selectively rerun.

The primary estimand is the paired valid-root-advance difference between the authority-separated system and prompt-equated monolithic model. The free-model contrast is key secondary. Analysis uses exact two-sided McNemar tests, 100,000 paired bootstrap samples stratified by scientific state, structural width and fault class, simultaneous intervals and Holm adjustment. The analysis rejects a panel that does not contain the exact crossed design.

### Mechanism transport and replication

Five frozen ablations independently remove causal memory, plan admissibility, candidate validation, typed recovery or independent promotion on an outcome-blind 90-task subset. A component is supported only if its removal attenuates valid advance and increases its declared target failure. Thirty CausaLab tasks test non-degradation in a distinct causal environment. A separate provider and execution site generate a disjoint 180-task replication. The final evidence integrator requires identified artifacts from every stage and returns the Boolean authorization used by the manuscript compiler.

The end-to-end autonomy-closure evaluation is a separate prospective extension. Its task identities, primary endpoint, intervention-accounting rules, ablations and success gates will be committed before any provider generates an eligible task or authority. It cannot modify the estimand, analysis or claim boundary of the frozen matched study.

### Implementation freeze and software tests

The implementation freeze binds source files, prompts, schemas, protocols, development manifests and statistical programs by SHA-256. Its identity is `27a53ce49129ca44dd45f1120241b5b7e7c4674759f95666ec714c42e0bdce95`. An automated clean replay checks source and protocol hashes, verifies that confirmatory namespaces do not exist, reproduces the adaptive and CausaLab qualifications and executes 151 targeted tests. Independent human audit remains required to establish answer separation, resource matching, interruption semantics, statistical fidelity, ablation isolation and provider sequestration.

### Language model use

Language models generated proposals in the system and control arms and are the substrate being evaluated. Codex assisted the authors with implementation and manuscript preparation. The human authors are responsible for study design, verification, interpretation and final text.

### Data and code availability

The frozen source, dependency lockfile, development manifests, protocols and audit instructions are included in the independent-audit archive. Confirmatory public tasks, trajectories, scores, private authorities and analysis manifests will be deposited after completion of the matched and replication studies. No confirmatory task authority or outcome exists at the time of this manuscript. The separate end-to-end evaluation will receive a new preregistration and content identity before task provision.

## References

1. Lu, C. et al. Towards end-to-end automation of AI research. *Nature* **651**, 914-919 (2026).
2. Yamada, Y. et al. The AI Scientist-v2: Workshop-level automated scientific discovery via agentic tree search. *arXiv* 2504.08066 (2025).
3. Schmidgall, S. et al. Agent Laboratory: Using LLM agents as research assistants. *arXiv* 2501.04227 (2025).
4. Gottweis, J. et al. Accelerating scientific discovery with Co-Scientist. *Nature* **655**, 487-496 (2026).
5. Meng, R. et al. ScientistOne: Towards human-level autonomous research via chain-of-evidence. *arXiv* 2605.26340 (2026).
6. Huang, K. et al. POPPER: Automated hypothesis validation with agentic sequential falsification. *Proceedings of the International Conference on Machine Learning* (2025).
7. Chen, J. et al. ScienceAgentBench: Toward rigorous assessment of language agents for data-driven scientific discovery. *International Conference on Learning Representations* (2025).
8. Starace, G. et al. PaperBench: Evaluating AI's ability to replicate AI research. OpenAI (2025).
9. OpenAI. MLE-bench: Evaluating machine learning agents on machine learning engineering. *arXiv* 2410.07095 (2024).
10. Wilkinson, M. D. et al. The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data* **3**, 160018 (2016).
11. Moreau, L. & Missier, P. PROV-DM: The PROV Data Model. W3C Recommendation (2013).
12. Nosek, B. A., Ebersole, C. R., DeHaven, A. C. & Mellor, D. T. The preregistration revolution. *Proceedings of the National Academy of Sciences USA* **115**, 2600-2606 (2018).

## Figure legends

**Figure 1 | Architecture for autonomy closure.** **a**, Goal closure converts a root objective into an evolving AND/OR graph and integrates evidence through parent-specific tests. **b**, Epistemic closure advances each leaf through prospective framing, explanation, testing and decision. **c**, Search closure separates incremental ancestry, de novo and delayed-hybrid discovery through registered information boundaries. **d**, Model-independent authority supplies recovery and claim closure by controlling admissibility, evidence, failure disposition and promotion. **e**, Operational closure uses a hash-chained ledger and causal memory to preserve state across interruption. Replaceable workers and domain instruments may propose actions but cannot certify them; an independent provider retains hidden task authority until matched terminal records are immutable.

**Figure 2 | Development qualification and prospective evidence boundary.** **a**, Valid-root-advance rates in the committed 18-task development panel. **b**, Corresponding rates in the separately committed six-task post-extension regression. Counts appear above bars. **c**, The completed controls establish assay operation and implementation readiness but do not estimate a confirmatory treatment effect. **d**, Evidence sequence from development through independent audit, the frozen matched authority study, mechanism and transport tests, the separately frozen end-to-end closure study, replication and deterministic claim integration. Both development panels are permanently excluded from confirmation.
