---
layout: page
title: Collaborative Discussions
description: Summaries from three unit discussion forums on agent-based systems, agent communication languages, and deep learning applications
permalink: /modules/intelligent-agents/collaborative-discussions/
---

*Part of the [Intelligent Agents](/eportfolio/modules/intelligent-agents/) module portfolio.*

---

## Discussion 1: Agent-Based Systems (Units 1–3)

**Topic:** Why agent-based approaches are increasingly relevant to organisations operating in complex, rapidly evolving environments.

[View forum thread](https://www.my-course.co.uk/mod/forum/view.php?id=1304139)

The discussion centred on three properties that make agent-based approaches well-suited to distributed organisational environments: the distribution of decision-making across autonomous components rather than centralised control (Russell and Norvig, 2021); the emergence of global behaviours from local agent interactions (Bonabeau, 2002); and the natural parallel between multi-agent specialisation and how organisations divide responsibilities (Wooldridge, 2009). Peer contributions from Matthew and Richárd grounded these points in concrete infrastructure and complex system modelling examples, reinforcing scalability and adaptability as the primary organisational benefits.

---

## Discussion 2: Agent Communication Languages (Units 5–7)

**Topic:** The evolution of agent communication design, from KQML to modern LLM-based frameworks, and the tensions that persist between formal and natural language approaches.

[View forum thread](https://www.my-course.co.uk/mod/forum/view.php?id=1304166)

My initial post argued that KQML's core contribution was encoding communicative intent explicitly through speech-act performatives, something method invocation in standard languages cannot do (Mayfield et al., 1996). Peer exchange extended this in two directions: LLM frameworks like AutoGen replace explicit performatives with natural language inference, which is flexible but sacrifices auditability (Wu et al., 2023); and domain standards like HL7 FHIR handle data but carry no intent, recreating the original gap. My conclusion was that the field has redistributed rather than solved the agent communication problem, with intent, trust, and verifiability remaining unresolved at each stage.

---

## Discussion 3: Deep Learning Applications (Units 9–11)

**Topic:** Ethical concerns arising from generative AI, with a focus on AI-assisted code generation as a high-stakes domain that is underexplored relative to its rate of adoption.

[View forum thread](https://www.my-course.co.uk/mod/forum/view.php?id=1304195)

My initial post focused on security vulnerabilities, deskilling risks, and unresolved intellectual property questions in AI-assisted code generation, against a significant governance gap between policy adoption and formal accountability frameworks. Peer contributions broadened the frame: transparency and explainability as a structural accountability problem (Goktas, 2024); bias as a training data issue that manifests differently across domains (Buolamwini and Gebru, 2018); and copyright uncertainty extending beyond code to image and text generation (Gervais, 2020). The summary post drew these threads together: insecure code, biased clinical models, copyright exposure, and opaque decision-making are not separate problems but the same pattern: deployment consistently outpacing the accountability structures around it, expressed across different domains.

---

## References

Bonabeau, E. (2002) 'Agent-based modeling: methods and techniques for simulating human systems', *Proceedings of the National Academy of Sciences*, 99(Supplement 3), pp. 7280–7287. Available at: https://doi.org/10.1073/pnas.082080899 [Accessed: 18 April 2026].

Buolamwini, J. and Gebru, T. (2018) 'Gender shades: intersectional accuracy disparities in commercial gender classification', in Friedler, S.A. and Wilson, C. (eds.) *Proceedings of the 1st Conference on Fairness, Accountability and Transparency*. Proceedings of Machine Learning Research, vol. 81. PMLR, pp. 77–91. Available at: https://proceedings.mlr.press/v81/buolamwini18a.html [Accessed: 18 April 2026].

Gervais, D.J. (2020) 'The machine as author', *Iowa Law Review*, 105(5), pp. 2053–2106.

Goktas, P. (2024) 'Ethics, transparency, and explainability in generative AI decision-making systems: a comprehensive bibliometric study', *Journal of Decision Systems*, pp. 1–29.

Mayfield, J., Labrou, Y. and Finin, T. (1996) 'Evaluation of KQML as an agent communication language', in Wooldridge, M., Müller, J.P. and Tambe, M. (eds.) *Intelligent Agents II: Agent Theories, Architectures, and Languages*. Lecture Notes in Artificial Intelligence, vol. 1037. Berlin: Springer, pp. 347–360.

Russell, S. and Norvig, P. (2021) *Artificial Intelligence: A Modern Approach*. 4th edn. Hoboken, NJ: Pearson.

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: John Wiley and Sons.

Wu, Q., Bansal, G., Zhang, J., Wu, Y., Li, B., Zhu, E., Jiang, L., Zhang, X., Zhang, S., Liu, J., Awadallah, A.H., White, R.W., Burger, D. and Wang, C. (2023) *AutoGen: enabling next-gen LLM applications via multi-agent conversation*. arXiv preprint arXiv:2308.08155. Available at: https://arxiv.org/abs/2308.08155 [Accessed: 18 April 2026].
