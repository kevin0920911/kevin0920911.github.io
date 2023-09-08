---
title: "Python Test"
subtitle: "Test of Python for linear algebra"
layout: post
author: "Hsu"
published: true
header-style: text
tags:
  - linearalgebra
  - Python
---

# Python Test

Status: Done

<aside>
💡 **Monster Problems**

There are two kinds of weird monsters here: A and B.

monster A has 2 eyes and 1 tail.

monster B has 3 eyes and 2 tails.

If we only know the sum of two kinds of monsters' eyes and the sum of two kinds of monsters' tails.

Could we figure out the amounts of each monster?

<aside>
👉 **Input**

The input data is only 1 line, split by space. The first number indicates the sum of the monsters' eyes. The second indicates the sum of the monsters' tails.

</aside>

<aside>
👉 **Output**

If the amounts of monsters are possible. Output the amounts of monsters A and B separated by space in 1 line. However, if the answer is not integer or negative, then the output is "impossible".

If the amounts of monsters are possible. Output the amounts of monsters A and B separated by space in 1 line. However, if the answer is not integer or negative, then the output is "impossible".

</aside>

<aside>
1️⃣ **Sample Input**

138

</aside>

<aside>
1️⃣ **Sample Output**

23

</aside>

<aside>
2️⃣ **Sample Input**

86

</aside>

<aside>
2️⃣ **Sample Output**

impossible

</aside>

```python
e,t=map(int,input().split())
A=-3*t+2*e
B=2*t-e
if A>0 and B>0:
	print(A,B)
else:
	print("impossible")
```

</aside>

<aside>
💡 **Insane Transpose Matrix!!!**

Below are some craziest matrix operation!!!

What am I gonna do?

1. **given matrix A and matrix B as input**
    
    $$
    A=\begin{bmatrix}
    1 & 2  \\
    3 & 4 
    \end{bmatrix}
    $$
    
    $$
    B=\begin{bmatrix}
    5 & 6  \\
    7 & 8 
    \end{bmatrix}
    $$
    
2. **calculate tanspose matrix $B^T$ from matrix $B$**
    
    $$
    B^T=\begin{bmatrix}
    5 & 7  \\
    6 & 8 
    \end{bmatrix}
    $$
    
1. **matrix C equals matrix A times transpose matrix  $B^T$**
    
    $$
    C=A×B^T=\begin{bmatrix}
    17 & 23  \\
    39 & 53 
    \end{bmatrix}
    $$
    
2. **Output transpose matrix $C^T$ from matrix $C$**
    
    $$
    C^T=\begin{bmatrix}
    17 & 39  \\
    23 & 53 
    \end{bmatrix}
    $$
    

<aside>
👉 **Input**

Each test case consist of two rows. First row is the input matrix $A$. Second row is the input matrix $B$. Both matrix are square matrix with the same size $N*N$, and $N$ is defined by larger size within matrix $A$ and matrix $B$. However if the elements in matrix do not fit square matrix, then append 00 in the end of matrix first! All elements are integer only.

<aside>
💡 **Hint: 1 2 3**

</aside>

$$
\begin{bmatrix}
1 & 2  \\
3 & 0 
\end{bmatrix}
$$

<aside>
💡 **Hint:  1 2 3 4 5 6 7 8 9**

</aside>

$$
\begin{bmatrix}
1 & 2&3  \\
4 & 5&6 \\7&8&9
\end{bmatrix}
$$

</aside>

<aside>
👉 **Output**

Output is simply matrix $C^T$

Row major with line by line. 

Each element split by 1 space between. 

See sample output below.

</aside>

<aside>
1️⃣ **Sample Input**

1 2 3 4

5 6 7 8

</aside>

<aside>
1️⃣ **Sample Output**

17 39

23 53

</aside>

<aside>
2️⃣ **Sample Input**

1 2 3 4 5 6 7 8 1 2

2 2 2 2 2

</aside>

<aside>
2️⃣ **Sample Output**

20 52 6 0

2 10 2 0

0 0 0 0

0 0 0 0

</aside>

```python
a=[int(i) for i in input().split()]
b=[int(i) for i in input().split()]
max_N=max(len(a),len(b))
i=1
while (i**2<max_N):i+=1
N=i
x=0
A=[[0]*N for i in range(N)]
B=[[0]*N for i in range(N)]
for i in range(N):
    for j in range(N):
        if (x==len(a)):
            break
        A[i][j]=a[x]
        x+=1
x=0
for i in range(N):
    for j in range(N):
        if (x==len(b)):
            break
        B[i][j]=b[x]
        x+=1

B=[list(j) for j in zip(*B)]
C=[[0]*N for i in range(N)]
for i in range(N): 
    for j in range(N):
        for k in range(N):
            C[i][k]+=A[i][j]*B[j][k]
C=[list(j) for j in zip(*C)]
for i in range(N):
    for j in range(N):
        print(C[i][j],end=" ")
    print()
```

</aside>

<aside>
💡 **More Determinant of A Square Matrix**

Calculate the Determinant of a square matrix.

