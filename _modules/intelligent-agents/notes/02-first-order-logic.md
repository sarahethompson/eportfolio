---
layout: page
title: "First Order Logic"
---

# First-Order Logic (FOL)

## Overview

First-Order Logic (FOL) is a formal system used to represent knowledge and reason about relationships between objects. It is widely used in artificial intelligence for knowledge representation and reasoning.

FOL extends propositional logic by allowing statements about objects and relationships.

## Components of First-Order Logic

### Constants

Constants represent specific objects.

Examples:

- Socrates
- London
- Server1

### Predicates

Predicates describe properties or relationships between objects.

Examples:

- Human(Socrates)
- Connected(Server1, Server2)

### Variables

Variables represent general objects.

Example:

- Human(x)

### Quantifiers

Universal quantifier:

`∀x`

Meaning: for all x.

Example:

`∀x Human(x) → Mortal(x)`

Existential quantifier:

`∃x`

Meaning: there exists an x.

Example:

`∃x Human(x)`

## Reasoning with First-Order Logic

FOL allows systems to derive new knowledge from existing facts.

Example:

- Human(Socrates)
- ∀x Human(x) → Mortal(x)

Therefore:

- Mortal(Socrates)

## Role in Artificial Intelligence

First-order logic forms the foundation of many symbolic AI systems, including:

- knowledge bases
- rule-based systems
- planning systems
- deliberative agent architectures
