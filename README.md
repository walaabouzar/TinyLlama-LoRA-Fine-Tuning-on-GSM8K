# TinyLlama LoRA Fine-Tuning on GSM8K
This repository demonstrates fine-tuning TinyLlama-1.1B-Chat using LoRA on the GSM8K dataset to improve step-by-step math reasoning.
Overview

The goal of this project is to teach TinyLlama to solve grade-school math problems in a step-by-step manner. We leverage LoRA to fine-tune the model efficiently without modifying all of its weights, making it possible to train even on limited GPU resources.

Features

Fine-tuning TinyLlama-1.1B-Chat for reasoning tasks.

Efficient 4-bit quantization to save GPU memory.

Uses LoRA to adapt only a subset of parameters for fast and low-cost fine-tuning.

Prepares GSM8K data in Instruction / Response format for optimal learning.

Dataset

GSM8K: A collection of ~8,500 grade-school math problems.

Each entry contains:

question: The math problem text.

answer: Step-by-step solution with final answer.

Ideal for training models on reasoning and multi-step problem solving.

Pipeline

Load the pretrained TinyLlama model in 4-bit precision.

Load and tokenize GSM8K into Instruction/Response format.

Configure LoRA for efficient fine-tuning.

Set training parameters: batch size, learning rate, epochs, gradient accumulation, etc.

Fine-tune the model using Hugging Face Trainer.

Save the trained LoRA adapters for later inference.

Notes

Using 4-bit quantization + LoRA allows training large models on smaller GPUs.

Instruction/Response formatting helps the model learn the structure of prompts.

The fine-tuned model can be used for reasoning tasks or extended to other datasets.
