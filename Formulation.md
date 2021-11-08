# PPO-based **allotion (PSA)
## State
1. <img src="https://render.githubusercontent.com/render/math?math=C = \prod {C_n}"> (Computation_power (learning_time)) : 1xn vector (C), 1x1 variable (C_n)
2. <img src="https://render.githubusercontent.com/render/math?math=D = \prod {D_n}"> (D2D communication rate) : nx(n-1) array (D), 1x(n-1) vector (D_n)
3. T = Allocation Task index : 1xN! vector = {-1, N} ==> finish status
4. <img src="https://render.githubusercontent.com/render/math?math=B = \prod {B_n} "> (Buffer status)
  - <img src="https://render.githubusercontent.com/render/math?math=B_n=[b_{n,1},...,b_{n,n!}], b_{n,t}={0: empty, 1: to be process, 2: to be transmits}"> Due to the limited storage, node $n$ cannot store deep networks over $*_n$ networks.   
6. wireless status (?) ==> D2D with shared network, D2D with unshared network.

## Action
The agent only detemire the allocation tasks at the start epoch. 
1. A^T = Allocation Task index : 1xN! vector = {0, 1} 
The remained action is excuted at every epoch.  
2. <img src="https://render.githubusercontent.com/render/math?math=A^P =\prod{A^P_n}"> = Processing task at node $n$ for task in buffer state : 1xN!
3. <img src="https://render.githubusercontent.com/render/math?math=A^D =\prod{A^D_n}"> = Transmission task to node $n$ for task in done : 1xN!

## Reward
1. After time deadlin the reported task to PS $\sum(T==0)$
2. Pelnaty of processing cost and transmission cost
