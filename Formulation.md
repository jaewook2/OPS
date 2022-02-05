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
4. <img src="https://render.githubusercontent.com/render/math?math=B = \prod {B_n} "> (Buffer status)
  - <img src="https://render.githubusercontent.com/render/math?math=B_n=[b_{n,1},...,b_{n,n!}], b_{n,t}=\{0: empty, 1: to be process, 2: to be transmits\}"> Due to the limited storage, node $n$ cannot store deep networks over $M_n$ networks ==> if $the number of stored networks is over than $M_n$, the latest arrived network is discard ==> state change -1   
6. wireless status (?) ==> D2D with unshared network.
7. Execution time  E.


## Action
The agent determines the task allocation and scheduling.

1. A^T = Allocation Task index : 1xN! vector = {0, 1} if $T_n$ is minus one, the action can be determined.
The remained action is excuted at every epoch.  
2. <img src="https://render.githubusercontent.com/render/math?math=A^P =\prod{A^P_n}"> = Processing task at node $n$ for task in buffer state : 1xN!
3. <img src="https://render.githubusercontent.com/render/math?math=A^D =\prod{A^D_n}"> = Transmission task to node $n$ for task in done : 1xN!

## Reward
1. After time deadlin the reported task to PS $\sum(T==0)$
2. Pelnaty of processing cost and transmission cost
