# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the NumPy library and define the matrix containing the coefficients and constants.
2. Convert the matrix into an upper triangular form.
3. Solve for the variables, starting from the last row and working upwards.
4. Conclude the program.



## Program:
'Program to solve a matrix using Gaussian elimination without partial pivoting.

 Developed by:  lakshmen prashanth R
 
 RegisterNumber:  24007066
 
'''
import numpy as np
import sys

n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

for i in range(n):
    if  a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]

x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i]-a[i][j]*x[j]
    x[i] = x[i]/a[i][i]

for i in range(n):
    print('X%d = %0.2f ' %(i, x[i]), end = ''


## Output:
![image](https://github.com/user-attachments/assets/a973664f-f8f0-4ed0-970b-3c00638f00f2)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

