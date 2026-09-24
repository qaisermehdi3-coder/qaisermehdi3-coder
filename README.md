# Qaiser Mehdi

I measure what LLM and GPU work actually costs.

- **[qvunex_single.py](https://github.com/qaisermehdi3-coder/qvunex/blob/main/qvunex_single.py)**: one file, no install, no network code. Records cost per finished task. A call whose cost is unknown is marked unknown, never counted as $0.
- **[GPU cost data](https://github.com/qaisermehdi3-coder/qvunex/tree/main/benchmarks/data)**: the same benchmark on T4, L4 and L40S, rerun to see which numbers repeat and which don't.
- **Reported in pydantic-ai, [#8704](https://github.com/pydantic/pydantic-ai/issues/8704)**: responses with no usage were recorded as $0 and slipped past spending limits. Confirmed by their triage.
- **[Cost audit](https://github.com/qaisermehdi3-coder/qvunex/blob/main/AUDIT.md)**: I run the meter on a day of your traffic and write up where the money goes.

Contact: open an issue on [qvunex](https://github.com/qaisermehdi3-coder/qvunex/issues).
