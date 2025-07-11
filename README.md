# Efficiently Serving LLMs

## About

This repository contains

- [Course notes](#course-contents)
- [Assignments](#assignments)
- Additional resources (collected for better understanding of the concepts)

## Course Information

- Instructor: Travis Addair
- [Course Website](https://www.deeplearning.ai/short-courses/efficiently-serving-llms/)

## Course Contents

|#|     Lesson  |   Description   |
|-|-------------|-----------------|
|0|[Introduction](./notes/Lesson_0.md)|<ul><li>Existing inefficiencies in serving open-source self-hosted LLMs</li><li>Techniques implemented at Predibase to efficiently serve LLM request</li><li>Parameters for evaluating efficiency of LLM serving requests</li></ul>|
|1|[Text Generation](./notes/Lesson_1.md)|<ul><li>Text generation using auto-regressive models</li><li>KV caching</li></ul>|
|2|[Batching](./notes/Lesson_2.md)|<ul><li>Handling multiple requests</li><li>Throughput vs Latency</li></ul>|
|3|[Continuous Batching](./notes/Lesson_3.md)|<ul><li>Continuous Batching benefits over Synchronous Batching</li><li>Implementation explained with merge and filter of batches along with visualization</li></ul>|
|4|[Quantization](./notes/Lesson_4.md)|<ul><li>Floating point representations explained</li><li>Zero-point quantization</li></ul>|
|5|[Low-Rank Adaptation](./notes/Lesson_5.md)|<ul><li>LoRA explained</li><li>Benefits of LoRA over normal fine-tuning</li></ul>|
|6|[Multi-LoRA Inference](./notes/Lesson_6.md)|<ul><li>End-to-end system with many fine-tuned models (Multiple LoRA adapters) with same base model</li><li>Vector based implementation of multiple LoRA adapters vs loop based implementation</li></ul>|
|7|[LoRAX](./notes/Lesson_7.md)|<ul><li>Display working of previous lessons in LoRAX</li></ul>|

## Assignments

|Lesson|         Assignment        |   Description   |
|-------|---------------------------|-----------------|
|#1|[Text Generation](./notes/Lesson_1.md#notebook)|<ul><li>Improving time taken to generate subsequent tokens using KV caching</li></ul>|
|#2|[Batching](./notes/Lesson_2.md#notebook)|<ul><li>Throughput vs Latency trade-off experiment with different batch sizes</li></ul>|
|#3|[Continuous Batching](./notes/Lesson_3.md#notebook)|<ul><li>Comparison with Synchronous Batching</li><li>Helper functions from previous lessons written in [helpers.py](./code/helpers.py)</li></ul>|
|#4|[Quantization](./notes/Lesson_4.md#notebook)|<ul><li>Continuous batching using zero-point quantization</li><li>Helper functions of [helpers.py](./code/helpers.py) improved in [utils.py](./code/utils.py)</li><li>Added function to generate responses using continuous batching in [utils.py](./code/utils.py)</li></ul>|
|#5|[Low-Rank Adaptation](./notes/Lesson_5.md#notebook)|<ul><li>LoRA implemented on a toy model by replacing linear layer with LoRA layer</li></ul>|
|#6|[Multi-LoRA](./notes/Lesson_6.md#notebook)|<ul><li>Improved [previous lesson's implementation](./notes/Lesson_5.md#notebook) with multiple LoRAs</li><li>Comparison of average latency between vectorized and loop based implementations</li></ul>|
|#7|[LoRAX](./notes/Lesson_7.md#notebook)|<ul><li>Working of previous lessons on LoRAX serverless shared endpoint</li><li>Deployment name: mistral-7b, **Model**: mistralai/Mistral-7B-v0.1</li><li>Shown improvement in NER task on usage of adapter along with base model</li></ul>|

## Python Environment

- Python: 3.11
- pip install libraries listed in [requirements.txt](./code/requirements.txt)

## Certificate

- [Course Completion Certificate](https://kaushikacharya.github.io/assets/certificates/DeepLearning_ai_Efficiently_Serving_LLMs.pdf)
- Issued on May 2025

## Related Courses

Visit my [Github page](https://kaushikacharya.github.io/courses/#machine-learning--deep-learning) for other Generative AI courses.
