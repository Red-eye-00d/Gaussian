# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start program and input number of unknowns n.

2. Declare augmented matrix A[n][n+1].

3. Call read_matrix(A, n) to input matrix values.

4. For k = 0 to n-1, check if A[k][k] == 0, call pivot_swap(A, k, n) if needed.

5. For i = k+1 to n-1, compute factor = A[i][k] / A[k][k].

6. For j = k to n, perform A[i][j] -= factor * A[k][j].

7. Repeat steps 4–6 until matrix is in upper triangular form.

8. Initialize solution vector x[n] = {0}.

9. For i = n-1 to 0, compute x[i] = (A[i][n] - Σ A[i][j]*x[j]) / A[i][i].

10. Call display_solution(x, n) to print results.

## Program:
```python

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]= float(input())
        
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio *a[i][k]
            
x[n-1] = a[n-1][n]/a[n-1][n-1]
    
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
        
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j] * x[j]
            
    x[i] = x[i]/a[i][i]
        
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end = ' ')
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SUDHARSANAN U
RegisterNumber: 212224230276
*/
```

## Output:
![gaussian elimination]()
![image](https://github.com/user-attachments/assets/9942b61f-3f44-4fdc-8bf5-2a7973ee50a4)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
