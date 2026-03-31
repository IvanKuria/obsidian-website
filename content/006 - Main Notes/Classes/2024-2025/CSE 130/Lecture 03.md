---
title: "Lecture 03"
type: lecture
class: CSE 130
date: 2025-04-14
tags:
  - cs
  - operating-systems
---

# C Strings, Variables and Unix File IO

## C Strings
- a c string is a bunch of bytes ending with 0
### Problems
1. Need to move through the string to get it's length
2. Strings can't have zero bytes
	- i.e. ![[cse130-c-string-with-zero-bytes.png | 500]]

#### What is sizeof(t)?
- 10

#### What is strlen(t)?
- 3

### Static Keyword
``` c
int main(void) {
	static char *t;
	...

	return 0;
}
```

- it acts both as *a local scope var* and can be used as *"global storage"*
- like other [[global variables]], it gets initialized to 0(*0x00000000*)
