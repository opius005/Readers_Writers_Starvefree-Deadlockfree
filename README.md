# Readers_Writers_Starvefree-Deadlockfre

The given solution is a starvefree and deadlockfree solution for readers-writers problem in process syncronisation of operating systems.
These are the main cases considered for solving the problem:
-> r + r = allowed
-> r + w = not allowed
-> w + r = not allowed
-> w + w = not allowed
-> when writers are waiting, readers are not allowed and should wait until the writers are done
Following the above cases we can achieve starvation and deadlock free solution.
r_count is the number of active readers
mutex is a binary semaphore used to achieve mutual exclusion among readers and writers
r_s is a binary semaphore to acheive mutual exclusion among readers while modifying r_acount
w_s is a binary semaphore to acheive mutual exclusion among writers
