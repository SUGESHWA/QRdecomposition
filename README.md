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
### Gram-Schmidt Method
```


''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: SUGESHWA S
RegisterNumber: 212224230277
'''
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape # get the shape of A
    Q = np.empty((n, n)) # initialize matrix Q
    u = np.empty((n, n)) # initialize matrix u
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1, n):
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j] # get each u vector
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i]) # compute each e vetor
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output

![image](https://github.com/user-attachments/assets/ebb5bd30-1474-4448-b941-915776108162)



![image](https://github.com/user-attachments/assets/420033db-759f-411e-a8ca-2371e7c2526e)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
