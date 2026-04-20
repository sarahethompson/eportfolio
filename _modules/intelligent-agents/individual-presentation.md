---
layout: page
title: Individual Presentation
description: Individual implementation and critical evaluation of the BDI multi-agent academic research system
permalink: /modules/intelligent-agents/individual-presentation/
---

*Part of the [Intelligent Agents](/eportfolio/modules/intelligent-agents/) module portfolio.*

---

## Overview

**Title:** Multi-Agent Academic Research System: Practical Implementation and Critical Evaluation

**Submitted:** 13 April 2026

**Format:** Recorded video presentation with transcript (approx. 2,000 words, 20 minutes)

The presentation covered the full individual implementation of the BDI multi-agent academic research system: system architecture, blackboard coordination, BDI reasoning cycles for each agent, deliberation and reconsideration in action, test coverage across 26 passing tests, and a live demo. The final section critically evaluated where the system met the team design proposal, where it fell short, and what a credible path forward would look like.

---

## System Architecture

The implementation comprises four specialised agents coordinated via a shared blackboard environment. The Coordinator (ResearchPipeline) posts goals and reads status; each agent runs a perceive–deliberate–act cycle before returning results to the blackboard.

<img src="{{ '/assets/img/bdi_arch_diagram.png' | relative_url }}" alt="BDI Multi-Agent System Architecture" class="img-fluid rounded my-3">

---

## BDI Reasoning Cycle

Each agent implements the BDI cycle with belief revision after each action. SearchAgent and ProcessingAgent exhibit full multi-cycle reasoning including intention reconsideration. ExtractionAgent and StorageAgent run single cycles, a deliberate design choice grounded in Bratman's (1987) argument that rational agents should not reconsider intentions without genuine cause.

<img src="{{ '/assets/img/bdi_cycle_diagram.png' | relative_url }}" alt="BDI Reasoning Cycle" class="img-fluid rounded my-3">

---

## Key Design Decisions and Limitations

The presentation identified four known limitations, two anticipated in the team design proposal and two that emerged during implementation.

**No persistent state.** Agent beliefs reset on every execution. This is a prerequisite for learning-based filtering but is not sufficient on its own: a learning system also requires a feedback signal, richer features, and an exploration strategy. Without those, persistent storage accumulates observations with no way to evaluate the decisions that produced them.

**Dead code path in quality scoring.** The ExtractionAgent populates a `full_text` field with the abstract as a placeholder, and the quality scoring formula includes a bonus for papers with full text over a thousand characters. Because the ArXiv API only returns abstracts, this bonus is unreachable in the current implementation.

**Rule-based filtering.** The ProcessingAgent applies fixed thresholds rather than learned ones. This was a deliberate trade-off: deterministic behaviour makes the test suite reliable. The reconsideration mechanism, triggered when fewer than 30% of results survive filtering, works cleanly in tests because the threshold is fixed. A learned model would make unit testing fragile.

**Single data source.** The system queries ArXiv only. Extending to Semantic Scholar or CiteSeer would give ExtractionAgent genuine reconsideration candidates: attempt one source, find incomplete metadata, reconsider and try another.

The progression from the current implementation toward a fully learning-based system is not two steps but three: fixed rules (current), adaptive rules using persistent state to adjust thresholds from observed statistics, and full learning requiring persistent state, a feedback signal, and an exploration strategy. Da Silva, Meneguzzi and Logan (2020) identify integrating learning with BDI reasoning as an open research challenge; Qu et al. (2025) make a similar point in a more recent survey.

---

## References

Bratman, M.E. (1987) *Intention, Plans, and Practical Reason*. Cambridge, MA: Harvard University Press.

Da Silva, L., Meneguzzi, F. and Logan, B. (2020) 'BDI agent architectures: A survey', in *Proceedings of the Twenty-Ninth International Joint Conference on Artificial Intelligence (IJCAI-20)*. Yokohama, Japan, pp. 4776–4784. Available at: https://doi.org/10.24963/ijcai.2020/684 [Accessed: 13 April 2026].

Floridi, L. et al. (2018) 'AI4People: An ethical framework for a good AI society', *Minds and Machines*, 28(4), pp. 689–707. Available at: https://doi.org/10.1007/s11023-018-9482-5 [Accessed: 13 April 2026].

Qu, X. et al. (2025) *A comprehensive review of AI agents: Transforming possibilities in technology and beyond*. arXiv preprint. Available at: https://doi.org/10.48550/arXiv.2508.11957 [Accessed: 13 April 2026].

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: John Wiley and Sons.
