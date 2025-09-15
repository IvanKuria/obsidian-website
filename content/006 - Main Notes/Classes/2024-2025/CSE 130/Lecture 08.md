Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-05-01
Teacher: **Dr. Veenstra 

# Client Server Model

## Marshaling
- coverts data into transferable formats between different systems

### Concerns
- integer sizes
	- i.e. *int32_t* vs *int64_t*
- endianness
- pointers(need swizzling/unswizzling)
![[Pasted image 20250501173525.png]]

## Buffered Communication & Intermediaries

- used when client/server aren't simultaneously available
	- i.e. *Email, Publish/Subscribe*
- intermediaries store and forward messages

### Modes
- *Push*: sender initiates
- *Pull*: receiver initiates
