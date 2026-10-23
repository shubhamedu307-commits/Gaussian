# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1. Import the numpy module to use the built-in functions for calculation

2.Prepare the lists from each linear equations and assign in np.array()

3.Using the np.zeros() and seprate them and use it in the for loops so we can find the solutions.

4.End the program

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SHUBHAM KUMAR
RegisterNumber: 26013866
*/
```
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
import sys


n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range (n):
    for j in range (n+1):
        a[i][j]=float(input())
for i in range (n):
    if a[i][i]==0:
       sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
           a[j][k]= a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=a[i][n]
    for j in range (i+1,n):
       x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
   print('X%d = %0.2f ' %(i,x[i]),end='')

```


## Output:
<img width="325" height="481" alt="Exp-06 - Record-Gaussian Elimination" src="https://github.com/user-attachments/assets/1b8998e8-1b8d-47b3-82c5-ac338d531559" />


<img width="262" height="147" alt="result 6" src="https://github.com/user-attachments/assets/0be2b4c8-2983-4da1-977c-cdd7cef4ab61" />





## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

