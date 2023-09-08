---
title: "Vector Space"
subtitle: "Vector Space"
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

# Vector in $R^n$

 
**Vector in $R^n$**

$R^n =$ n-space $=$ **n-tuple : $(x_1,x_2,x_2\dots,x_n)$**

 
**Vector Operation**

Let $u=(u_1,u_2\dots,u_n)$      $v=(v_1,v_2\dots,v_n)$ 

1. addition 

$ u+v=(u_1+v_1,u_2+v_2\dots,u_n+v_n) $

1. scalar multiplication
 
$$
cu=(cu_1,cu_2\dots,cu_n)
$$

 
 
**Def Linear Combination of Vector**

Both x and v is vector, c is scale

$$
x=c_1v_1+c_2v_2\dots+c_nv_n
$$

 
# Vector Spaces

 
**Def** **Vector Spaces**

1. Let V be a set 
2. If the listed axioms are satisfied for all operation 

### Addition

1. $u+v$ in V 
2. $u+v=v+u$
3. $u+(v+w)=(u+v)+w$
4. V has 0 vector($u+0=u\space \space \space \space   \forall u\in V$)
5. $u+(-u)=0 \space\space\space \forall u\in V$

### Scalar

1. $cu \in V$
2. $c(u+v)=cu+cv$
3. $(c+d)u=cu+du$
4. $c(du)=cd(u)$
5. $1u=u$

 
**Anyway 農眉毛說證明最多只考反證明**

 
 
# Subspaces of Vector Spaces

 
**Def Subspaces of Vector Spaces**

1. **Subspace**: W
2. **Vector**: V
3. W if a vector space under the operation of **scalar** and **addition** define by V

 
**Test for Subspaces**

1. if $u,v \in W$ $u+v \in W$
2. if $u \in W$ and c is scalar, then $cu \in W$
 
 
**Intersection of Two subspaces is a subspace**

兩個subspace的交集還是會在V內

$V \cap W\in V $
 
 
 
**Subspace in $R^n$**

 
1️⃣ $R^2$

1. W consist of single point (0,0)
2. W consist all points on a line that process through the origin 
3. W consists of all of $R^2$
 
 
2️⃣ $R^3$

1. W consist of single point (0,0,0)
2. W consist all points on a line that process through the origin 
3. W consists of all of $R^2$
 
 
# Spanning set

 
**Def Spanning set of Vector space**

Set S 任一種組合向量皆可表示成V中每一個向量 **(call S span V)**

 
**用數學的方式表達**

$S=\{ v_1,v_2,\dots,v_n\}$  is a set of vector 

$span(S)=\{ c_1v_1+c_2v_2+ \dots + c_nv_n\}$

when $span(S)=V$, it is said that **V is spaned by S**

 
 
# Linear Independence

 
**Def Linear independece**

$c_1v_1+c_2v_2+ \dots + c_nv_n=0$

1. **Trivial Solution :** Linear independece
2. **Nontrivial Solution :** Linear dependece

 
**Thm A property of Linear Dependent Sets**

Set S is linear dependent if and only if one of vector can be written as a linear combination of other vectors in S

 
**Corollary**

1. Two vector u and v is in vector space
2. Both of them are linear dependent 
3. **A scalar multiple of the other**
 
 
 
# Basis and Dimension

 
**Def Basis**

set of vector $S=\left\{ v_1,v_2,\dots , v_3 \right\}$ in vector space V is basis for V when the conditions below are true

1. S span V
2. S is linearly independent

 
**Thm Uniqueneaa of Basis Representation**

1. S is basis in V
2. V is vector spaces

Every vector in V can be writen in one way as linear combination of vector S

 
 
**Thm  Bases and Linear Dependence**

1. S is basis in V  ($S=\left\{ v_1,v_2,\dots , v_3 \right\}$)
2. V is vector spaces

Every set containing more than n vectors in V is **linearly dependent**

 
 
**Thm Number of Vectirs in a Basis**

If vector space V has one basis with n vectors, then every basis for V has n vectors. 

**Notion: $dim(V)=n$**

 
**常見向量空間整理**

1. $R^n$ -> n
2. $P_n$-> n+1
3. $M_{m,n}$ -> m*n


 
 
 
**Thm Test for Basis for n-dim Space**

