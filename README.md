# 🌍 Language-Agnostic Text Classifier  
> Train on English. Works on Hindi. No translation. No multilingual training.

## Core Idea (in simple words)

> Languages look different, but **meaning is shared**.

Instead of teaching the model:
- “what English words mean”

we force it to learn:
- **what sentences mean**, independent of language

If a Hindi sentence expresses the same *idea* as an English one,  
their internal representations should be **close**.

## Key Innovation Used

### Language-Agnostic Semantic Learning  
The model is trained to focus on **semantics**, not surface words.

It learns:
- positivity vs negativity
- intent and sentiment
- meaning patterns

rather than memorizing English vocabulary.

### Contrastive Learning (Most Important Part)

During training, each English sentence is paired with a **semantic variant** of itself  
(shuffled, reordered, lightly perturbed).

The model is trained so that:
- same meaning → embeddings closer
- different meaning → embeddings farther

This **forces abstraction**.

As a result:
- Hindi sentences with similar meaning naturally fall into the same regions.

### Sentence-Level Classification (Not Token-Level)

We classify **entire sentences**, not individual words.

Why?
- Meaning transfers across languages better than syntax
- Sentence semantics are more universal than grammar rules

This makes cross-lingual generalization practical.

### Multiscript Tokenization (Engineering Necessity)
The model **can read Hindi characters**, but:
- it is never trained on Hindi data
- it never sees Hindi labels

Hindi capability is **emergent**, not supervised.

## What the System Actually Does

### Training phase
- Uses **only English data**
- Learns sentiment classification
- Learns language-independent sentence representations

### Inference phase
- Accepts:
  - English input 
  - Hindi input 
  - Code-mixed input (partial)
- Outputs a classification label

No translation. No retraining.

##  What makes it interesting

- Multilingual behavior **emerges from training strategy**
- Hindi support comes **without Hindi supervision**
- Adding a new language later requires **no retraining**
- Same system scales to other languages


## Real-World Relevance

This approach is useful when:
- multilingual data is scarce
- labeling non-English data is expensive
- fast deployment across languages is required

It mirrors how **modern multilingual systems are actually built**.

## One-Line Summary

> **A language-agnostic text classifier trained only on English that generalizes to Hindi by learning meaning instead of language.**

This project demonstrates that **multilingual intelligence is not about data quantity — it’s about abstraction**.

*- Shiv Prakash Verma*
