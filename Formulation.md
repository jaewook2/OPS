# PPO-based **allotion (PSA)
## Object: 
 The maximize the number of updated paraters to FL server wthin time deadline ==> 이것을 기점으로.
 The minimize the round time to receive $N$ updated parameters at the FL server
## System model
 : Shared model? or Non-shared model? ==> Non-shared model can be defined (디아비스간 독립적인 무선자원을 할당 받는다고 가정)
 : 
## State
1. <img src="https://render.githubusercontent.com/render/math?math=C = \prod {C_n}"> (Computation_power (learning_time)) : 1xn vector (C), 1x1 variable (C_n)
2. <img src="https://render.githubusercontent.com/render/math?math=D = \prod {D_n}"> (D2D communication rate) : nx(n-1) array (D), 1x(n-1) vector (D_n)
3. T = Allocation Task index : 1xN! vector = {-1,..., N+1} ==> -1 represents the learning task $n$ is not allocated, >-1 means the task is allocated, 0< <N  represents the number finsihed learning job, N represents $n$ tasks are finised.
4. Device state 필요
 - processing state (1xn) size : processing (timer-based): {-1, 0, 1, 2, 3, ..., T_{n}} represents the reamined processing time. Specially, -1 represents this task is not procssed yet. 0 represents this learning task is processed and buffered.
 - processing buffer state (1xn) size : 0 or 1 (buffered or not)
 - wireless buffer state (1xn) size : 0 or 1 (buffered or not)
 - transmiting state (1xn) size : 0 or 1
   
7. wireless status (?) ==> D2D with unshared network.
8. Execution time  E.


## Action
The agent determines the task allocation and scheduling.

1. A^S = Start Learning Task index : NxN! vector = {0, 1}. at:  
1. A^T = Allocation Task index : NxN! vector = {0, 1}. at:  
1. A^P = Allocation Task index : NxN! vector = {0, 1}. at:  

%2. <img src="https://render.githubusercontent.com/render/math?math=A^P =\prod{A^P_n}"> = Processing task at node $n$ for task in buffer state : 1xN!
%3. <img src="https://render.githubusercontent.com/render/math?math=A^D =\prod{A^D_n}"> = Transmission task to node $n$ for task in done : 1xN!

## Reward
1. After time deadlin the reported task to PS $\sum(T==0)$
2. Pelnaty of processing cost and transmission cost
