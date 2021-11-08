# PPO-based **allotion (PSA)
## State
1. <img src="https://render.githubusercontent.com/render/math?math=$C = \times {C_n}$> (Computation_power (learning_time)) : 1xn vector (C), 1x1 variable (C_n)
2. $D = \times {D_n}$ (D2D communication rate) : nx(n-1) array (D), 1x(n-1) vector (D_n)
3. $T = Allocation Task index : 1xN! vector = {-1, N}$ ==> finish status
4. $B = \times {B_n}$ (Buffer status) : (t, 1xN! vector ={0,1}) ==> t is the number of allocated tasks which will be processed and ==> the element in vector represents which task should be processed. 
5. $U = \times {U_n}$ (Update status) : (u, 1xN! vector ={0,1}) ==> u is the number of updated parameter in node n ==> the element in vector represents which parameter should be transmitted. 

## Action
1. A^T = Allocation Task index : 1xN! vector = {0, 1} 
2. A^P = Processing task in buffered state : 1xN!
3. A^D = Transmission task in updated parameter : 1xN!

## Reward
1. After time deadlin the reported task to PS $\sum(T==0)$
