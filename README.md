# Evaluating Pretrained Models using TOPSIS

## Overview
This project applies the **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** method to rank six pre-trained **open-source** conversational AI models based on multiple evaluation criteria. The evaluation considers factors such as response quality, inference time, and model size.

## Objectives
- Compare multiple conversational AI models on diverse metrics.
- Use **ROUGE scores** to measure text quality.
- Measure **inference time** and **model size** for efficiency evaluation.
- Apply **TOPSIS ranking** to find the best model based on multiple factors.

---

## Evaluation Metrics
Each model is evaluated based on the following criteria:

| Metric           | Description |
|-----------------|-------------|
| **ROUGE-1 F1**  | Measures unigram overlap between generated and ideal responses. |
| **ROUGE-2 F1**  | Measures bigram overlap for better fluency assessment. |
| **ROUGE-L F1**  | Measures longest matching sequence for structural similarity. |
| **Inference Time** | Measures how long the model takes to generate a response (lower is better). |
| **Model Size**  | Approximate storage size of the model (lower is better). |

**TOPSIS** is used to determine the best model by considering both **beneficial** (higher is better) and **non-beneficial** (lower is better) criteria.

---

## Models Evaluated
We selected six **open-source** conversational models:

1. **GPT-2** (`gpt2`)
2. **OPT-125M** (`facebook/opt-125m`)
3. **DialoGPT-small** (`microsoft/DialoGPT-small`)
4. **GPT-Neo-125M** (`EleutherAI/gpt-neo-125M`)
5. **BLOOM-560M** (`bigscience/bloom-560m`)
6. **Flan-T5 Small** (`google/flan-t5-small`)

Models are loaded and tested using **Hugging Face's Transformers library**.

---

## Sample Evaluation Prompts
Models are tested on diverse prompts, and their responses are compared to **ideal answers**.

### **Example Prompt 1:**
**Question:** "Tell me about the latest advancements in AI."  
**Ideal Answer:** "Recent advancements in AI include improvements in large language models like GPT-4, increased efficiency in reinforcement learning, and better multimodal understanding."

### **Example Prompt 2:**
**Question:** "What should I do if I get lost in a forest?"  
**Ideal Answer:** "If you get lost in a forest, stay calm and try to retrace your steps. Look for landmarks, conserve energy, and try to call emergency services if possible."

---

## How TOPSIS Works
1. Normalize the decision matrix.
2. Apply **weighted** criteria to balance different factors.
3. Compute **ideal (best) and negative ideal (worst) solutions**.
4. Calculate **distance to ideal and negative ideal**.
5. Compute **TOPSIS scores** and rank models accordingly.

---

## Results
The results are displayed in a table format, showing **model names, evaluation metrics, TOPSIS scores, and rankings**. The table is also **saved as a CSV file** (`model_evaluation_results.csv`).

### **Example Output Table:**
| Model | ROUGE-1 F1 | ROUGE-2 F1 | ROUGE-L F1 | Inference Time | Model Size | TOPSIS Score | Rank |
|--------|-----------|-----------|-----------|---------------|-----------|--------------|------|
| GPT-2 | 0.45 | 0.30 | 0.40 | 1.2s | 500MB | 0.78 | 1 |
| DialoGPT | 0.42 | 0.28 | 0.38 | 1.5s | 520MB | 0.72 | 2 |
| ... | ... | ... | ... | ... | ... | ... | ... |

---
## Contributor
Name: Kartik Sidana

