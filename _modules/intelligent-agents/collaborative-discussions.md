---
layout: page
title: Collaborative Discussions
description: Summaries from three unit discussion forums — agent-based systems, agent communication languages, and deep learning applications
permalink: /modules/intelligent-agents/collaborative-discussions/
---

*Part of the [Intelligent Agents](/eportfolio/modules/intelligent-agents/) module portfolio.*

---

## Discussion 1 — Agent-Based Systems (Units 1–3)

**Topic:** Why agent-based approaches are increasingly relevant to organisations operating in complex, rapidly evolving environments.

The discussion highlights several key reasons why agent-based systems have become increasingly relevant to organisations operating in complex, rapidly evolving environments. A common theme across the posts is the ability of agent-based approaches to address problems that are difficult to manage using traditional centralised systems. As Matthew noted, modern organisational systems often operate across distributed infrastructures and changing conditions, which can make static or monolithic architectures less effective. Agent-based systems address this challenge by distributing decision-making across autonomous components that can perceive their environment and act independently (Russell and Norvig, 2021).

Another important theme raised in the discussion is the role of emergent behaviour in complex systems. As Richárd highlighted, modelling systems at the level of individual agents enables researchers and organisations to observe how global outcomes arise from local interactions among many independent actors. Agent-based modelling has therefore been widely used to analyse complex social and organisational systems for which outcomes cannot be easily predicted using top-down approaches (Bonabeau, 2002).

The discussion also emphasised the importance of specialisation and coordination within multi-agent systems. Rather than relying on a single intelligent component, many agent-based architectures divide responsibilities across multiple agents that focus on specific tasks, such as monitoring, analysing information or coordinating responses. This structure mirrors how organisations themselves operate, with different roles contributing specialised expertise to collective decision-making. As Wooldridge (2009) notes, multi-agent systems are particularly well-suited to problems that require distributed expertise and coordination among autonomous components.

Overall, the discussion demonstrates that agent-based approaches offer significant benefits for organisations, including scalability, flexibility and improved decision-making in complex environments. These characteristics explain why agent-based systems continue to attract attention in both research and real-world applications.

**References**

Bonabeau, E. (2002) 'Agent-based modeling: Methods and techniques for simulating human systems', *Proceedings of the National Academy of Sciences*, 99(Suppl 3), pp. 7280–7287.

Russell, S. and Norvig, P. (2021) *Artificial Intelligence: A Modern Approach*. 4th edn. Pearson.

Wooldridge, M. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Wiley.

---

## Discussion 2 — Agent Communication Languages (Units 5–7)

**Topic:** The evolution of agent communication design, from KQML to modern LLM-based frameworks, and the tensions that persist between formal and natural language approaches.

This discussion traced a compelling arc in agent communication design, from the formal performative-based approach of KQML through to the natural language exchanges of modern LLM-based frameworks, and the tensions that persist between these approaches remain unresolved.

My initial post established that KQML's core contribution was encoding communicative intent explicitly through speech-act-inspired performatives, drawing on Austin (1962) and Searle (1969). This distinguished ACLs from method invocation in languages such as Python or Java, which carries data efficiently but expresses no intent. The practical limitations of KQML — its informal semantics and absence of a trust model — were well documented by Mayfield, Labrou and Finin (1996), and motivated the development of FIPA-ACL and, more recently, lightweight protocols such as MCP and A2A (Zhao et al., 2025).

Engaging with peers extended this analysis in two important directions. Responding to Ioanna's post, I explored how LLM-based frameworks such as AutoGen now use natural language as the communication medium between agents, with the LLM itself inferring intent rather than reading an explicit performative (Wu et al., 2023). This is where Unit 7's focus on NLP becomes directly relevant: as the lecturecast highlights, natural language understanding remains genuinely difficult for machines, with ambiguity, context-dependence, and lack of formal grounding presenting persistent challenges. This helps explain why replacing KQML's explicit performatives with natural language inference, while flexible, introduces auditability and reliability concerns that formal ACLs were specifically designed to avoid (Wooldridge, 2009).

Responding to Richárd's post introduced a further dimension — that in real-world mixed human-agent systems such as healthcare monitoring and autonomous vehicles, neither formal ACLs nor natural language exchanges are currently adequate. Domain-specific standards such as HL7 FHIR handle data exchange effectively but carry no communicative intent (Vreeman, 2025), recreating the very gap that motivated KQML's design.

Taken together, these threads suggest that the field has not so much solved the agent communication problem as redistributed it — from formal but rigid ACLs, to flexible but opaque natural language, with the challenge of intent, trust, and verifiability remaining central at each stage.

**References**

Austin, J.L. (1962) *How to Do Things with Words*. Oxford: Oxford University Press.

Ehtesham, A., Singh, A., Gupta, G.K. and Kumar, S. (2025) 'A survey of agent interoperability protocols: MCP, ACP, A2A, and ANP', *arXiv preprint*, arXiv:2505.02279. Available at: https://doi.org/10.48550/arXiv.2505.02279 [Accessed: 5 April 2026].

Mayfield, J., Labrou, Y. and Finin, T. (1996) 'Evaluation of KQML as an agent communication language', in Wooldridge, M., Müller, J.P. and Tambe, M. (eds) *Intelligent Agents II: Agent Theories, Architectures, and Languages*. Berlin: Springer, pp. 347–360.

Searle, J.R. (1969) *Speech Acts: An Essay in the Philosophy of Language*. Cambridge: Cambridge University Press.

Vreeman, D.J. (2025) *Building the standards infrastructure for healthcare AI*. HL7 International. Available at: https://blog.hl7.org/building-the-standards-infrastructure-for-healthcare-ai-lessons-from-the-interoperability-journey [Accessed: 5 April 2026].

Wooldridge, M. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: John Wiley & Sons.

Wu, Q. et al. (2023) 'AutoGen: Enabling next-generation large language model applications', *arXiv preprint*, arXiv:2308.08155.

---

## Discussion 3 — Deep Learning Applications (Units 9–11)

*Summary to be added on completion of the discussion forum.*
