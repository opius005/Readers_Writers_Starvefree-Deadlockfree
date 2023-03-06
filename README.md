# Readers_Writers_Starvefree-Deadlockfre

The given solution is a starvefree and deadlockfree solution for readers-writers problem in process syncronisation of operating systems.\
These are the main cases considered for solving the problem:\
-> r + r = allowed\
-> r + w = not allowed\
-> w + r = not allowed\
-> w + w = not allowed\
-> when writers are waiting, readers are not allowed and should wait until the writers are done\
Following the above cases we can achieve starvation and deadlock free solution.\
r_count is the number of active readers\
mutex is a binary semaphore used to achieve mutual exclusion among readers and writers\
r_s is a binary semaphore to acheive mutual exclusion among readers while modifying r_acount\
w_s is a binary semaphore to acheive mutual exclusion among writers\

case-1:\
when a reader enters into critical section for first time, w_s is set to 0 and mutex is changed from 1-0-1 . When another reader comes before any writer comes , he can enter into critical section. When all the active readers are done(r_count=0) then the waiting writers are signelled; \
case-2:\
As explained in case-1, w_s is set to 0 . so writer can't enter into critical section and will be waiting\
case-3 & case-4\
when a writer enters into critical section it sets mutex and w_s to 0. so no reader or writer can enter into critical section.\
case-5:\
when writers are waiting when a reader is in critical section , if a new reader comes it cannot enter into critical section as mutex is set to 0 by writers who came before\
