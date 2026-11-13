# CS5760 Natural Language Processing - Homework 4

## Student Information

* **Name:** Ruyi Gai
* **Student ID:** 700778329
* **Course:** CS5760 Natural Language Processing
* **Semester:** Fall 2026
* **University:** University of Central Missouri


## Files

```text
Homework 4.docx
Homework 4.ipynb
README.md
```

### `Homework 4.docx`

This document contains: short-answer, code and results screenshots

### `Homework 4.ipynb`

The Jupyter Notebook contains:

* The code and results for all three programming questions
* Comments explaining the main steps of the code



## Assignment Overview

This assignment covers sequence-to-sequence models, attention mechanisms, and the Transformer architecture. The programming exercises demonstrate text preprocessing, named entity recognition, and a NumPy implementation of scaled dot-product attention.


## Part I: Short Answers

| Question | Topics |
| --- | --- |
| 1. Sequence-to-Sequence Models and Attention | Encoder and decoder roles in machine translation, the fixed-length context bottleneck, and attention over encoder hidden states |
| 2. Attention Mechanisms | Hard and soft attention, backpropagation, dot-product scores, softmax weights, and the context vector |
| 3. Self-Attention in Transformers | Self-attention and encoder–decoder attention, the roles of Q, K, and V, and long-distance dependencies |
| 4. Multi-Head Attention | Independent attention heads, the calculation of 64 dimensions per head for a 512-dimensional model with 8 heads, and concatenation followed by an output projection |
| 5. Transformer Architecture | Positional encodings, causal masking, and the differences between RNN sequence processing, parallel Transformer training, and autoregressive generation |


## Part II: Programming

### Question 1: NLP Preprocessing Pipeline

The notebook uses a regular expression to split a sentence about virtual assistants into words and punctuation. It filters punctuation and common English stopwords, lowercases the remaining words, and applies NLTK's Porter stemmer.

The notebook prints the original tokens, the filtered tokens, and the final stems. For example, `techniques` becomes `techniqu` and `assistants` becomes `assist`. The written answers explain the difference between stemming and lemmatization and discuss how stopword removal can affect tasks that depend on negation.

### Question 2: Named Entity Recognition with spaCy

The notebook applies spaCy's `en_core_web_sm` model to the provided sentence about LeBron James. Each detected entity is printed with its text, label, and character offsets. The start offset is inclusive and the end offset is exclusive.

Two examples from the saved output are shown below.

```text
Text: LeBron James | Label: PERSON | Start: 1 | End: 13
Text: 2020 | Label: DATE | Start: 91 | End: 95
```

The written answers compare named entity recognition with part-of-speech tagging and describe applications of entity recognition.

### Question 3: Scaled Dot-Product Attention

The notebook computes `Q @ K.T`, divides the scores by the square root of the key dimension, applies softmax to each query row, and multiplies the attention weights by `V`. It subtracts the maximum score in each row before exponentiation for numerical stability.

For the supplied matrices, the key dimension is 4 and the scaling factor is 2. The notebook prints the following matrices rounded to three decimal places.

```text
Attention Weights:
[[0.731 0.269]
 [0.269 0.731]]

Final Output:
[[2.076 3.076 4.076 5.076]
 [3.924 4.924 5.924 6.924]]
```

The written answers explain why scaling reduces softmax saturation and how self-attention uses context to represent relationships between words.



## Technologies Used

* **Python**
* **NLTK**
* **spaCy and the `en_core_web_sm` English model**
* **NumPy**
* **Jupyter Notebook**


## Conclusion

This assignment covered sequence-to-sequence models for machine translation, hard and soft attention, self-attention, and multi-head attention. The short-answer questions explained how attention addresses the fixed-length context bottleneck and how positional encodings and causal masking support Transformer training and generation.

The programming exercises used regular expressions to tokenize text, NLTK to remove stopwords and stem words, spaCy to identify named entities and report their character offsets, and NumPy to compute scaled dot-product attention. The NumPy exercise put the attention concepts into practice by calculating attention weights and using them to combine value vectors.


