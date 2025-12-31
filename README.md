# Language-Agnostic Text Classifier  
> Train on English. Works on Hindi. No translation. No multilingual training.
> This project demonstrates that **multilingual intelligence is not about data quantity — it’s about abstraction**.
## Core Idea

> Languages look different, but **meaning is shared**.

Instead of teaching the model:
- “what English words mean”
we force it to learn:
- **what sentences mean**, independent of language
If a Hindi sentence expresses the same *idea* as an English one,  
their internal representations should be **close**.

### Language-Agnostic Semantic Learning  
The model is trained to focus on **semantics**, not surface words.
It learns:
- positivity vs negativity
- intent and sentiment
- meaning patterns
rather than memorizing English vocabulary.

### Contrastive Learning

During training, each English sentence is paired with a **semantic variant** of itself  
(shuffled, reordered, lightly perturbed).
The model is trained so that:
- same meaning → embeddings closer
- different meaning → embeddings farther
This **forces abstraction**.
As a result:
- Hindi sentences with similar meaning naturally fall into the same regions.
  
### Sentence-Level Classification
We classify **entire sentences**, not individual words.
Why?
- Meaning transfers across languages better than syntax
- Sentence semantics are more universal than grammar rules
This makes cross-lingual generalization practical.

### Multiscript Tokenization
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

## One-Line Summary

> **A language-agnostic text classifier trained only on English that generalizes to Hindi by learning meaning instead of language.**

## Usage
For using model visit: *[🤗Hugging Face](https://huggingface.co/wizardoftrap/language_agnostic_classifier)*

*- Shiv Prakash Verma*
