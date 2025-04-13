# Batching

## Objective

- Multiple request
- Trade-off between **throughput** (handling multiple request) and **latency** (responding to any one request)

## Single Request Generation

![Single Request Generation](../images/2_0.png)

## Multi Request Generation

![Multi Request Generation](../images/2_1.png)

- Padding tokens ensure consistent matrix shape.

## Throughput vs Latency

- Additional Info (KA)
  - Definitions:
    - **Latency**: The overall time it takes for the model to generate the full response for a user.
    - **Throughput**: The number of output tokens per second an inference server can generate across all users and requests.
  - Source: [Databricks article: LLM Inference Performance Engineering: Best Practices](https://www.databricks.com/blog/llm-inference-performance-engineering-best-practices)

- Optimized for latency
  - Minimize wait time for individual requests
  ![Optimized for latency](../images/2_2.png)
  - My understanding (KA):
    - Latency = $1 + 1.2 + 1.4$ = $3.6$ seconds
      - Average Latency: $3.6/3$ = $1.2$ seconds/request
    - Throughput:
      - 3 seconds overall for 3 requests
      - Hence throughput = 3/3 = 1 requests/second

- Prioritize throughput over latency (Batching)
  - We wait for requests to create batch
  ![Prioritize throughput over latency](../images/2_3.png)
  - My understanding (KA):
    - Latency = $2.4 + 1.6 + 1$ = $5$ seconds
      - Average Latency: $5/3$ = $1.67$ seconds/request
    - Throughput:
      - $2.4$ seconds overall for 3 requests
      - Hence thoughput = $3/2.4$ = $1.25$ requests/second

- We'll study the effect of batch size on throughput vs latency
  - In the notebook batch size are varied in terms of power of 2.

- Objective:
  - Increase throughput with trade-off in latency.

## Notebook

- [Jupyter Notebook](../code/Lesson_2-Batching.ipynb)
- Padding and Truncation details available on [Hugging Face](https://huggingface.co/docs/transformers/v4.35.2/en/pad_truncation)
- Observation: Padded tokens are not assigned attention
- ?? position_ids are assigned 1 for padded tokens
  - What purpose does it serves?
- ?? Unlike the computation shown [above](#throughput-vs-latency), there's no consideration of "idle" time for latency computation.
