# Oracle SWE Intern — Technical Interview Prep

  

> **Date**: Feb 17, 2026 @ 7 PM

> **Role**: SWE Intern, Customer Success Services (CSS)

> **Intel source**: Recruiter notes from a previous candidate on the **same team**

  

---

  

## What the Recruiter Told You

  

The interviewer left these notes about the candidate who passed:

- "Sliding window + deque"

- "Clear dry run"

- "Removing out of window"

- "REST APIs, SQL, React"

- "Docker, Kubernetes"

- "Node.js Dockerfile"

- "Database indexing"

- "Normal form"

- "Pods, containers"

- "Subarrays"

  

The previous candidate **passed even though they didn't fully implement the Dockerfile** — their problem-solving and working-things-out approach helped more.

  

**Translation**: This interview has two parts — (1) a sliding window + deque LeetCode problem, and (2) systems/practical questions. They care about **how you think** more than perfect syntax.

  

---

  

## PART 1: LeetCode — Sliding Window + Deque

  

### Priority #1: LC 239 — Sliding Window Maximum (MOST LIKELY)

  

> **LeetCode**: https://leetcode.com/problems/sliding-window-maximum/

> **NeetCode solution**: https://neetcode.io/solutions/sliding-window-maximum

> **Video walkthrough**: Search YouTube for "NeetCode Sliding Window Maximum" (his NeetCode 150 video)

> **Algo.monster deep-dive**: https://algo.monster/liteproblems/239

  

**Why this is almost certainly the problem**: Every single clue matches — "sliding window + deque", "removing out of window", "subarrays", "clear dry run". This is THE canonical monotonic deque problem.

  

**Pattern — Monotonic Decreasing Deque (stores INDICES, not values)**:

1. Remove indices from **front** if outside window (`i - k`)

2. Remove indices from **back** while their values <= current value

3. Push current index to back

4. Front of deque = maximum for current window

  

**Complexity**: O(n) time, O(k) space

  

**Python solution to memorize**:

```python

from collections import deque

  

def maxSlidingWindow(nums, k):

result = []

dq = deque() # stores indices

  

for i in range(len(nums)):

# 1. Remove front if out of window

while dq and dq[0] < i - k + 1:

dq.popleft()

  

# 2. Remove back if smaller than current

while dq and nums[dq[-1]] <= nums[i]:

dq.pop()

  

# 3. Add current index

dq.append(i)

  

# 4. Record answer once window is full

if i >= k - 1:

result.append(nums[dq[0]])

  

return result

```

  

**Dry Run — Practice This Out Loud!**

```

Input: [1, 3, -1, -3, 5, 3, 6, 7], k = 3

Expected: [3, 3, 5, 5, 6, 7]

  

i=0: val=1 deque=[] -> add 0 -> deque=[0]

i=1: val=3 1<=3 pop 0 -> add 1 -> deque=[1]

i=2: val=-1 -1<=3? no -> add 2 -> deque=[1,2] -> window full -> ans=[3]

i=3: val=-3 front=1, 3-1=2<3 ok. -3<=-1? no -> add 3 -> deque=[1,2,3] -> ans=[3,3]

i=4: val=5 front=1, 4-1=3>=3 -> pop 1. -3<=5 pop 3, -1<=5 pop 2 -> add 4 -> deque=[4] -> ans=[3,3,5]

i=5: val=3 front=4, 5-4=1<3 ok. 3<=5? no -> add 5 -> deque=[4,5] -> ans=[3,3,5,5]

i=6: val=6 front=4, 6-4=2<3 ok. 3<=6 pop 5, 5<=6 pop 4 -> add 6 -> deque=[6] -> ans=[3,3,5,5,6]

i=7: val=7 front=6, 7-6=1<3 ok. 6<=7 pop 6 -> add 7 -> deque=[7] -> ans=[3,3,5,5,6,7]

```

  

---

  

### Priority #2: LC 1438 — Longest Continuous Subarray With Absolute Diff <= Limit

  

> **LeetCode**: https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/

> **Algo.monster**: https://algo.monster/liteproblems/1438

  

**Why**: Medium difficulty, "subarrays", uses deque — more intern-appropriate label. Could be asked instead of 239.

  

