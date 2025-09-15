Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-04-30
Teacher: **Dr. Veenstra

# Modularity

## Soft Modularity

### Function Calls
- implement modularity by dividing code into named procedures
- *errors can propagate between modules!*
	- i.e
		- called function never returns(function crashes)
		- called function writes values to the wrong location
#### Soft Modularity invites error propagation
- this can be limited by using [[constrained languages]] 
##### Solution
- *enforced modularity*
- but can this be done in a high level language?

## Hard Modularity
- essentially use explicit messages for interactions between modules
	- *client*: initiates a request
	- *server*: responds to the request with a *response* or *reply*
### Advantages
- independent memory and interpreters
- less [[fate sharing]], more fault containment

### Communication
- makes use of a "wire" (real or virtual); models like a web browser/server

## Remote Procedure Call (RPC)
- essentially acts like a local function call, but over a network
	- i.e. calling *processPayment()* from Stripe's API
- uses stubs to pack/unpack arguments and communicate

![[Pasted image 20250501132424.png]]
[Reference](https://www.youtube.com/watch?v=S2osKiqQG9s) 
### Benefits
- familiar interface for developers
- reduces [[fate sharing]]

### Limitations
- failure modes (hung call, server down)
- slower than local calls due to :
	- network round trips
	- [[marshaling]](serialization) overhead
- call-by-reference doesn't work well

## RPC Error Handling

### At Least Once
- retries until acknowledgement
#### Risks
- duplicate side effects
- requires [[idempotent]] operations

### At Most Once
- one try only; avoids duplicates
#### Risks
- may silently fail

### Exactly Once
- retries + tracking
#### Risks
- most difficult to implement
