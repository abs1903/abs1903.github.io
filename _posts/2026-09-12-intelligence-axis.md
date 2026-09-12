---
title: "The Age of the Intelligence Axis"
excerpt: "LLMs may be less a talking dispatch layer and more the accumulating core of cognition itself — a proposal for how to think about 'intelligence content,' what embodiment actually adds, and how this reframes how we judge research."
permalink: /posts/2026/09/intelligence-axis/
tags:
  - AI
  - LLM
  - research
header:
  teaser: ""
---

The pace of recent progress in large language models — and the potential it keeps revealing — keeps challenging what researchers, and frankly everyone else, thought we knew about intelligence.

From millennium-prize-level mathematics to manipulating robotic arms, these systems display a range that would have sounded absurd a decade ago.

This post argues a simple point: **the LLM has become the central embodiment of what I will call the intelligence axis.**

That claim immediately raises several questions that need to be discussed before it can be taken seriously: What exactly is "intelligence content"? Why might a language model carry it? What do embodiment and world models actually add? And how does the *power* of accumulated intelligence determine model behavior?

## 1. "Intelligence Content"

Imagine ten different intelligent systems: one writes programs, one operates a browser, one organizes research materials, one controls a robot, and the rest fan out into other domains.

If they all depend on the same base model, have we gained ten implementations of one and the same set of cognitive abilities?

Suppose a robot learns to execute complex instructions, where the knowledge about object affordances, task ordering, and conditional constraints comes mostly from the underlying model, and the new training mainly solves visual grounding, action output, and execution calibration. That progress is real — but it is closer to *extending the reach of existing intelligence* than to *creating an equal amount of cognition from scratch*.

Conversely, if the robot discovers, through interaction, regularities the base model did not know, and turns them into methods that transfer to other tasks, then it is not merely a *consumer* of intelligence. It has become a new *source* of it.

So the question this post really cares about is:

> Of the capabilities a system exhibits, which are inherited, which are invoked, and which are newly learned?

Answering it requires identifying the component where cognitive ability primarily accumulates.

Here is the trap to avoid. Cut the power and the robot stops working; remove its sensors and it loses perception; break the communication protocol and it may fail to execute any instruction at all. But no one would conclude that the battery, the sensors, and the protocol each carry *all* of the intelligence.

By the same logic, the fact that a system fails when you remove a large model does not prove the model carries the bulk of the intelligence. It might merely be an unavoidable dispatch node.

**Necessity is not cognitive content, and sitting at the center of the call chain is not the same as sitting at the center of the knowledge structure.**

What the "intelligence axis" is about is precisely the latter: the center of the knowledge structure.

## 2. Language Carries Learning That Humans Have Already Completed

This is a well-worn observation, but it deserves a brief restatement.

A substantial part of language data is not a raw record of the world; it is the *residue of humans having already learned from the world*.

Picture two kinds of material. One is a massive corpus of video of objects moving. The other is what people wrote down after observing, experimenting, and failing: the regularities they extracted, along with applicability conditions, procedures, and counterexamples.

The former preserves rich physical detail. The latter discards most detail, yet may directly supply the *structure* needed for action. It tells a later learner: you do not need to repeat every trial-and-error yourself — you can start from where prior learning ended.

From this angle, language can be understood as a lossy, purpose-oriented encoding that has passed through human cognition. It loses touch, continuous motion, and concrete context; it keeps certain context-independent regularities.

This is why I suspect LLMs have high "intelligence density": what they are exposed to is not only *what happened*, but also humanity's distilled *why* and *how*.

Foundation-model research already treats "large-scale learning with cross-task adaptation" as a defining feature of these models [1], and there is a concrete technical link between language modeling and compression [2]. But "can compress data" does not automatically equal "carries broadly usable cognitive ability" — that step needs an additional argument.

The core of intelligence content is whether the model has organized scattered knowledge into a structure that can be *combined, transferred, and invoked* — the machine equivalent of 举一反三, extrapolating from one case to many.

A book that contains the solution to a problem, and a system that can select, adapt, and execute that solution under new conditions, are not the same thing.

So "the LLM is the carrier of intelligence content" should *not* be read as "it is a very large encyclopedia." The more precise claim is: it may have accumulated both the knowledge itself *and* the ability to reorganize that knowledge across problems.

My working hypothesis: for the LLM — and its agent form — as the intelligence axis, there may be no fundamental per-domain trade-off at all. Any kind of "intelligence" can enter the LLM in linguistic form and be put to use.

## 3. In Embodiment: General Knowledge, Current State, and Action

"Knowing how to operate" is at least three different things.

**General knowledge**: to achieve the goal, what steps are usually needed? Which conditions are necessary? Which behaviors tend to cause failure?

**Current state**: where is the object right now? Is the door open or closed? Which corridor did the robot just search? Is the cup about to tip over?

