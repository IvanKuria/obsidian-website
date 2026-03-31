---
title: "Idempotent"
type: definition
domain: operating-systems
aliases: [idempotency, idempotence]
tags:
  - definition
---

An operation in mathematics or computer science that can be applied multiple times without changing the result beyond the initial application. Formally, $f(f(x)) = f(x)$.

## Context

Idempotency is critical in distributed systems and API design. For example, an HTTP PUT request should be idempotent: sending the same PUT request twice should produce the same server state as sending it once. This property makes systems more resilient to retries and network failures.

## See Also

- [[fate sharing]]
- [[concurrency]]
