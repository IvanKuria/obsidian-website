Class: [[CSE 120]]
Subject: #computer-science #computer-architecture 
Date: 2025-05-05
Teacher: **Prof. Nath

# RISC-V Cont

## Functions in RISC-V

*jal*: jump and link. used to jump to a function address from the current PC(program counter)

*ret*: direct PC to address stored in register x1

### Example
**assume label foo is stored at address 8000 and bar is stored at address 8080**

#### C code

``` c
void bar()
{
	return;
}

void foo() 
{
	bar();
	// rest of foo code
}
```

#### RISC-V Implementation
``` c
// address  instructions
8000(foo):  jal bar; // x1 = 8004(PC + 4)
8004:       // PC jumps back here afrer executing function bar

...

9080(bar):  ret; // PC jumps to value in x1 = 8004
```