**Pattern**: Two deques — one monotonic increasing (min tracker), one monotonic decreasing (max tracker). Expand window right; shrink from left when `max - min > limit`.

  

```python

from collections import deque

  

def longestSubarray(nums, limit):

max_dq = deque() # decreasing (tracks max)

min_dq = deque() # increasing (tracks min)

left = 0

result = 0

  

for right in range(len(nums)):

while max_dq and nums[max_dq[-1]] <= nums[right]:

max_dq.pop()

while min_dq and nums[min_dq[-1]] >= nums[right]:

min_dq.pop()

max_dq.append(right)

min_dq.append(right)

  

while nums[max_dq[0]] - nums[min_dq[0]] > limit:

left += 1

if max_dq[0] < left: max_dq.popleft()

if min_dq[0] < left: min_dq.popleft()

  

result = max(result, right - left + 1)

  

return result

```

  

**Complexity**: O(n) time, O(n) space

  

---

  

### Priority #3: LC 1696 — Jump Game VI

  

> **LeetCode**: https://leetcode.com/problems/jump-game-vi/

  

**Why**: DP + deque optimization, medium difficulty, tests "removing out of window"

  

**Pattern**: `dp[i] = nums[i] + max(dp[j])` for `j` in `[i-k, i-1]`. Use monotonic deque to get max dp value in k-sized window.

  

```python

from collections import deque

  

	def maxResult(nums, k):
	
		n = len(nums)
		
		dp = [0] * n
		
		dp[0] = nums[0]
		
		dq = deque([0]) # stores indices, decreasing by dp value
	
	  
	
		for i in range(1, n):
		
		# Remove front if out of window
		
		while dq and dq[0] < i - k:
		
		dq.popleft()
		
		  
		
		# Best we can do reaching index i
		
		dp[i] = nums[i] + dp[dq[0]]
		
		  
		
		# Maintain decreasing deque
		
		while dq and dp[dq[-1]] <= dp[i]:
		
		dq.pop()
		
		dq.append(i)
		
		  
		
		return dp[-1]

```

  

**Complexity**: O(n) time, O(k) space

  

---

  

### Backup: LC 862 — Shortest Subarray with Sum at Least K

  

> **LeetCode**: https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/

  

**Pattern**: Build prefix sums. Monotonic deque stores indices in increasing prefix-sum order. For each j, pop front while `prefix[j] - prefix[front] >= K`.

  

```python

from collections import deque

  

def shortestSubarray(nums, k):

n = len(nums)

prefix = [0] * (n + 1)

for i in range(n):

prefix[i + 1] = prefix[i] + nums[i]

  

dq = deque()

result = float('inf')

  

for j in range(n + 1):

# Check if current prefix - front prefix >= k

while dq and prefix[j] - prefix[dq[0]] >= k:

result = min(result, j - dq.popleft())

  

# Maintain increasing deque of prefix sums

while dq and prefix[dq[-1]] >= prefix[j]:

dq.pop()

dq.append(j)

  

return result if result != float('inf') else -1

```

  

---

  

### Key Deque Pattern — Memorize This Template

  

```

deque stores INDICES, not values

for each i:

1. while front out of window -> popleft

2. while back value <= current -> pop (or >= for min-deque)

3. push i to back

4. answer = value at front

```

  

**Why deque?** O(1) operations on both ends. Regular queue only pops from front; stack only pops from back. Deque gives you both, which is exactly what you need for maintaining a monotonic window.

  

---

  

## PART 2: Docker

  

### Video Resources

- **Fireship — Docker in 100 Seconds**: https://youtu.be/Gjnup-PuquQ (~2 min overview)

- **Fireship — Learn Docker in 7 Easy Steps**: https://fireship.io/lessons/docker-basics-tutorial-nodejs/

- **Docker official Node.js guide**: https://docs.docker.com/guides/nodejs/

  

### Node.js Dockerfile — Memorize This

  

```dockerfile

# Stage 1: Build

FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm ci --only=production

COPY . .

  

# Stage 2: Production

FROM node:20-alpine

WORKDIR /app

COPY --from=builder /app .

USER node

EXPOSE 3000

CMD ["node", "server.js"]

```

  

### Line-by-Line Talking Points

  

| Line | Why |

|------|-----|

| `FROM node:20-alpine` | Alpine Linux base = ~5MB vs ~900MB for full image |

