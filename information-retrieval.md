---
description:
  Information Retrieval and Related Applications. TF/IDF, Cosine Similarity.
---

# Information Retrieval

## TF/IDF

### Term Frequency (TF)

TF: number of times term t occurs in document (or alternative: number of terms
divided by length of document)

$$TF(t, d)=Count(times\ of\ term\ t\ appearing\ in\ d)$$

### Inverse Document Frequency (IDF)

IDF: logarithm of number of documents (in corpus) divided by number of documents
containing term t

$$IDF(t)=\log{{Count(documents\ in\ total)}\over{Count(documents\ containing\ term\ t)}}$$

### TF-IDF

$$TF\_IDF(t, d)=TF(t, d) * IDF(t)$$

## Cosine Similarity

Cosine of the Angle Between the Vectors. Range is [0, 1]. The higher the value,
the more similar the vectors.

$$Cosine(v1, v2) = \frac{v_1 \cdot v_2}{\sqrt{{v_1}^2} \cdot \sqrt{{v_2}^2}}$$

### Example

$$v1 = [0, 5, 0, 5, 0]$$

$$v2 = [0, 7, 0, 9, 0]$$

$$Cosine(v1, v2) = {{0*0+5*7+0*0+5*9+0*0}\over{\sqrt{0^2+5^2+0^2+5^2+0^2}+\sqrt{0^2+7^2+0^2+9^2+0^2}}} = 0.992$$
