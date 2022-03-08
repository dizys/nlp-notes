---
description: >-
  Distribution of Words in Sentences: N-grams, Phrase Structure Syntax and
  Parsing
---

# Constituent Structure

## unigram

Probability of each token chosen randomly (and independently of other tokens)

$$unigram(t) = {Count(times\ t\ appearing)\over{Count(total\ word\ appearings)}} $$

### Markov Assumption

Probability of each token chosen randomly (and independently of other tokens)

## bigram

Probability of a token given the previous token

$$bigram(t, t_{previous}) = {{Count({t_{previous}}\rightarrow{t})}\over{Count(t_{previous})}}$$

### Example

```python
Count(the) = 69_971
Count(the -> same) = 628

bigram(same, the) = count(the -> same) / count(the) = 628 / 69_971 = 0.0898
```

### Additional Steps

1. Include probability that a word occurs at the beginning of a sentence, i.e.
   bigram(the, START)
2. Include probability that a token occurs at the end of a sentence, e.g.
   bigram(END, .)
3. Include non-zero probability for case when an unknown word follows a known
   one.

### Backoff Model

If a bigram has a zero count, "backoff" (use) the unigram of the word.

That is to replace `bigram(current_word, previous_word)` with
`unigram(current_word)`.

### Markov Assumption

Probability of a word depends only on the previous word.

## Trigrams, 4-grams, N-grams

### Trigram Probability

$$trigram(t, t_{-1}, t_{-2})={Count({t_{-2}}\rightarrow{t_{-1}}\rightarrow{t})\over{Count({t_{-2}}\rightarrow{t_{-1}})}}$$

Example: `count(the -> same -> as) / count(the -> same)`

### 4-gram Probability

$$fourgram(t, t_{-1}, t_{-2}, t_{-3})={Count({t_{-3}}\rightarrow{t_{-2}}\rightarrow{t_{-1}}\rightarrow{t})\over{Count({t_{-3}}\rightarrow{t_{-2}}\rightarrow{t_{-1}})}}$$

Example: `count(the -> same -> as -> an) / count(the -> same -> as)`

### N-gram Probability

$$ngram(t, t_{-1}, ..., t_{-n+1})={Count({t_{-n+1}}\rightarrow{...}\rightarrow{t_{-1}}\rightarrow{t})\over{Count({t_{-n+1}}\rightarrow{...}\rightarrow{t_{-1}})}}$$

### Markov Assumptions

Trigram Model: probability of a word depends only on the previous two words.

N-gram Model: probability of a word depends only on the previous N-1 words.

Probability of a sentence = Product of probabilities of each word.

## CKY
