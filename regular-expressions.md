---
description: Formal Languages, Regular Expressions, Automata and Transducers
---

# Regular Expressions

## Formal Language = Set of Strings of Symbols

A Formal Language can model a phenomenon, e.g. written English

Examples: All combinations of the letters, any number of As, followed by any
number of Bs, mathematical equations, all the sentences of a simplified version
of written English, a sequence of musical notation (e.g., the notes in
Beethoven's 9th Symphony), etc.

### What is a Formal Grammar for?

A formal grammar: a set of rules that match all and only instances of a formal
language. A formal grammar defines a formal language.

In Computer Science, Formal grammars are used to **generate** and **recognize**
formal languages (e.g., programming languages)

- Parsing a string of a language involves:
  - Recognizing the string and
  - Recording the analysis showing it is part of the language
- A compiler translates from language X to language Y, e.g.,This may include
  parsing language X and generating language Y
- If all natural languages were formal languages, then Machine Translation
  systems would just be compilers

### A Formal Grammar Consists of

#### N: a Finite set of non-terminal symbols

Symbols that can be replaced by other symbols

#### T: a Finite set of terminal symbols

Symbols that cannot be replaced by other symbols

#### R: a set of rewrite rules

Replace the symbol sequence XYZ with abXzY: `XYZ → abXzY`

#### S: A special non-terminal that is the start symbol

Marks the start of the language

## The Chomsky Hierarchy

### Type 0: No restrictions on rules

Equivalent to Turing Machine, general system capable of simulating any
algorithm.

### Type 1: Context-sensitive rules

`αAβ → αγβ`

- Greek letters = 0 or more non-terms/terms.
- A = non-terminal
- Rule means: replace A with γ, when A is between α and β

### Type 2: Context-free rules

`A → αγβ`

- Like context-sensitive, except left-hand side can only contain exactly one
  non-terminal

Example Rule from linguistics:
![Context-free Rules](.gitbook/assets/chomsky-hierarchy-type-2.png)

### Type 3: Context-free rules with restrictions

Regular (finite state) grammars

- `A → βa` or `A → ϵ` (left regular)
- `A → aβ`, or `A → ϵ` (right regular)

Like Type 2, except:

- Non-terminals can precede terminals in left regular grammar
- Non-terminals can follow terminals in right regular grammar
- Null string is allowed
