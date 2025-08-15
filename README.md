# TinyLlama LoRA Fine-Tuning on GSM8K

This repository demonstrates fine-tuning **TinyLlama-1.1B-Chat** using **LoRA** on the **GSM8K** dataset to improve step-by-step math reasoning.

---

## Table of Contents

- [Overview](#overview)  
- [Dataset](#dataset)  
- [Method](#method)  
- [Pipeline](#pipeline)  
- [Results](#results)  
- [Notes](#notes)  
- [License](#license)  

---

## Overview

Fine-tuning large language models can be resource-intensive.  
This project uses **LoRA (Low-Rank Adaptation)** and **4-bit quantization** to efficiently train TinyLlama for step-by-step math problem solving.

---

## Dataset

**GSM8K** is a dataset of ~8,500 grade-school math problems.  

Each example contains:  

- `question`: The math problem in natural language.  
- `answer`: Step-by-step reasoning leading to the final solution.

---

## Method

### Model

- TinyLlama-1.1B-Chat, compact and optimized for chat/reasoning tasks.

### Tokenizer

- Converts text into tokens the model can understand.

### Quantization

- 4-bit precision to reduce GPU memory usage.

### LoRA Fine-Tuning

- Fine-tunes only a small subset of model parameters, making training faster and more memory-efficient.

---

## Pipeline

### 1. Load Pretrained Model

Load TinyLlama in 4-bit precision with automatic device mapping.

### 2. Load Dataset

Import GSM8K and prepare questions and answers.

### 3. Tokenization

Format each entry as `Instruction / Response` and convert text into tokens.

### 4. Configure LoRA

Set up LoRA layers for efficient fine-tuning.

### 5. Training Setup

Define batch size, epochs, learning rate, gradient accumulation, and logging.

### 6. Fine-Tuning

Train the model on the tokenized dataset using Hugging Face `Trainer`.

### 7. Save Model

Save the fine-tuned model and LoRA adapters for inference or future tasks.

---

## Results

- Model solves GSM8K math problems step by step.  
- Produces human-readable reasoning.  
- Retains general language understanding while improving problem-solving abilities.

---

## Notes

- 4-bit quantization and LoRA allow training large models on small GPUs.  
- Instruction/Response formatting helps the model learn prompt structure.  
- This approach can be extended to other reasoning datasets.

---