**Action implementation**: what motor commands should *this* body emit? How to handle error? How to correct mid-execution?

The first kind of knowledge transfers across environments. The second and third are tightly coupled to the current situation, the body, and feedback.

Take navigation. "When you cannot find the target, check unexplored areas" is a reusable strategy. But "the left corridor has already been checked" is experience from this particular episode, and "moving forward now would hit an obstacle" requires judging the current state.

A language model has never been inside this building, so it cannot know from nothing that a particular door was just closed. But that ignorance must not be misread as a lack of general exploration and planning ability.

Conversely, being able to *state* exploration principles does not prove the model possesses *executable* navigation competence. It may fail to maintain state, resolve ambiguity, or select correct actions within the time budget.

SayCan demonstrated one explicit division of labor: the language model supplies high-level semantic knowledge, while an affordance (skill-value) function constrains actions to what is feasible in the specific environment [3]. RT-2 explored another path: transferring capabilities from web pretraining into robot control through a vision-language-action model [4]. Both lines support the possibility that *existing* capabilities can enter physical tasks; neither proves that *all* capabilities physical tasks require already live in the language model.

Embodied learning therefore splits into two kinds of increments: some of it adds *new* cognitive ability, and some of it merely supplies the state, coordinates, actions, and feedback that *existing* cognitive ability needs in order to take effect.

Both can be extremely difficult. They should not be booked as the same kind of progress.

## 4. Kolmogorov Complexity and Intelligence Content

To keep "intelligence content" from being a mere rhetorical flourish, it helps to attempt a definition grounded in Kolmogorov complexity.

Fix a universal computational language. The complexity of a string $$x$$ is

$$K(x) = \min_{p:\,U(p)=x} |p|,$$

the length of the shortest program that generates $$x$$. The conditional complexity

$$K(x \mid y) = \min_{p:\,U(p,y)=x} |p|$$

measures how much additional description is needed to obtain $$x$$ once you already have $$y$$.

But information-rich does not mean intelligence-rich. What we actually care about is *useful structure*: which problems does it apply to, how much additional learning does it remove, and can it be invoked under realistic resource constraints?

Kolmogorov complexity is a good language for *posing* the question — but it is not adequate for *measuring* intelligence content. The question must shift from "how complex is the model itself" to:

> Given the model, how much *extra* structure is still needed to solve a set of new problems?

## 5. Information That Exists Is Not Information That Is Available

If we only ever discuss shortest descriptions under unbounded computation, then many cognitive advances we consider deeply important collapse into "computing the result from rules already present."

What is the difference between knowing a set of axioms and finding the crucial proof? Between knowing the rules of a finite game and being a strong player?

From a purely computability-theoretic viewpoint, the latter is already implicit in the former. But for an agent with finite time, memory, and compute, the difference can be enormous.

**Implicitly derivable does not mean actually accessible.**

The same applies to "all the operational knowledge is in the text." Even if the knowledge really is present in the training material, that does not mean the model learned it. Even if the structure has entered the parameters, that does not mean the model can invoke it correctly within the budget a task allows.

So we need to distinguish at least three layers: whether the information *exists* logically; whether the system *learned* the corresponding structure; and whether that structure can be *converted into reliable behavior* within a given budget.

The 2026 work on *Epiplexity* starts from computationally bounded observers, formalizes the *learnable structural* information in data, and separates it from random, unpredictable content [5]. It is an important reminder: evaluating data and learning outcomes from the vantage point of an infinite-compute observer is a category error.

Following this thread: training is not merely the transport of information. It can also convert results that were previously hard to obtain into structures that are cheap to invoke. Reasoning, search, and self-play may play a similar role: even without new external observations, they can generate new, *practically accessible* capability.

So I will not equate "no new external information" with "no cognitive progress."

Intelligence advances in two ways: by learning facts one did not know, and by finally being able to *use* knowledge one could not use before.

This is exactly why intelligence content must carry a compute budget. It cannot be discussed as a static quantity of stored information.

## 6. A Tentative Definition

Following the discussion above, here is a tentative definition.

Fix a program language, a public background $$y$$, and an interaction protocol. Define the *intelligence content* of a model $$M$$ with respect to a target capability as its **residual implementation cost spectrum**:

$$C_{\mathcal{E}}(f \mid M) \;=\; \inf_{\pi}\; \Big\{ \mathrm{cost}(\pi) \;:\; d\big(\,\mathcal{D}_f^{\,\mathcal{E}},\; \mathcal{D}_{\langle M,\pi\rangle}^{\,\mathcal{E}}\big) \le \varepsilon,\;\; \mathrm{budget}(\langle M,\pi\rangle) \le B \Big\},$$

and, comparing two candidate cores $$M_1, M_2$$:

