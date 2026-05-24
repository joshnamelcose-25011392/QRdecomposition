# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
```
#Program to QR decomposition using the Gram-Schmidt method
#Developed by: Joshna.M
#RegisterNumber: 212225230118
import numpy as np
def g(a):
    a = np.array(a, dtype=float) 
    m, n = a.shape 
    q = np.zeros((m, n)) 
    r = np.zeros((n, n)) 
    
    for j in range(n):
        v = a[:, j]
        for i in range(j):
            r[i, j] = np.dot(q[:, i], a[:, j]) 
            v = v - r[i, j] * q[:, i]
        r[j, j] = np.linalg.norm(v) 
        q[:, j] = v / r[j, j]    
    return q, r
a = np.array(eval(input()))
q, r = g(a)
print("The Q Matrix is\n", q)
print("The R Matrix is\n", r)
```
### Gram-Schmidt Method
```







```

## Output
```
([[1,1,0],[1,0,1],[0,1,1]])
The Q Matrix is
 [[ 0.70710678  0.40824829 -0.57735027]
 [ 0.70710678 -0.40824829  0.57735027]
 [ 0.          0.81649658  0.57735027]]
The R Matrix is
 [[1.41421356 0.70710678 0.70710678]
 [0.         1.22474487 0.40824829]
 [0.         0.         1.15470054]]
```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