In the first step of this problem, we introduce a row-major truncated represented square matrix to represent a traditional square matrix.

<aside>
👉 **Input**

A serial of numbers to represent the row-major truncated represented square matrix.

The square matrix size is between 2 x 2~6 x 6. All the entries are represented as an integer. The value range is between -10 and 10.

<aside>
⚠️ **測資高達6階，讚吧** 🙂

</aside>

<aside>
💡 **Hint: 1 2 3**

</aside>

$$
\begin{bmatrix}
1 & 2  \\
3 & 0 
\end{bmatrix}
$$

<aside>
💡 **Hint:  1 2 3 4 5 6 7 8 9**

</aside>

$$
\begin{bmatrix}
1 & 2&3  \\
4 & 5&6 \\7&8&9
\end{bmatrix}
$$

</aside>

<aside>
👉 **Output**

The output shows the determinant as an integer.

</aside>

<aside>
1️⃣ **Sample Input**

1 2 3 2 3 2 1 -1 1

</aside>

<aside>
1️⃣ **Sample Output**

-10

</aside>

<aside>
2️⃣ **Sample Input**

1 2 1 1 2 2 3 1 1 5 4 5 2 3 4 3 3 1 2 1 3

</aside>

<aside>
2️⃣ **Sample Output**

3

</aside>

```python
def det(m):
    if len(m)==1:
        return m[0][0]
    else:
        total=0
        for i in range(len(m)):
            n=[[row[j] for j in range(len(m)) if i!=j] for row in m[1:]]
            if i%2==0:
                total+=det(n)*m[0][i]
            else:
                total-=det(n)*m[0][i]
        return total
A=[int(i) for i in input().split()]
n=0
while n**2<len(A):n+=1
m=[[0]*n for i in range(n)]
for i in range(n):
    for j in range(n):
        if i*n+j==len(A):
            break
        m[i][j]=A[i*n+j]
print(det(m))
```

</aside>

<aside>
💡 **Inverse Matrix of A Square Matrix**

Calculate the inverse matrix of a square matrix.

First step of this problem, we introduce a row-major truncated represented square matrix to represent a traditional square matrix. As we know, the size of the square matrix should be n $n^2, n\in N$ . The row-major traditional square matrix for $A= \begin{bmatrix}1&0&5\\ 2&3&1\\ 5&0&0\end{bmatrix}$can be represented as a serial of numbers  $\begin{matrix}1&0& 5& 2& 3& 1& 5&0&0\end{matrix}$ The row-major truncated represented square matrix can be shorted as A is $\begin{matrix}1&0& 5& 2& 3& 1& 5\end{matrix}$. That is, the last 2 zeros can be ignored. Consider the row-major truncated represented square matrix, we can get the number of the entries to reason the minimal size of the square matrix. For example, the row-major truncated represented square matrix  $\begin{matrix}1&0& 5\end{matrix}$ is presented the square matrix $A= \begin{bmatrix}1&0\\ 5&0\end{bmatrix}$.

To calculate the inverse matrix, For example, input a square matrix $A= \begin{bmatrix}1&4\\ -1&-3\end{bmatrix}$ Then, the inverse matrix  $A^{-1}= \begin{bmatrix}-3&-4\\ 1&1\end{bmatrix}$

<aside>
👉 **Input**

A serial of numbers to represent the row-major truncated represented square matrix.

The square matrix size is between 2 x 2~5x 5. All the entries are represented as an integer. 

<aside>
💡 **Hint: 1 2 3**

</aside>

$$
\begin{bmatrix}
1 & 2  \\
3 & 0 
\end{bmatrix}
$$

<aside>
💡 **Hint:  1 2 3 4 5 6 7 8 9**

</aside>

$$
\begin{bmatrix}
1 & 2&3  \\
4 & 5&6 \\7&8&9
\end{bmatrix}
$$

</aside>

<aside>
👉 **Output**

Output shows the inverse matrix as the row-major truncated form. All the entries are represented by rounding to a fixed point with the second decimal place. If there is  noninvertible matrix, then output "Singular".

**Notice: -0.00 should be represented as 0.00**

</aside>

<aside>
1️⃣ **Sample Input**

1 3 2 4

</aside>

<aside>
1️⃣ **Sample Output**

-2.00 1.50 1.00 -0.50

</aside>

<aside>
2️⃣ **Sample Input**

1 -1 0 6 -2 -1 3 4 12

</aside>

<aside>
2️⃣ **Sample Output**

0.36 0.22 0.02 -1.36 0.22 0.02 0.55 -0.13 0.07

</aside>

