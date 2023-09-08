---
title: "Determine"
subtitle: "Determine"
layout: post
author: "Hsu"
published: flase
header-style: text
tags:
  - linearalgebra
  - Python
---
<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# Determinant



💡 **Def Determinant of a $2*2$**

$\begin{vmatrix}
   a_{11} & a_{12}\\
   a_{21} & a_{22}
\end{vmatrix}$$=$$a_{11}*a_{22}-a_{12}*a_{21}$



✅ **How to find det. of square martrix of order higher than 2**





💡 **Def Minors and Cofactors**

**Minors: $M_{ij}$**

**Cofactors: $C_{ij}$$= (-1)^{i+j}M_{ij}$．**






💡 **Def The determinant of Square Matrix**



$det(A)=\begin{vmatrix}
   A
\end{vmatrix}$=$\begin {array}{l}\sum_{j=1}^n a_{ij}C_{ij}\\=a_{i1}C_{i1}+\dots a_{in}C_{in}\end{array}$

$det(A)=\begin{vmatrix}
   A
\end{vmatrix}=$$\begin {array}{l}\sum_{i=1}^n a_{ij}C_{ij}\\=a_{1j}C_{1j}+\dots a_{nj}C_{nj}\end{array}$

$i^{th}$ row expansion

$j^{th}$ col expansion


✅ **Code Determine**

```python
def det(m):
    if len(m)<=0:
        return None
    if len(m)==1:
        return m[0][0]
    else:
        total=0
        for i in range(len(m)):
            n=[ [row[j] for j in range(len(m)) if j!=i] for row in m[1:]]
            if i%2==0:
                total+=m[0][i]*det(n)
            else:
                total-=m[0][i]*det(n)
        return total
```







# Determinants Operation


📢 **Thm row/col Operation and Determinants**

1. Inchange two row or col of A 
2. Adding a multiple of a row or col to another row or col 
3. Muliple a row or col $c(c{=}\mathllap{/\,}0)$

1. 值加加負號
2. 值不變
    
    
3. 值多乘c


💡 Thm  Determinant is 0

1. 一列(行)為零
2. 兩列(行)為倍數關係


# Properties


📢 **Thm Product**

$$
det(AB)=det(A)det(B)
$$

📢 **Thm** **Scalar Multiple of a Matrix**

$$
det(cA)=c^n det(A)
$$


📢 **Thm** **Invertible Martix Properties**

$$
det(A^{-1})=1/det(A)
$$


📢 **Thm Determinant of Transpose**

$$
det(A^{T})=det(A)
$$



# Application


💡 **Thm Find Inverse using Adjoint**

$$
⁍⁍⁍
$$


❓ **Def Adjoint Matrix**

$$
adj(A)=\begin{bmatrix}
C_{11} & C_{12}&\dots & C_{n1}\\
\vdots & \ddots &  & \vdots \\ C_{1n} & C_{n2}&\dots & C_{nn}
\end{bmatrix}^T
$$


✅ **Code Inverse**

```python
from fractions import Fraction
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
def cofactor(x,y,m):
    A=[]
    for i in range(len(m)):
        tmp=[]
        for j in range(len(m)):
            if i!=x and j!=y:
                tmp.append(m[i][j])
        if tmp!=[]:
            A.append(tmp)
    return det(A)*((-1)**(x+y))
def scalar(c,m):
    for i in range(len(m)):
        for j in range(len(m[1])):
            m[i][j]*=c
n=int(input())
A=[]
for i in range(n):A.append([Fraction(j) for j in input().split()])
adj=[[0]*n for i in range(n)]
for i in range(n):
    for j in range(n):
        adj[i][j]=cofactor(i,j,A)
inv=[list(i) for i in zip(*adj)]
try:
    c=Fraction(1/det(A))
    scalar(c,inv)
    for i in range(n):
        for j in range(n):
            print(inv[i][j],end=" ")
        print()
except:
    print("Singular")
```

💡 **Thm Area of Triangle in xy-Plane**

The area of triangle with vertices $(x_{1},y_{1}),(x_{2},y_{2}),(x_{3},y_{3})$ is

$$
⁍⁍
$$


✅ **Find colinear**



$$
\left| \left |\begin{array}{}      x_{1} &y_{1}   & 1 \\
x_{2} &y_{2} & 1  \\
x_{3} &y_{3} &1 \\
\end{array}\right|  \right|=0
$$

💡 **Thm Volume of Tetrahedron**

The area of triangle with vertices $(x_{1},y_{1},z_{1}),(x_{2},y_{2},z_{2}),(x_{3},y_{3},z_{3}),(x_{4},y_{4},z_{4})$ is

![Untitled](Determine%203bdbe917a324402db46ee3e2071dbd15/Untitled%202.png)

$$
Area=\frac{1}{6}\left| \left |\begin{array}{}      x_{1} &y_{1}   & z_{1} &1 \\
x_{2} &y_{2} & z_{2} &1  \\
x_{3} &y_{3} & z_{3} &1 \\x_{4} &y_{4} & z_{4} &1
\end{array}\right|  \right|
$$


✅ **Find coplanar**



$$
\left| \left |\begin{array}{}      x_{1} &y_{1}   & z_{1} &1 \\
x_{2} &y_{2} & z_{2} &1  \\
x_{3} &y_{3} & z_{3} &1 \\x_{4} &y_{4} & z_{4} &1
\end{array}\right|  \right|=0
$$


💡 **Thm Cramer’s Rule**



$$
x_{1}=\frac{det(A_{1})}{det(A)}, x_{2}=\frac{det(A_{2})}{det(A)} \dots,x_{n}=\frac{det(A_{n})}{det(A)}
$$

```python
def det(m):
    if len(m)<=0:
        return None
    if len(m)==1:
        return m[0][0]
    else:
        total=0
        for i in range(len(m)):
            tmp=[[row[j] for j in range(len(m)) if i!=j] for row in m[1:]]
            if i%2==0:
                total += det(tmp)*m[0][i]
            else:
                total -= det(tmp)*m[0][i]
        return total
n=int(input())
A=[]
for i in range(n):
    A.append([int(j) for j in input().split()])
Coffient=[list(i) for i in zip(*A)]
b=Coffient[-1]
Coffient=Coffient[0:n]
x=0
wa=[]
for i in range(n):
    C=[row for row in Coffient]
    C[x]=b
    try:
        print(det(C)/det(Coffient))
    except:
        wa.append(det(C))
    x+=1
flag=1
if det(Coffient)==0:
    for i in wa:
        if i!=0:
            print("No solution")
            flag=0
            break
    if flag:
        print("Too many")
```

