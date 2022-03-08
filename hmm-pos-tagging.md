---
description: >-
  HMM and Part of Speech Tagging. Viterbi Algorithm. Limits of Sequence
  Labeling.
---

# HMM POS Tagging

## POS Tagger Tool

{% embed url="https://codepen.io/dizys/pen/XWzOpyO" %} POS Tagger Tool
{% endembed %}

## Penn Treebank POS Tag Set

| Tag  | Description              | Examples       | Tag | Description         | Examples         |
| ---- | ------------------------ | -------------- | --- | ------------------- | ---------------- |
| CC   | Coordinating conjunction | and, or        | RB  | Adverb              | very             |
| CD   | Cardinal number          | one, 2         | RBR | Adverb, comparative | better           |
| DT   | Determiner               | the, a         | RBS | Adverb, superlative | best             |
| EX   | Existential there        | there          | RP  | Particle            | out              |
| FW   | Foreign word             | 单词           | SYM | Symbol              | %                |
| IN   | Preposition or subord.   | of, in, with   | TO  | Infinitival marker  | to               |
| JJ   | Adjective                | big, nice      | UH  | Interjection        | um, ah, oh, oops |
| JJR  | Adjective, comparative   | bigger, better | VB  | Verb, base form     | go               |
| JJS  | Adjective, superlative   | biggest, best  | VBD | Verb, past form     | went             |
| LS   | List item marker         | 1, 2, 3        | VBG | Verb, gerund form   | running          |
| MD   | Modal                    | can, should    | VBN | Verb, past part     | ran              |
| NN   | Noun, singular or mass   | book, car      | VBP | Verb, present       | eat              |
| NNS  | Noun, plural             | books, cars    | VBZ | Verb, 3rd person    | eats             |
| NNP  | Proper noun, singular    | Edinburgh      | WDT | Wh-determiner       | which            |
| NNPS | Proper noun, plural      | Smiths         | WP  | Wh-pronoun          | who              |
| PDT  | Predeterminer            | all, both      | WP$ | Possessive wh-pron. | whose            |
| POS  | Possessive ending        | 's             | WRB | Wh-adverb           | how              |
| PRP  | Personal pronoun         | I, you, he     | PU  | Punctuation         | ",", "."         |
| PRP$ | Possessive pronoun       | my, your, his  |

## HMM Viterbi Algorithm

### Training States

**Transition Probability / Prior Probability**

$$Trans\_Prob(TagA \rightarrow TagB) = {{Count(TagB\_following\_TagA)}\over{Count(TagA)}}$$

**Emission Probability / Likelihood**
$$Emis\_Prob(TokenA, TagA) = {{Count(TokenA\_being\_TagA)}\over{Count(TagA)}}$$

### Viterbi Algorithm

Each step:

$$Step\_Prob(TokenA, TagA) = max[Step\_Prob(Last\_Token, TagX) * Trans\_Prob(TagX, TagA)] * Emis\_Prob(TokenA, TagA)$$

### Example: Fish sleep.

#### Transition Probability

![Transition Probability for "Fish sleep."](.gitbook/assets/hmm-viterbi-example-trans-probs.png)

#### Emission Probability

$$Emis\_Prob(fish, noun)={8\over{8+2}}=0.8$$
$$Emis\_Prob(fish, verb)={5\over{5+5}}=0.5$$
$$Emis\_Prob(sleep, noun)={2\over{8+2}}=0.2$$
$$Emis\_Prob(sleep, verb)={5\over{5+5}}=0.5$$

#### Steps

![Steps result for "Fish sleep."](.gitbook/assets/hmm-viterbi-example-steps.png)
