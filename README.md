# VALUE ITERATION ALGORITHM

## AIM
To develop a Python program to find the optimal policy for the given MDP using the value iteration algorithm.

## PROBLEM STATEMENT
To find the optimal policy for the mdp using value iteration algorithm instead of policy iteration which is slower than value iteration.

## VALUE ITERATION ALGORITHM
=Firstly the state value function and action value function for all the states of mdp are initialized to zero then while iterating through actions of each state the value function and action value function is caluculated for each state then the maximum action value function of each state is taken to find the best ploicy.

## VALUE ITERATION FUNCTION
### Name:Himavath M
### Register Number:212223240053
```
def value_iteration(P, gamma=1.0, theta=1e-10):
    V=np.zeros(len(P), dtype=np.float64)
    while True:
      Q=np.zeros((len(P),len(P[0])), dtype=np.float64)
      for s in range(len(P)):
        for a in range(len(P[s])):
          for prob,next_state,reward,done in P[s][a]:
            Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
      if np.max(np.abs(V-np.max(Q,axis=1)))<theta:
        break
      V=np.max(Q,axis=1)
      pi=lambda s: {s:a for s, a in enumerate(
          np.argmax(Q,axis=1))
     }[s]
    return V, pi

print("Name: Himavath M Register Number: 212223240053")
print('Optimal policy and state-value function (VI):')
print_policy(pi_best_v, P)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/f99546c0-701d-4877-8495-f6810fcea258)
![image](https://github.com/user-attachments/assets/561b3988-425e-4a31-bd9f-965fdcbc2225)
![image](https://github.com/user-attachments/assets/883eb458-c4f7-4270-af95-4e2cf8b87953)


## RESULT:

Thus, The python program to find the optimal policy for the given MDP using the value iteration algorithm is successfully executed.
