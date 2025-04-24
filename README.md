# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

```
## Algorithm
###Step 1.Form the augmented matrix for the system of equations.
###Step2.Apply forward elimination to convert the matrix to upper triangular form.
###Step 3.Check for division by zero to avoid invalid operations.
###Step 4.Use back substitution to solve for the unknown variables.
```

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: MARIMUTHU MATHAVAN
RegisterNumber: 212224230153
*/
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]= a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end = ' ')

```

## Output:
![Screenshot 2025-04-24 212419](https://github.com/user-attachments/assets/11ca5b37-0ad5-4150-a2bb-fb7963fe9b75)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

