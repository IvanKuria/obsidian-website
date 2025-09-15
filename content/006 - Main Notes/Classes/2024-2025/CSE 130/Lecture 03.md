Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-04-14
Teacher: **Dr. Veenstra

# C Strings, Variables and Unix File IO

## C Strings
- a c string is a bunch of bytes ending with 0
### Problems
1. Need to move through the string to get it's length
2. Strings can't have zero bytes
	- i.e. ![[Pasted image 20250414072419.png | 500]]

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