# Introduction

## Objectives

- Efficiently serve LLM applications to large number of users
  - Relevant when you host open-source LLM
  - Scenario: In spite of using powerful GPUs, hosted LLM serving one request at a time.
- Techniques
  - Vectorization
    - Allows handling of request from multiple users
    - Multiple fine-tuned model at same time
  - KV Caching
- Latency
  - Time taken by users to receive response to the prompt
- Throughput
  - Rate of server processing requests
- Auto-Regressive model
  - Generating one token at a time
  - Learn KV caching to reduce latency for subsequent tokens
- Batch prompts and continuous Batching
- LoRA