$$\Delta(M_1, M_2) \;=\; C_{\mathcal{E}}(f \mid M_1) \;-\; C_{\mathcal{E}}(f \mid M_2).$$

Here $$\mathcal{D}_f^{\,\mathcal{E}}$$ is the output distribution of the target process $$f$$ in environment $$\mathcal{E}$$, and $$\mathcal{D}_{\langle M,\pi\rangle}^{\,\mathcal{E}}$$ is the distribution achieved by wrapping the model $$M$$ in a new program $$\pi$$. The divergence $$d$$ measures distributional distance between the two — not a task score. The budget constraint restricts compute, memory, and interaction resources; $$\mathrm{cost}(\pi)$$ counts all new task-specific code, data, and weights, and the compute spent *invoking* $$M$$ is billed too. If the capability is unattainable, the cost is $$\infty$$.

The question the definition asks is: *given that you already have $$M$$, how much additional structure must you supply to realize this capability?* The second expression compares the reusability of cognitive resources across candidate cores — and permits two systems to be incomparable, rather than forcing a total ranking.

The **intelligence axis**, then, is the single core that keeps lowering this residual cost across a broad range of heterogeneous capabilities.

## 7. Intelligence Content, Intelligence Density, and Axiality Are Three Different Questions

With the distinctions above in hand, the phrase "domain X has the highest intelligence content" can no longer be used carelessly.

**Intelligence content** asks: relative to some task range and resource constraint, how much reusable capability does the system provide?

**Intelligence density** additionally asks: relative to what cost? Storage size of the model? Compute per invocation? Total training investment?

**Axiality** asks: is this capability repeatedly borrowed by many different systems, and do improvements in it propagate to many domains?

A specialist model can be tiny and supremely efficient on its task without constituting a cross-domain cognitive axis. A generalist model can have vast reserves yet be expensive to invoke, and so be compute-inefficient in many settings.

Also — and this matters — the *bottleneck* of a real system need not coincide with the component holding the most transferable knowledge. A system missing one bit of state ("is the door already open?") can go from total failure to success. That bit is enormously valuable, but it would be a mistake to book it as a whole body of general cognitive ability. Likewise, the high-frequency physical manipulation that embodiment struggles with may simply not be a general cognitive capability.

Conversely, vast knowledge reserves that cannot enter the right feedback loop may have no practical value *for now*.

Knowledge reserves, immediate value, and bottleneck status cannot substitute for one another.

There is a further subtlety: system capability often comes from synergy between components. When core and controller are jointly necessary, removing either one destroys all performance. You cannot add the two ablation results together and claim the system contained "two complete copies of intelligence."

I would make "axis" concrete with three tests:

1. With the core fixed, does it allow many domains to adapt with only limited extra work?
2. When the core improves, do broad transfer gains appear?
3. Compared with building full systems separately, does sharing the core reduce duplicated learning while preserving capability?

**The intelligence axis is the component that most persistently carries cognition across domains.**

## 8. Embodiment and World Models

We can now return to the most contested judgment: is the intelligence *density* of embodiment and world models possibly *lower* than that of LLMs?

My conjecture: within ranges dominated by knowledge, task understanding, and abstract decision-making, the answer is probably yes. But this must not be inflated into "all physical capability is just an interface."

World models especially deserve caution. If a model mainly pursues photorealistic reconstruction, much of its compute goes to textures, lighting, and background variation that have little to do with the current decision. Faithfully depicting the world and extracting structure that *changes actions* are different optimization objectives.

Of course, not every world model is a video generator. MuZero learns a model organized around quantities directly relevant to planning — reward, policy, value — rather than reconstructing the pixel world [6].

So judge a world model's cognitive contribution not by how pretty its imagined futures look, but by whether it reduces *decision-relevant* uncertainty: Is this action feasible? What happens if conditions change? What regularity did this failure expose, and does it transfer?

And here is a hard boundary: reality can contain information that language pretraining neither provided nor could infer. Picture a button whose function was randomized *after* the model finished training. However broad the model's prior knowledge, no amount of recalling text will reveal it. The system must observe, intervene, or be told. A cognitive core can supply *how to explore*; it cannot substitute for experience not yet acquired.

Embodiment research therefore has two distinct possible contributions: making existing cognition act reliably on the world, and extracting structure from the world that the existing core lacks. Neither is nobler than the other — but they give different answers to "where is the intelligence axis?"

If future evidence shows that interaction-trained models supply more reusable capability across tasks than language pretraining does, then "the LLM is the main axis" should be revised. That is the honest position.

## 9. How Would This Change How We Judge Research and Industry Value?

If this perspective is accepted, then evaluating a piece of work should not stop at "how much did the benchmark improve?" The additional question is whether the work has *axiality*:

- Does it add general cognitive reserves, domain-specific knowledge, or invocation efficiency?
- Does it solve missing state, execution error, or a shortfall of core capability?
- Can the experience it produces flow back into the intelligence axis at sufficient throughput?

