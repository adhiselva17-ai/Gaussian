# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Write a python program for the given matrix.
2.Using numpy library.
3.Using the np.linalg.matrix_rank(),we can find the rank of the given matrix.
4.Run the program and get the output. 

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: ADHI SELVAKUMAR R 
RegisterNumber: 212225220003
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end=' ')
```

## Output:
<img width="1047" height="695" alt="Screenshot 2026-06-03 083641" src="https://github.com/user-attachments/assets/6c63427a-005c-4db4-b5f2-ad27aa2366aa" />
<img width="1080" height="568" alt="Screenshot 2026-06-03 083657" src="https://github.com/user-attachments/assets/5d9d46d6-fca3-4161-a34c-4ea4a05518da" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

