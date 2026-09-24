# Qaiser Mehdi

I measure what LLM inference actually costs, down to the GPU.

- **[qvunex_single.py](https://github.com/qaisermehdi3-coder/qvunex/blob/main/qvunex_single.py)**: one file, no install, no network code. Records cost per finished task, and a call whose cost is unknown is marked unknown, never counted as $0. For self-hosted vLLM, `--reconcile` checks your client's counts against the server's own counters, and `--gpu-rate` gives the cost per request at the load you actually ran. Both tested live on vLLM.
- **[GPU cost data](https://github.com/qaisermehdi3-coder/qvunex/tree/main/benchmarks/data)**: the same benchmark on T4, L4 and L40S, repeated. On one L40S, minutes apart, CUDA-graph timings repeated within 0.7% on average and eager timings moved up to 78%.
- **Reported in pydantic-ai, [#8704](https://github.com/pydantic/pydantic-ai/issues/8704)**: responses with no usage were recorded as $0 and slipped past spending limits. Confirmed by their triage.
- **Proposed in AgentMeasure, [#26](https://github.com/roy-tong/AgentMeasure/discussions/26)**: self-hosted servers as a known measurement limit, with the server-side way to close it, tested live.
- **[Cost audit](https://github.com/qaisermehdi3-coder/qvunex/blob/main/AUDIT.md)**: I run the meter on a day of your traffic and write up where the money goes.

Contact: qvunexaudit@gmail.com, or open an issue on [qvunex](https://github.com/qaisermehdi3-coder/qvunex/issues).
