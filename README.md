# Qaiser Mehdi

I measure what LLM inference actually costs, down to the GPU.

- **[qvunex_single.py](https://github.com/qaisermehdi3-coder/qvunex/blob/main/qvunex_single.py)**: one file, no install, no network code. Records cost per finished task, and a call whose cost is unknown is marked unknown, never counted as $0. For self-hosted vLLM, `--reconcile` checks your client's counts against the server's own counters, and `--gpu-rate` gives the cost per request at the load you actually ran. Both tested live on vLLM.
- **[GPU cost data](https://github.com/qaisermehdi3-coder/qvunex/tree/main/benchmarks/data)**: the same benchmark on T4, L4, L40S and RTX 3090, repeated. On one L40S, minutes apart, CUDA-graph timings repeated within 0.7% on average and eager timings moved up to 78%.
- **Two vLLM servers on one GPU, measured**: an embedding model next to a chat model on one RTX 3090, with the startup error, the fix and the slowdown when both are busy. [Data](https://github.com/qaisermehdi3-coder/qvunex/tree/main/benchmarks/data/coloc-3090-2026-10-23), written up in [vllm#60599](https://github.com/vllm-project/vllm/issues/60599).
- **Reported in pydantic-ai, [#8704](https://github.com/pydantic/pydantic-ai/issues/8704)**: responses with no usage were recorded as $0 and slipped past spending limits. Fixed by the maintainers in [#9491](https://github.com/pydantic/pydantic-ai/pull/9491).
- **Merged in AgentMeasure, [#39](https://github.com/roy-tong/AgentMeasure/pull/39)**: self-hosted servers as a known measurement limit, with the server-side way to close it, tested live. It now runs in their conformance checks.
- **[Cost audit](https://github.com/qaisermehdi3-coder/qvunex/blob/main/AUDIT.md)**: I run the meter on a day of your traffic and write up where the money goes.

Contact: qvunexaudit@gmail.com, or open an issue on [qvunex](https://github.com/qaisermehdi3-coder/qvunex/issues).
