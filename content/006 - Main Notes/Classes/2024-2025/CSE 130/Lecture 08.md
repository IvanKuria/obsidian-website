---
title: "Lecture 08"
type: lecture
class: CSE 130
date: 2025-05-01
tags:
  - cs
  - operating-systems
---

# Client Server Model

## Marshaling
- coverts data into transferable formats between different systems

### Concerns
- integer sizes
	- i.e. *int32_t* vs *int64_t*
- endianness
- pointers(need swizzling/unswizzling)
![[cse130-marshaling-concerns.png]]

## Buffered Communication & Intermediaries

- used when client/server aren't simultaneously available
	- i.e. *Email, Publish/Subscribe*
- intermediaries store and forward messages

### Modes
- *Push*: sender initiates
- *Pull*: receiver initiates
