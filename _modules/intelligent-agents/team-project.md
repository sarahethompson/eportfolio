---
layout: page
title: Team Project
description: Meeting notes, coordination record and tutor feedback from the Group E BDI multi-agent academic research system design project
permalink: /modules/intelligent-agents/team-project/
---

*Part of the [Intelligent Agents](/eportfolio/modules/intelligent-agents/) module portfolio.*

---

## Project Overview

**Project title:** BDI Multi-Agent Academic Research Retrieval System

**Team:** Group E — Sarah Thompson, Richárd Szépi, Ioanna Tziouvaka, Adaeze Ugochukwu

**My role:** Project Lead / primary coordinator — responsible for team communication, BDI prototype implementation, design decisions and methodology section, and final report coordination.

**Deliverable:** A design proposal for a multi-agent system applying the Belief–Desire–Intention (BDI) architectural model to academic research retrieval, comprising Search, Extraction, Processing, and Storage agents coordinated via a shared blackboard environment.

---

## Meeting Notes

### Kick-off — 29 January 2026

Team introductions and project selection. Confirmed *Academic Research Online* as the chosen project. Finalised the team contract with assigned roles (Sarah Thompson — Project Lead; Ioanna Tziouvaka — Technical Lead; Richárd Szépi — Research and Documentation Lead; Adaeze Ugochukwu — UML Design Lead). Agreed communication via the module discussion forum and Google Drive for document collaboration. Agreed to check in at least every other day.

**My actions:** Upload finalised meeting minutes to Google Drive; conduct initial research over the weekend.

---

### 2 February 2026

Each team member presented initial research findings. Clear alignment was identified across individual findings. A list of prospective academic sources was proposed and agreed as the primary theoretical backbone. Initial structure of the design proposal was mapped.

**My actions:** Propose and formalise adoption of the BDI framework as the core architectural model.

---

### 5 February 2026

Reviewed the full assignment brief to ensure shared understanding. Formally allocated report sections among team members. Drafted an initial conceptual outline of the proposed multi-agent system, identifying core components and agreeing on the BDI-based architectural direction.

**My actions:** Begin drafting assigned sections based on agreed structure.

---

### 10 February 2026

Each member presented first draft progress. Team reviewed the current draft collectively for structure, theoretical grounding, and technical coherence. Agreed a peer review phase before the next meeting. GitHub profiles shared to support collaboration.

**My actions:** Develop the first prototype implementation of the agents based on the agreed BDI framework and architectural outline.

---

### 17 February 2026

I presented a revised BDI implementation addressing alignment with the assignment brief requirement that agents act on their own beliefs, desires, and intentions. The updated implementation includes separate classes for Beliefs, Desires, Deliberation, and Intentions. Agents execute a genuine perceive → deliberate → act → update beliefs cycle (up to five cycles). Deliberation evaluates ranked candidates independently from the committed intention, and SearchAgent and ProcessingAgent support intention reconsideration. The implementation uses only the Python standard library and passed 26 tests including reconsideration tests.

Adaeze presented draft diagram concepts: component architecture, sequence diagram, and activity diagram for ProcessingAgent. The team agreed these aligned well with the theoretical and architectural narrative.

The team also agreed to use future tense consistently throughout the design proposal, reflecting its status as a proposed system rather than a completed implementation.

**My actions:** Complete the revised BDI implementation; write the Design Decisions and Methodology section.

---

### 24 February 2026

Ioanna and I reviewed the full assignment, identifying minor inconsistencies in tone, terminology, and structure. I created a new consolidated working draft combining the latest revised versions of all sections. Identified that the report exceeded the word count limit.

**My actions:** Write the Introduction section and ensure alignment with the consolidated draft.

---

### 3 March 2026

Full team reviewed the current version of the report for structure, clarity, and alignment. Confirmed all sections were complete. Word count reduction identified as the main outstanding task before submission.

**My actions:** Review and shorten the Design Decisions and Methodology section while maintaining key content.

---

### 5 March 2026

Each member confirmed word count reductions were complete. Full report reviewed collectively for consistency in terminology, writing style, and structure. Diagram placement and referencing verified. The final version was approved by all members for submission.

---

## Tutor Feedback

The following feedback was received on the team report submission.

**Knowledge and understanding of the topic**

The report demonstrates a strong understanding of intelligent agent architectures and the application of the Belief–Desire–Intention model within an academic research retrieval context. The theoretical foundations of agent systems are explained clearly and are appropriately connected to the proposed system design. The discussion of multi-agent coordination, reasoning cycles, and modular architecture reflects good comprehension of core intelligent agent principles, although further detail on implementation mechanisms and system behaviour during runtime would strengthen the technical depth.

**Criticality**

The report shows good evidence of critical reflection, particularly when discussing trade-offs between reactive and deliberative architectures and the limitations of rule-based approaches. The inclusion of challenges, limitations, and future work demonstrates awareness of practical design constraints and evolving agent research directions. However, the analysis could be further strengthened through deeper comparison with alternative agent architectures or approaches to intelligent information retrieval.

**Use of relevant sources**

The report demonstrates a strong use of relevant academic literature related to intelligent agents, multi-agent systems, and BDI architectures. Sources are integrated effectively to support theoretical explanations and design decisions, showing engagement with both foundational and contemporary work in the field. Greater synthesis of the literature to support critical argumentation would further improve the academic depth of the discussion.

**Structure and presentation**

The report is clearly structured with well organised sections including theoretical background, system requirements, design decisions, challenges, and future work. The inclusion of architectural and interaction diagrams supports the explanation of the system design and improves overall readability. Minor improvements in formatting consistency and diagram labelling would enhance the overall professional presentation.

**Academic integrity**

Academic conventions are followed consistently throughout the report, with appropriate citation of sources and a clearly structured reference list. The work demonstrates a strong attempt to maintain academic integrity and appropriate attribution of ideas. Minor improvements in formatting consistency and referencing style would further strengthen adherence to academic writing standards.
