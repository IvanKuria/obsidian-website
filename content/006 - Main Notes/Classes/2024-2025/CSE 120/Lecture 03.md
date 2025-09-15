Class: [[CSE 120]]
Subject: #computer-science #computer-architecture 
Date: 2025-04-27
Teacher: **Prof. Nath

# RISC-V Cont

## Arrays in RISC-V

### Example 1

#### C code
``` c
a = b + pow[7];
```

**Assume 
	pow2 base address is in x3
	pow2's element size is 4B(1 word)**

#### RISC-V code
``` c
lw x4, 28(x3)   // x4 = Memory[pow2[7]]
add x2, x1, x4  // a = b + pow2[7]
```


### Example 2

#### C code
``` c
a[i] = b + c
```

**Assume: 
	i in x3,
	b in x1,
	c in x2, 
	a in x4, element size is 8B**

#### RISC-V code
``` c
add  x5, x1, x2   // x5 = b + c  

slli x6, x3, 3    // x6 = 8 * i

add  x6, x4, x6   // x6 = a + 8*i

sd   x5, 0(x6)    // Memory[a[i]] = b+c

```


## RISC-V Conditional Branch

### beq
- essentially branch if equal

``` c
beq reg1, reg2, label1
```

- consider the code:
#### SB Instruction Format
``` c
if (a == b) goto L1;
a = a + c;
L1: // continue
```

- here's how it would look like in RISC-V

#### RISC-V
``` c
// address    instruction
8080:         beq x1, x2, L1
8084:         add x1, x3, x4

...

8092(L1)      Continue
```

### bne
- branch if *not* equal

``` c
bne reg1, reg2, label
```

#### SB Instruction Format
``` c
if (a != b) goto L1;
a = a + c;
L1: // continue
```

#### RISC-V code
``` c
bne s0, s1, L1
add s0, s0, s2

...

L1: // continue
```

## While Loop

### Example 

#### C code
``` c
while (a[i] == k)
{
	i = i + j;
}
```

**assume: 
	i  = s0,
	j = s1, 
	k = s2,
	a[i] holds word size elements(4B)**
#### RISC-V code
``` c
j Cond                // goto Cond

Loop:
	add s0, s0, s1    // i = i + j

Cond:
	slli t0, s0, 2    // t0 = 4 * j
	add t1, t0, s3    // t1 = &(a[i])
	lw t2, 0(t1)      // t2 = a[i]
	beq t2, s2, Loop  // goto Loop if (a[i] == k)

Exit:
```

## For Loop

### Example

#### C code
``` c
int result = 0;
for (i = 0; i < n; i ++)
{
	result += a[i];
}
```

#### RISC-V Pseudo Code

``` c
int result = 0;
int i;
i = 0;

loop:
	result += a[i];

test:
	if (i < n) goto lopp;
```

#### RISC-V code

``` c
// a0 = a(at start)
// a1 = n
// a0 = result(at end)
// t0 = i

sum_array:
	add a2, a0, x0 // save a before overwriting it
	add a0, x0, x0 // result = 0
	add t0, x0, x0 // i = 0
	j test

loop:
	slli t1, t0, 2  // t1 = i * 4
	add t1, a2, t1  // &(a[i])
	lw t1, 0(t1)    // a[i]
	add a0, t1, a0  // result += a[i]
	addi t0, t0, 1  // i ++

test:
	blt t0, a1, loop  // if (i < n) goto loop

```



