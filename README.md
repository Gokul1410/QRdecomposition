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
Developed by: Gokul C
RegisterNumber: 212223240040
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    R=np.zeros((n,m))
    u=np.zeros((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]w
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![Screenshot 2024-04-16 211046](https://github.com/Gokul1410/QRdecomposition/assets/153058321/773d98be-3535-475e-8c4e-22a35c6d060f)
![320392348-6390c5a7-9f19-4190-9283-9ced3921537a](https://github.com/Gokul1410/QRdecomposition/assets/153058321/1cd62374-684d-435e-9778-a0396d699977)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