This changes what counts as a "research increment." Some work improves one narrow task yet clears a critical real-world bottleneck. Some work shows unremarkable single-metric gains yet lets the same capability enter many new domains. Some work creates new transferable structure whose payoff only appears in later tasks. All three are valuable; no single benchmark delta captures them.

The value of *data* changes too. What is worth acquiring first is not necessarily the most data, but the data that best reduces the current core's blind spots. Oceans of records re-confirming known regularities, and a single interaction that falsifies a wrong assumption, are not necessarily proportional in value [5].

But none of this implies "nothing outside the core is worth doing." Even a module that adds little general knowledge can matter enormously if it makes an important capability safe, reliable, and cheap.

Nor does "axis" mean returns must concentrate infinitely at one node. Real systems face latency, privacy, energy, reliability, and deployment constraints. Shared capability can be realized through different models at different scales and deployment sites — the world does not have to call one remote brain.

And a shared core brings shared defects. Foundation-model research noted early on that downstream systems inherit the base model's flaws [1]. The other side of cognitive reuse is the reuse of errors. A genuinely mature axis system must let external verification *correct the core*, not demand that the whole world adapt to its errors.

**The age of the intelligence axis may well be a distributed one.** Look at the data pipeline that already exists: data collected in a factory in city A, processed at university B, bought and cleaned by company C for training, and served to everyone as model D. The emergence of intelligence is *already* a distributed process.

## 10. The Intelligence Axis Is Not the Endpoint

Return to the opening claim: the LLM is the central embodiment of the intelligence axis. I still want to keep the strong intuition it expresses, but with a more careful reading:

> In many tasks we should seriously test this possibility — that the system's principal cross-domain knowledge and cognitive structure have already accumulated in the core formed by language pretraining, and that much of the subsequent work is not re-manufacturing intelligence, but supplying the conditions for that intelligence to act on the world.

The "carrier" here is not consciousness, personhood, or any mystical property, and it is not a claim that language contains all of reality. It is a warning against demoting the cognitive core to a talking dispatch layer while crediting all intelligence to the visible layer of external behavior.

Architecturally, the carrier of the intelligence axis must be a model with general theoretical reasoning ability — and the current LLM paradigm happens to satisfy that. But I refuse to turn this judgment into an article of architectural faith.

"Shared cognition becomes the organizing axis of intelligent systems" and "this axis comes primarily from LLMs" are propositions of different strength. The first being true does not guarantee the second stays true forever. What really matters is how capability accumulates and transfers.

So the most important feature of the age of the intelligence axis is probably not the arrival of an omniscient model. It is this:

> **Intelligence has begun to exist in a form that accumulates across systems and grows from shared experience.**

The way LLMs fuse the knowledge of many systems into one model, in linguistic form, is exactly what satisfies this.

We should stop asking only: *which system looks the most intelligent?* And start asking: which knowledge does not need to be re-learned? Which capabilities can cross bodies and tasks? Which experiences will become the new starting point for all systems?

If the future holds a change worth calling a turning point, I would rather understand it as this — there can be more and more different intelligent systems in the world, but intelligence itself no longer needs to happen from scratch inside each one of them.

When the *power* of some system's accumulated intelligence reaches a critical level, that will be the moment of the singularity.

## References

1. R. Bommasani et al., "On the Opportunities and Risks of Foundation Models," [arXiv:2108.07258](https://arxiv.org/abs/2108.07258), 2021.
2. G. Delétang, A. Ruoss, P.-A. Duquenne, E. Catt, T. Genewein, C. Mattern, J. Grau-Moya, L. K. Wenliang, M. Aitchison, L. Orseau, M. Hutter, J. Veness, "Language Modeling Is Compression," [arXiv:2309.10668](https://arxiv.org/abs/2309.10668), 2023. (ICLR 2024)
3. M. Ahn et al., "Do As I Can, Not As I Say: Grounding Language in Robotic Affordances," [arXiv:2204.01691](https://arxiv.org/abs/2204.01691), 2022. (SayCan)
4. A. Brohan et al., "RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control," [arXiv:2307.15818](https://arxiv.org/abs/2307.15818), 2023.
5. M. Finzi, S. Qiu, Y. Jiang, P. Izmailov, J. Z. Kolter, A. G. Wilson, "From Entropy to Epiplexity: Rethinking Information for Computationally Bounded Intelligence," [arXiv:2601.03220](https://arxiv.org/abs/2601.03220), 2026.
6. J. Schrittwieser et al., "Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model," [arXiv:1911.08265](https://arxiv.org/abs/1911.08265), 2019. (MuZero)
7. D. Ha, J. Schmidhuber, "World Models," [arXiv:1803.10122](https://arxiv.org/abs/1803.10122), 2018.
