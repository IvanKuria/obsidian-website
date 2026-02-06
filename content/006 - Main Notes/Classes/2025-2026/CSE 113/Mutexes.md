Class: [[CSE 113]]
Subject: #computer-science #computer-architecture 
Date: 2026-02-05
Teacher: **Prof. Souza

# Mutexes

## Properties of Mutexes

1. **Mutual Exclusion**: two threads cannot be in the critical section at the same time
2. **Deadlock Freedom**: If a thread has requested a mutex and no thread is currently holding the mutex, the mutex must be acquired by one of the requesting threads
3. **Starvation Freedom**: (optional) A thread that requests the mutex must obtain the mutex.