---
description: >-
  HMM and Part of Speech Tagging. Viterbi Algorithm. Limits of Sequence
  Labeling.
---

# HMM POS Tagging

## POS Tagger Tool

{% embed url="https://codepen.io/dizys/pen/XWzOpyO" %} POS Tagger Tool
{% endembed %}

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
