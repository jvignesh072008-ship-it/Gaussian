# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.Start the program and import required libraries. Read the number of variables n from the user.

2.Create an augmented matrix a[n][n+1] and solution array x[n], then read all matrix elements from the user.

3.Check if the diagonal element is zero; if it is zero, terminate the program to avoid division by zero.

4.Perform forward elimination to convert the augmented matrix into an upper triangular matrix.

5.Apply back substitution to calculate the values of unknown variables and store them in the solution array.

6.Print the calculated values of all variables as the final solution.
```
## Program:
```
/*
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: VIGNESH J
RegisterNumber: 212225230297

import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by zero detected")
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio* a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print(f"X{int(i)} = {x[i]:.2f}",end=' ')
*/
```

## Output:
<img width="698" height="921" alt="Screenshot 2026-03-10 091830" src="https://github.com/user-attachments/assets/a58d944b-abae-445d-ad9d-0ae5762576ad" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