| `AS builder` | Multi-stage build — build deps in one stage, copy only what's needed to production |

| `WORKDIR /app` | Sets working directory inside container (creates if doesn't exist) |

| `COPY package*.json ./` | Copy package.json + package-lock.json FIRST for Docker layer caching |

| `RUN npm ci` | `ci` is faster + deterministic (uses lockfile exactly). `install` can update lockfile |

| `COPY . .` | Copy source code AFTER installing deps (so code changes don't bust dep cache) |

| `USER node` | Run as non-root user (uid 1000) for security |

| `EXPOSE 3000` | Documents the port — doesn't actually publish it |

| `CMD ["node", "server.js"]` | Exec form (not shell form) — signals go directly to node process |

  

### Also Know: `.dockerignore`

```

node_modules

.git

.env

npm-debug.log

```

  

### Key Concepts to Mention

- **Image vs Container**: Image is blueprint, container is running instance

- **Layer caching**: Each Dockerfile instruction creates a layer; unchanged layers are cached

- **Multi-stage builds**: Reduce final image size by discarding build tools

- **`docker build -t myapp .`** builds the image

- **`docker run -p 3000:3000 myapp`** runs it, mapping host:container ports

  

---

  

## PART 3: Kubernetes

  

### Video Resources

- **Fireship — Kubernetes in 100 Seconds**: Search YouTube "Fireship Kubernetes 100 Seconds" (~2 min overview)

- **TechWorld with Nana — K8s Crash Course for Absolute Beginners**: https://youtube.com/watch?v=s_o8dwzRlu4 (~1 hour, comprehensive)

- **K8s official interactive tutorial**: https://kubernetes.io/docs/tutorials/kubernetes-basics/

  

### Pods vs Containers (The #1 Question They'll Ask)

  

| Concept | What it is | Analogy |

|---------|-----------|---------|

| **Container** | Single isolated process (a Docker container) | One app in a box |

| **Pod** | Smallest K8s unit; wraps 1+ containers sharing network/storage | A house with rooms |

| **Deployment** | Manages pod replicas + rolling updates | A property manager |

| **Service** | Stable IP/DNS to route traffic to pods | A phone number that forwards to whoever's on duty |

| **Namespace** | Logical cluster subdivision | Different departments |

| **HPA** | Horizontal Pod Autoscaler — scales replicas on CPU/memory | Automatic hiring/firing based on workload |

  

### Architecture (Know This Diagram)

  

```

Control Plane (Master)

├── API Server ← all communication goes through here

├── Scheduler ← decides which node runs a pod

├── Controller Mgr ← ensures desired state = actual state

└── etcd ← key-value store (cluster state)

  

Worker Nodes

├── kubelet ← agent that manages pods on this node

├── kube-proxy ← handles networking/load balancing

└── Container Runtime (Docker/containerd)

```

  

### When Multiple Containers in One Pod?

**Sidecar pattern** — containers that need to share:

- Same network namespace (communicate via `localhost`)

- Same storage volumes (e.g., log files)

- Example: app container + logging agent, app + service mesh proxy (Envoy)

  

### Key Commands to Know

```bash

kubectl get pods # list all pods

kubectl get deployments # list deployments

kubectl describe pod <name> # detailed pod info

kubectl logs <pod-name> # view pod logs

kubectl apply -f deploy.yaml # apply a manifest

kubectl scale deployment myapp --replicas=3

```

  

---

  

## PART 4: REST APIs

  

### HTTP Methods

  

| Method | Purpose | Idempotent? | Safe? | Example |

|--------|---------|-------------|-------|---------|

| GET | Read resource | Yes | Yes | `GET /users/123` |

| POST | Create resource | **No** | No | `POST /users` |

| PUT | Replace resource | Yes | No | `PUT /users/123` |

| PATCH | Partial update | No | No | `PATCH /users/123` |

| DELETE | Remove resource | Yes | No | `DELETE /users/123` |

  

**Idempotent** = calling it multiple times has the same effect as calling it once

  

### Status Codes (Memorize These 10)

  

| Code | Meaning | When |

|------|---------|------|

| 200 | OK | Successful GET/PUT/PATCH |

| 201 | Created | Successful POST |

| 204 | No Content | Successful DELETE |

| 400 | Bad Request | Invalid syntax from client |

| 401 | Unauthorized | Not authenticated |

| 403 | Forbidden | Authenticated but no permission |

| 404 | Not Found | Resource doesn't exist |

| 409 | Conflict | Version conflict (optimistic locking) |

| 500 | Internal Server Error | Server crashed |

| 503 | Service Unavailable | Temporary overload/maintenance |

  

### Design Best Practices

1. Use **nouns** not verbs: `/users` not `/getUsers`

2. Use **plurals**: `/users/123` not `/user/123`

3. HTTP methods ARE the verbs — don't put actions in URLs

4. **Version your API**: `/v1/users`

5. Use **query params** for filtering: `/users?role=admin&page=2`

6. Return **meaningful error bodies**: `{ "error": "Email already exists" }`

  

---

  

## PART 5: Database Indexing

  

### Video Resources

- **Hussein Nasser — Database Indexing Explained**: Search YouTube "Hussein Nasser database indexing"

- **PlanetScale — B+ Trees**: https://planetscale.com/blog/btrees-and-database-indexes

- **Built In — How B-Tree Indexing Works**: https://builtin.com/data-science/b-tree-index

  

### B-Tree Index — How It Works

  

```

[50] ← root

/ \

[20,30] [60,80] ← internal nodes

/ | \ / | \

[10] [25] [35] [55] [70] [90] ← leaf nodes (data pointers)

```

  

- Self-balancing tree where each node has many children (100s in practice)

- O(log n) search, insert, delete

- **Why B-tree over binary tree?** Fewer levels = fewer disk reads. A B-tree with branching factor 100 needs only 3 levels for 1 million rows.

  

### When to Index

  

| DO Index | DON'T Index |

|----------|-------------|

| Primary keys (automatic) | Low-cardinality (boolean, gender) |

| Foreign keys (JOIN columns) | Small tables (<1000 rows) |

| WHERE clause columns | Write-heavy columns |

| High-cardinality (email, user_id) | Rarely queried columns |

| Range queries (BETWEEN, >, <) | Already part of composite index |

  

### Trade-offs (CRITICAL Interview Answer)

> "Indexes speed up reads by 10-100x because the B-tree lets us find rows in O(log n) instead of scanning the whole table. The trade-off is slower writes — every INSERT, UPDATE, or DELETE must also update the index and potentially rebalance the tree. So you index selectively: high-read, low-write columns that appear in WHERE clauses."

  

### Types of Indexes

- **B-tree** (default in PostgreSQL/MySQL): Range queries, equality, sorting

- **Hash index**: O(1) equality only — no range support

- **GIN/GiST**: Full-text search, JSON, arrays (PostgreSQL)

- **Composite index**: Multiple columns — order matters! `(city, date)` helps `WHERE city = 'NYC'` but NOT `WHERE date = '2024-01-01'` alone

  

---

  

## PART 6: Database Normalization

  

### Video Resources

- **Decomplexify — Learn Database Normalization (1NF-5NF)**: https://youtu.be/GFQaEYEc8_8 (~30 min, excellent examples)

- **FreeCodeCamp written guide**: https://www.freecodecamp.org/news/database-normalization-1nf-2nf-3nf-table-examples/

- **DigitalOcean guide**: https://www.digitalocean.com/community/tutorials/database-normalization

  

### The Four Normal Forms

  

#### 1NF — Atomic Values

Each cell has a single, indivisible value. No arrays or repeating groups.

  

| BAD (violates 1NF) | | GOOD (1NF) | |

|---|---|---|---|

| StudentID | Phones | StudentID | Phone |

| 1 | "555-1234, 555-5678" | 1 | 555-1234 |

| | | 1 | 555-5678 |

  

#### 2NF — No Partial Dependencies

Must be in 1NF. No non-key attribute depends on only PART of a composite key.

  

| BAD (violates 2NF) — composite key is (StudentID, CourseID) | | |

|---|---|---|

| StudentID | CourseID | StudentName |

| 1 | CS101 | "Alice" |

  

`StudentName` depends only on `StudentID`, not the full key. Fix: move to separate `Students` table.

  

#### 3NF — No Transitive Dependencies

Must be in 2NF. No non-key attribute depends on another non-key attribute.

  

| BAD (violates 3NF) | | |

|---|---|---|

| StudentID | InstructorID | InstructorEmail |

  

`InstructorEmail` depends on `InstructorID` (not on `StudentID`). Fix: move to `Instructors` table.

  

#### BCNF — Boyce-Codd Normal Form

For every functional dependency X -> Y, X must be a superkey. Stricter than 3NF.

  

### Quick Normalization Example

  

**Denormalized**: `Orders(OrderID, CustomerName, CustomerEmail, ProductName, ProductPrice)`

  

**3NF**:

- `Customers(CustomerID, Name, Email)`

- `Products(ProductID, Name, Price)`

- `Orders(OrderID, CustomerID, ProductID, Quantity)`

  

**Why?** Eliminates update anomalies — changing a customer's email only requires updating one row in `Customers`, not every order.

  

---

  

## PART 7: ACID Properties

  

### Video Resources

- **Hussein Nasser — ACID Transactions Explained by Example**: https://youtube.com/watch?v=pomxJOFVcQs (~43 min, the gold standard)

- **GeeksforGeeks written guide**: https://www.geeksforgeeks.org/dbms/acid-properties-in-dbms/

  

### The Four Properties

  

| Property | Meaning | Example |

|----------|---------|---------|

| **Atomicity** | All or nothing | Bank transfer: debit AND credit both happen, or neither |

| **Consistency** | DB moves between valid states | Constraints, triggers, foreign keys enforced |

| **Isolation** | Concurrent transactions don't interfere | Two users withdrawing from same account see correct balance |

| **Durability** | Committed data survives crashes | Written to disk, not just memory |

  

### Isolation Levels (Ranked Low to High)

  

| Level | Dirty Read | Non-Repeatable Read | Phantom Read | Performance |

|-------|-----------|-------------------|-------------|-------------|

| Read Uncommitted | Possible | Possible | Possible | Fastest |

| Read Committed | Prevented | Possible | Possible | Good (default in most DBs) |

| Repeatable Read | Prevented | Prevented | Possible | Slower |

| Serializable | Prevented | Prevented | Prevented | Slowest |

  

**Definitions**:

- **Dirty read**: Reading uncommitted data from another transaction

- **Non-repeatable read**: Same query returns different data within one transaction

- **Phantom read**: New rows appear between two reads in one transaction

  

**Interview answer**: "I'd typically use Read Committed as the default — it prevents dirty reads while keeping good performance. For financial transactions or inventory systems where consistency is critical, I'd use Serializable despite the performance cost."

  

---

  

## PART 8: Study Schedule (20 Hours)

  

### Block 1 — LeetCode Deep Dive (Hours 0-8)

- [ ] **Hours 0-3**: LC 239 — solve 3 times from scratch, practice dry run OUT LOUD

- [ ] **Hours 4-5**: LC 1438 (two-deque pattern) — solve twice

- [ ] **Hours 6-7**: LC 862 or 1696 — solve once, understand pattern

- [ ] **Hour 8**: Timed mock — solve LC 239 in 20 min with verbal dry run

  

### Block 2 — Systems Theory (Hours 9-14)

- [ ] **Hours 9-10**: Watch Docker videos + memorize Dockerfile template

- [ ] **Hours 11-12**: Watch K8s crash course + memorize pod vs container

- [ ] **Hours 13-14**: REST API methods/codes + SQL indexing (B-tree)

  

### Block 3 — Database Deep Dive (Hours 15-18)

- [ ] **Hours 15-16**: Watch normalization video + work through 3 examples by hand

- [ ] **Hours 17-18**: Watch ACID video + flashcard isolation levels

  

### Block 4 — Final Review (Hours 19-20)

- [ ] **Hour 19**: Speed-run LC 239, 1438 (15 min each max)

- [ ] **Hour 20**: Mock interview — dry run LC verbally + answer 5 random systems questions

  

---

  

## PART 9: Interview Day Strategy

  

### For the Coding Problem (Expected: ~25 min)

1. **Clarify** (1 min) — edge cases, constraints, input size

2. **Explain approach** (2 min) — "I'll use a monotonic deque storing indices. The deque maintains a decreasing order so the front always holds the window maximum..."

3. **Code** (10 min) — clean, with brief comments

4. **DRY RUN** (3 min) — **THE MOST IMPORTANT PART per recruiter notes**. Walk through example step-by-step: "At i=0, deque is empty, I push index 0..."

5. **Complexity** (1 min) — "O(n) time because each element enters and leaves the deque at most once. O(k) space for the deque."

  

### For Systems Questions (Expected: ~20 min)

- Be **specific**: "I'd use `FROM node:20-alpine` for a 5MB base image instead of the 900MB default..."

- **Explain trade-offs**: "Indexes speed reads but slow writes because the B-tree must rebalance..."

- **Use examples**: "To normalize this, I'd extract CustomerName into a separate Customers table to prevent update anomalies..."

- **Think out loud**: If you don't know exact syntax, explain what you're trying to accomplish

  

### Red Flags to Avoid

- Jumping to code without explaining approach

- Forgetting the dry run (recruiter SPECIFICALLY noted this)

- Vague answers ("Docker is for containers") instead of specifics

- Not asking clarifying questions

  

### Things That Impress

- Mentioning trade-offs unprompted ("Alpine is smaller but may lack some system libraries...")

- Clean variable names and code structure

- Explaining WHY, not just WHAT ("We use a deque because we need O(1) operations on both ends")

- Catching your own bugs during dry run

  

---

  

## Quick Reference Links

  

### LeetCode Problems

| Problem | Link |

|---------|------|

| LC 239 — Sliding Window Maximum | https://leetcode.com/problems/sliding-window-maximum/ |

| LC 1438 — Longest Subarray Abs Diff | https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/ |

| LC 1696 — Jump Game VI | https://leetcode.com/problems/jump-game-vi/ |

| LC 862 — Shortest Subarray Sum >= K | https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/ |

  

### Video Resources

| Topic | Video | Length |

|-------|-------|--------|

| Sliding Window Maximum | NeetCode — search "NeetCode Sliding Window Maximum" on YouTube | ~15 min |

| Docker Overview | [Fireship — Docker in 100 Seconds](https://youtu.be/Gjnup-PuquQ) | ~2 min |

| Docker + Node.js | [Fireship — Docker basics with Node.js](https://fireship.io/lessons/docker-basics-tutorial-nodejs/) | ~12 min |

| Kubernetes Crash Course | [TechWorld with Nana — K8s for Absolute Beginners](https://youtube.com/watch?v=s_o8dwzRlu4) | ~1 hr |

| Database Normalization | [Decomplexify — 1NF through 5NF](https://youtu.be/GFQaEYEc8_8) | ~30 min |

| ACID Properties | [Hussein Nasser — ACID Explained by Example](https://youtube.com/watch?v=pomxJOFVcQs) | ~43 min |

| B-Tree Indexing | [PlanetScale — B+ Trees and Indexes](https://planetscale.com/blog/btrees-and-database-indexes) | Article |

  

### Written Resources

| Topic | Link |

|-------|------|

| Docker Node.js Guide | https://docs.docker.com/guides/nodejs/ |

| K8s Official Tutorial | https://kubernetes.io/docs/tutorials/kubernetes-basics/ |

| REST API Tutorial | https://www.restapitutorial.com/ |

| DB Normalization | https://www.freecodecamp.org/news/database-normalization-1nf-2nf-3nf-table-examples/ |

| B-Tree Indexing | https://builtin.com/data-science/b-tree-index |

| ACID Properties | https://www.geeksforgeeks.org/dbms/acid-properties-in-dbms/ |

| NeetCode Solutions | https://neetcode.io/solutions/sliding-window-maximum |

| Algo.monster LC 239 | https://algo.monster/liteproblems/239 |

  

---

  

## Self-Test Checklist

  

- [ ] Can solve LC 239 from memory in under 20 minutes

- [ ] Can verbally dry-run LC 239 step by step without notes

- [ ] Can write a Node.js Dockerfile from memory and explain each line

- [ ] Can explain pod vs container and when to use multi-container pods

- [ ] Can list HTTP methods with idempotency and 5+ status codes

- [ ] Can normalize a denormalized table to 3NF with explanation

- [ ] Can explain B-tree indexing trade-offs (reads vs writes)

- [ ] Can recite ACID properties with real-world examples

- [ ] Can explain at least 2 isolation levels and when to use each