Let V is vector space, and $dim(V)=n$

1. If  $S=\left\{ v_1,v_2,\dots , v_n \right\}$ is linear independent set of Vector in V, then S is basis for V
2. If   $S=\left\{ v_1,v_2,\dots , v_n \right\}$ spans V ,then S is basis for V
 
 
# Row-Space , Col-Space ,rank

 
**Def row & col space**

Let A be a $m*n$ matrix

1. The row space of **A is the subspace of $R^n$** spanned by row vector of A
2. The col space of **A is the subspace of $R^m$** spanned by col vector of A

 
**Thm Row-Equivalent**

 If an $m*n$ matrix A is row-equivalent to an $m*n$ matrix B, then the row space of A is equal to row space of B.

 
 
**Thm Basis for the Row Space of Matrix**

1. $A \rightarrow B(row-echelon form)$
2. Nonezero row vector of B is a basis form row-space of A (**subspace of $R^n$**)
 
 
**Thm Row Space and Col Space Have equal Dim**

$dim(row-space)=dim(col-space)$

 
 
**Def Rank**

$dim(row-space)=dim(col-space)= rank(A)$

 
 
# NullSpace

 
**Def Nullspace**

The solution of linear equation $Ax=0$ is the subspace of $R^n$ called **nullspace** of A (Notion: $N(A)$)

$$
N(A)=\left\{  x\in R^n: Ax=0  \right\}
$$

The dimension of the nullspace of A is nullity of A

 
**Thm Dimension of the Solution Space**

If A is $**m*n$**  martix rank r

$$
n=rank(A)+nullity(A)
$$

 
 
# Solution of Linear Equations

 
**Thm Solution of Nonhomogenwous Linear Systeam**

1. $x_p$ is a particular solution of nonhomogeneous system $Ax=b$
2. $x_h$  is the solution of homogeneous system $Ax=0$

Then 

$$
x=x_h+x_p
$$

 
**Thm Solution of a System of Linear Equation**

The system $Ax=b$ is consistent $\leftrightarrow$ **b is the col space of A**

 
 
# Coordinate Representaion in $R^n$

 
**Def Coordinate Representation Relative to a Basis**

Let $B=\left\{ v_1,v_2 \dots , v_n\right\}$ be an ordered basis for a vector space V and let $x\in V$

$$
x=c_1v_1+c_2v_2\dots+c_nv_n
$$

The scalars $c_1, c_2\dots c_n$ are the coordinates of x relative to the basis B

$$
[x]_B=\begin{bmatrix}
c_1\\c_2\\c_3 \\ \vdots \\ c_n
\end{bmatrix}
$$

 
# Change of Basis in $R^n$

 
**Thm the Inverse of Transition Matrix**

**Transition matrix from $B$ to $B'$:  $P^{-1}$**

**Transition matrix from $B'$ to $B$:  $P$**

$$
P[x]_{B'}=[x]_{B} \rightarrow [x]_{B'}=P^{-1}[x]_{B} 
$$

 
 **Thm Transition Matrix from $B$ to $B'$**

1. **USE GAUSS-JORDAN ELIMINATION**
2. $[B'\space\space\space |\space\space\space B]  \space\rightarrow\space [I\space\space\space|\space\space\space P^{-1}]$

 
 
**Code Change of Basis in $R^n$**

```python
import copy
def det(m):
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
def Cramer(m):
    M=[list(j) for j in zip(*copy.deepcopy(m))]
    Ans=[]
    b=M[-1]
    A=M[:len(M)-1]
    x=0
    while x<len(M)-1: 
        tmp=copy.deepcopy(A)
        tmp[x]=b
        Ans.append(det(tmp)/det(A))
        x+=1
    return Ans
n=int(input())
A=[]
B=[]
for i in range(n): 
    A.append([int(j) for j in input().split()])
for i in range(n): 
    B.append([int(j) for j in input().split()])
Ans=[]
B=[list(j) for j in zip(*B)]
for j in A:
    x=0
    ArgumentMartix=[]
    for i in B:
        ArgumentMartix.append(copy.deepcopy(i))
        ArgumentMartix[x].append(j[x])
        x+=1
    Ans.append(Cramer(ArgumentMartix))
for i in Ans:
    for j in i:
        print(j,end=" ")
    print()
```

 
