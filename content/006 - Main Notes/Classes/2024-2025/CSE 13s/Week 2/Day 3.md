
Class: [[CSE 13s]]
Subject: #computer-science 
Date: 2024-10-11
Teacher: *Dr. Veenstra*

# Functions

## Examples of Using Functions


## Assert
- used to report internal errors
### Code

```C
#include <assert.h>
#include <stdio.h>

int main(void) {
	int rows = 0, cols = 0;
	int conversions = scanf("%d %d\n", ), &rows, &cols);
	assert(conversions == 2);
	printf("rows = %d, cols = %d\n", rows, cols);
	return 0;
}
```

*Assertion*
- Essentially says, "I assert that conversions == 2 is true. Let me know when it is not."