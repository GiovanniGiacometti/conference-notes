# Post-Training Small Language Models - the adventures of a practitioner

https://2025.pycon.it/en/event/post-training-small-language-models-the-adventures-of-a-practitioner

Speaker: [Stefano Fiorucci](https://www.linkedin.com/in/stefano-fiorucci/)

---

Why finetuning?
- fun
- experimentation

---

1. Pretraining

Very costly. It produces a Base Model that can just produce text.

2. Supervised Fine-tuning

Teach the model to follow instructions

3. Preference alignment

It produces a Chat Model

---

Do I need fine tuning?

Can do vibecheck but better use an evaluation pipeline

- popular benchmarks
- custom benchmarks (your bench from huggingface)

---

How to choose the model to train?

Base vs Instruct
Check if popular in fine tuning tasks

---

Many training libraries

---

### Preference Alignment

PPO algorithm, uses RL

hard to do at home

-> DPO (direct preference optimization)

Simplified probelm
classification problem (no reward model, leaving some performance on the table)

2 answers, one is better than the other (not necessarily much better but more fluent)

---

Synthetic data

gpu: Prime Intellect

---

Memoy efficient training -> 

LORA and its evolution QLORA

Spectrum 
Basic you only train a small part of the model

It achieves better results than LORA 

---

Model merging

Interpolate weights of two models to get a simple new model
It works well, doens't even need GPU (and a lot of RAM)

---

Reasoning Models / GRPO (used by deepseek)

Reasoning -> chain of thought, the final answer is based on those

pretraining has diminishing returns
but o1 showed that you can improve performance both increasing
- the training time compute
- test time compute

GRPO has the model generate a group of answers and give reward to those above the average performance

num_generations usually starts from 8