---
title: "Concurrency"
type: definition
domain: operating-systems
aliases: [concurrent]
tags:
  - definition
---

Multiple threads taking turns executing on the same hardware resource. Concurrency creates the illusion of simultaneous execution through interleaving, but only one thread runs at any given instant on a single core.

## Context

Concurrency is essential in operating systems and server design. For example, a web server handles thousands of requests concurrently by switching between them, even on a single CPU core. This differs from [[parallelism]], where multiple threads truly execute at the same time on different cores.

## See Also

- [[parallelism]]
- [[throughput]]
- [[latency]]