```python
import math
def det(m):
    if len(m)==1:
        return m[0][0]
    else:
        total=0
        for i in range(len(m)):
            n=[[row[j] for j in range(len(m)) if i!=j] for row in m[1:]]
            if i%2==0:
                total+=m[0][i]*det(n)
            else:
                total-=m[0][i]*det(n)
        return total
def cofactor(x,y,m):
    A=[]
    for i in range(len(m)):
        tmp=[]
        for j in range(len(m)):
            if x!=i and y!=j:
                tmp.append(m[i][j])
        if tmp!=[]:
            A.append(tmp)
    return det(A)*((-1)**(x+y))
A=[int(i) for i in input().split()]
n=1
while n**2<len(A):
    n+=1
M=[[0]*n for i in range(n)]
for i in range(n):
    for j in range(n):
        if i*n+j>=len(A):
            break
        M[i][j]=A[i*n+j]
adj=[[0 for j in range(n)] for i in range(n)]
for i in range(n):
    for j in range(n):
        adj[i][j]=cofactor(i,j,M)
adj=[list(i) for i in zip(*adj)]
c=det(M)
if c==0:
    print("Singular")
else:
    for i in range(n):
        for j in range(n):
            adj[i][j]=round(adj[i][j]/c,2)
            if len(str(adj[i][j]).split('.')[1])==1:
                if str(adj[i][j])=="-0.0":
                    print("0.00",end=" ")
                else:
                    print(str(adj[i][j])+"0",end=" ")
                continue
            print(adj[i][j],end=" ")
```

</aside>

<aside>
💡 **Least Squares Regression**

The method of least squares is a standard the approach in regression analysis to approximate the solution of overdetermined systems. The most an important application is in data fitting. The best fit in the least-squares sense minimizes the sum of squared residuals. In statistics, polynomial regression is a form of regression analysis in which the relationship between the independent variable x and the dependent variable y is modeled as an nth-degree polynomial in x. Polynomial regression fits a nonlinear relationship between the value of x and the the corresponding conditional mean of y, denoted $E(y|x)$. Although polynomial regression fits a nonlinear model to the data, as a statistical estimation problem it is linear.

In this problem, we focus on the least squares regression quadratic polynomial. That is, we have a pair data set $\{(x_i, Y_i)|X_i, Y_i \in R\}$. The data pair $(x_i,y_i)$ can be represented as a point in the x-y Cartesian coordinate system. Then, we should find a quadratic polynomial 

$y = c0+c1x + c_2x^2$ to best fit the data set by the least squares regression.

<aside>
👉 **Input**

There is one row for the data pairs. The number of the data should be even. The

minimal number of data is 8. Every pair is shown as the form $(x_i,y_i)$. That is, the data is show as $x_1\space y_1\space x_2\space y_2\space x_3\space y_3$.... The number range of the data is $8< num(data) ≤ 30$

<aside>
💡 **Hint: 1 2 3 4**

$$
(1,2) , (3,4)
$$

</aside>

</aside>

<aside>
👉 **Output**

The coefficients of the quadratic polynomial $y = c0+c1x + c_2x^2$. That

is, $c_0\space  c_1\space c_2$ Three coefficients should berepresented in one row and showed as a

fixed point with the second decimal place. (use format %.2f)

**Notice: -0.00 should be represented as 0.00**

</aside>

<aside>
1️⃣ **Sample Input**

0.21 1.5 2 2.5 3 4

</aside>

<aside>
1️⃣ **Sample Output**

1.95 -0.80 0.50

</aside>

<aside>
2️⃣ **Sample Input**

5 4.9 10 5.3 15 5.7 20 6.1 25 6.5

</aside>

<aside>
2️⃣ **Sample Output**

4.50 0.08 0.00

</aside>

```python
import copy
def det(m):
    if len(m)==1:
        return m[0][0]
    else:
        total=0
        for i in range(len(m)):
            n=[[row[j] for j in range(len(m)) if i!=j]for row in m[1:]]
            if i%2==0:
                total+=det(n)*m[0][i]
            else:
                total-=det(n)*m[0][i]
        return total
def Cramer(Am):
    A=[list(j) for j in zip(*Am)]
    b=copy.deepcopy(A[-1])
    A=copy.deepcopy(A[:len(A)-1])
    Ans=[]
    for i in range(len(A)):
        tmp=copy.deepcopy(A)
        tmp[i]=b
        Ans.append(det(tmp)/det(A))
    return Ans
def Mul(A,B):
    row1,col1,col2=len(A),len(A[0]),len(B[0])    
    C=[[0]*col2 for i in range(row1)]
    for i in range(row1):
        for j in range(col1):
            for k in range(col2):
                C[i][k]+=A[i][j]*B[j][k]
    return C
n=[float(i) for i in input().split()]
Point=[[0]*2 for i in range( int( len(n)/2 ) + ( len(n)%2 ) )]
for i in range(len(n)):
    Point[int(i/2)][i%2]=n[i]
Point=[list(j) for j in zip(*Point)]
B=[]
for i in Point[0]:
    B.append([1,i])
BTB=Mul([list(j) for j in zip(*B)],B)
BTC=Mul([list(j) for j in zip(*B)],[list(j) for j in zip(Point[1])])
for i in range(len(BTB)):
    BTB[i].extend(BTC[i])
for i in Cramer(BTB):
		if str(i)=="-0.0":
			print("0.00",end=" ")
		else:
	    print(f"{round(i,2):.2f}",end=" ")
```

</aside>