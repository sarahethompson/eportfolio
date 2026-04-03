---
layout: page
title: "Agent Architectures"
---

# Agent Architectures

Agent architecture refers to the internal structure that determines how an agent perceives its environment, makes decisions and performs actions.

Different architectures have been developed within artificial intelligence research.

## Reactive Agents

Reactive agents respond directly to environmental stimuli without maintaining complex internal models.

Example rule:

`if obstacle detected → turn`

Reactive agents are:

- simple
- fast
- robust

## Subsumption Architecture

Subsumption architecture is a reactive agent architecture developed by Rodney Brooks.

It consists of layered behaviours where higher layers can override lower ones.

Example behaviour layers:

- Layer 1: avoid obstacles
- Layer 2: wander
- Layer 3: explore

If an obstacle is detected, the avoid obstacle behaviour overrides other behaviours.

Subsumption architecture demonstrated that complex behaviour can emerge from simple behavioural rules.

## Deliberative Agents

Deliberative agents maintain an internal representation of the world and use reasoning to plan actions.

Typical cycle:

1. perceive environment
2. update world model
3. plan actions
4. execute plan

These systems were common in early symbolic AI.

## BDI Architecture

BDI stands for:

- **Beliefs**
- **Desires**
- **Intentions**

Beliefs represent information the agent has about the world.

Desires represent goals the agent wishes to achieve.

Intentions represent the plans the agent commits to executing.

BDI reasoning loop:

1. perceive environment
2. update beliefs
3. select goals
4. choose intentions
5. execute actions

BDI architectures are widely used in multi-agent systems research.

## Coordination in Multi-Agent Systems

Agents must coordinate their actions in multi-agent systems.

Common coordination mechanisms include:

- hierarchical coordination
- blackboard systems
- Contract Net Protocol
