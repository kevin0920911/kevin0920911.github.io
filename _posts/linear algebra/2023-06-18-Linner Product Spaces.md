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



# Vector Length and Unit Vector


**Def Length of vector in $R^n$**

if $v=(v_1,v_2,\dots,v_n)$ and

$\left|\left|v\right|\right|$$=\sqrt{v_1^2+v_2^2\dots+v_n^2}$

if $\left|\left|v\right|\right|=1$ , then v is unit vector


**Def Length of a Scalar Multiple**

$\left|\left|cv\right|\right|=c\left|\left|v\right|\right|$


**Def Unit Vector**

$u=\frac{v}{\left|\left|v\right|\right|}$ has length 1



# Dot Product of $R^n$


**Def Dot Product**

$$
u\cdot v =u_1v_1+u_2v_2\dots+u_nv_n
$$


**Properties of Dot Product**

1. $u\cdot v=v\cdot u$
2. $u \cdot(v+w)=u\cdot v+u\cdot w$
3. $c(u\cdot v)= (cu) \cdot v =u \cdot(cv)$
4. $v \cdot v =\left|\left| v^2\right|\right| \geq 0$ 

5. if  $v \cdot v=0$ if and only if v=0

# Between two vector…

**Def Distance Between Two Vector**

[https://www.geogebra.org/calculator/nxfx2qxt?embed](https://www.geogebra.org/calculator/nxfx2qxt?embed)

$$
d(u,v)=\left|\left|v-u\right|\right|
$$

**Def Angle Between Two Vector**

$$
cos\theta= \frac{u\cdot v}{\left|\left|u\right|\right|\left|\left|v\right|\right|}
$$

if  $u\cdot v=0$ ortjgonal



# Inquality


**Thm The Cauchy-Schwarz Thm**

$$
\left|u\cdot v\right| \leq\left|\left|u\right|\right| \left|\left|v\right|\right|
$$

when equal is true, $cos\theta =1$ 


**Thm The Triangle Inquality**

$$
\left|\left|u+ v\right| \right| \leq\left|\left|u\right|\right| +\left|\left|v\right|\right|
$$

when equal is true, $u\cdot v\geq0$



# Lnner Product


**Def Lnner Product**

Lnner Product is a fuction and it is satisfied with below condition

1. $\left<u,v \right>=\left<v,u \right>$
2. $\left<u,v+w \right>=\left<u,v \right>+\left<u,w \right>$
3. $c\left<u,v \right>=\left<cu,v\right>$
4. $\left<v,v \right> = 0$   if and only if $v=0$



**Def length, Distance, Angle**

1. Length: $\sqrt{\left<v,v \right>}$
2. Distance: $\left|\left|u-v \right|\right|$
3. Angle: $cos\theta=\frac{\left<u,v \right>}{\left|\left|v\right|\right|\left|\left|u\right|\right| }$
4. Orthogonal: $\left<u,v \right> =0$

**Thm Inquality**

1. Cauchy-Schwarz: $\left|\left<u,v\right>\right| \leq\left|\left|u\right|\right| \left|\left|v\right|\right|$
2. Triangle: $\left|\left|u+ v\right| \right| \leq\left|\left|u\right|\right| +\left|\left|v\right|\right|$

**Def** **Projection**

$Proj_vu=\frac{\left<u,v\right>}{\left<v,v\right>}v$

**ps** $d(u,proj_vu)=d(u,cv)$ $c \ne \frac{\left<u,v \right>}{\left<v,v \right>}$


# Orthonormal Bases


**Def Orthonormal Bases**

For $S=\{v_1,v_2 \dots v_n\}$ is an inner product space

### Orthogonal

$\left< v_i,v_j\right>=0\space\space\space\space\space\space i\ne j$

### Orthonormal

$\left< v_i,v_j\right>=0\space\space\space\space\space\space i\ne j$

$\left|\left| v_i\right|\right| = 1\space\space\space\space\space\space\space\space\space\space i=1,2 \dots n$


**Thm Orthonormal Bases Set are Linearly Independent**

$S=\{v_1,v_2 \dots v_n\}$ is Orthonormal Bases then vector in S are Linearly Independent




**Thm Corollary**

If V is an inner product space, and $dim(V)=n$, then any orthogonal set of n nonzero vector is basis for V


**Thm Coordinates Relative to an Orthonormal Basis**

If $B=\{ v_1,v_2\dots ,v_n\}$ is an **Orthonormal Basis,** then the cordinate representation of vector w relative to B is

$$
w=\left<w,v_1\right>v_1+\left<w,v_2\right>v_2+ \dots+ \left<w,v_n\right>v_n
$$

In Short

$$
\left[x\right]_B=\left[\left<w,v_1\right>,\left<w,v_2\right> \dots \left<w,v_n\right>\right]^T
$$



# Gram-Schmidt Orthonormal Process

> 炫哥說必考，謝謝濃眉毛
> 

**Thm Gram-Schmidt Orthonormal Process**

1. Let $B=\{v_1,v_2 \dots v_n\}$ be a basis for an inner product space V
2. Let $B^{'}=\{w_1,w_2 \dots w_n\}$ where
    
    $$
    w_1=v_1\\w_2=v_2-\frac{\left<v_2,w_1\right>}{\left<w_1,w_1\right>}w_1\\ w_3=v_3-\frac{\left<v_3,w_1\right>}{\left<w_1,w_1\right>}w_1-\frac{\left<v_3,w_2\right>}{\left<w_2,w_2\right>}w_2\\ \vdots
    $$
    
    <aside>
    **背法**
    
    1. $w_1=v_1$
    2. $w_2=v_2-proj_{w_1}v_2$
    3. $w_3=v_3-proj_{w_2}v_3-proj_{w1}v_3$
    
                              $\vdots$
    
    1. $w_n=v_n-\sum_ { k= 1 } ^ { k-1 } proj_{w_k}v_n$ 
    </aside>
    
3. let w become unit vector


# Least Square Analysis


**Least Square Analysis**

Find the minimied of the distance (L to all point)


**Def Orthogonal Subspaces**

$S_1 ,S_2$ are orthogonal when $v_1 \sdot v_2=0$ where $v_1 \in S_1 \space\space\space\space v_2 \in S_2$ 


**Def Orthogonal Complement**

The Orthogonal Complement of S: $S^{\perp}=\{u\in R^n:v\sdot u=0  \space\space\forall v\in S \}$


**Def Direct Sum**

Let $S_1 ,S_2$  is subsapce of $R^n$. If each vector $x\in R^n$ can br uniquely,                  $x= s_1+s_2 \space \space \space \space s_1\in S_1 \space\space \space \space  s_2\in S_2$ , then $R^n$  is the direct sum of $S_1$  and $S_2$ 

**Notion:** $R^n =S_1 \oplus S_2$



**Thm Properties of Orthogonal Subspaces**

1. $dim(S)+dim(S^{\perp})=n$
2. $R^n = S \oplus S^{\perp}$
3. $(S^{\perp})^{\perp}=S$

**Thm Projection of Subspace**

Subspace $S=\{ u_1,u_2\dots ,u_n\}$  is orthgonal basis to subspace of $R^n$ then given a vector $v\in R^n$

$$
proj_Sv=\sum_{i=1}^n (v\sdot u_i)u_i
$$

**Distance**

$\left|\left| v-proj_Sv\right|\right| < \left|\left| v-u\right|\right|$



**Fundamental Subspaces of a Matrix**

$$
N(A)=nullspaces of A\\R(A)=column space of A
$$


📢 **Thm Fundamental Subspaces of a Matrix**

A is $m*n$ martrix then

1. $R(A)$  and $N(A^T)$ are orthogonal subspace of $R^m$
2. $R(A)$  and $N(A^T)$ are orthogonal subspace of $R^n$
3. $R(A) \oplus N(A^T) =R^m$
4. $R(A^T) \oplus N(A) =R^n$

⭐ **Least Square Analysis**

**一次回歸:** 

A 是帶入$y=c_0+c_1x$ 的係數矩陣, b是全部y軸的矩陣 : 解$A^TAx=A^Tb$

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
def Mul(A,B):
    Ans=[[0]*len(B[0]) for i in range(len(A))]
    for i in range(len(A)):
        for j in range(len(A[0])):
            for k in range(len(B[0])):
                Ans[i][k]+=A[i][j]*B[j][k]
    return Ans
n=int(input())
A=[]
for i in range(n):
    A.append([int(i) for i in input().split()])
B=[[0]*2 for i in range(n)]
C=[[0] for i in range(n)]
for i in range(n):
    B[i][0]=1
    B[i][1]=A[i][0]
    C[i][0]=A[i][1]    
BT=[list(i) for i in zip(*B)]
BBT=Mul(BT,B)
newC=Mul(BT,C)
for i in range(len(BBT)):
    BBT[i].append(newC[i][0])
if Cramer(BBT)[1]>=0:
    print("y=",Cramer(BBT)[0],"x +",Cramer(BBT)[1],end="")  
else:
    print("y=",Cramer(BBT)[0],"x ",Cramer(BBT)[1],end="")
```

**二次回歸:**

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
def Cramer(argumentMartix):
    Transpose=[list(j) for j in zip(*argumentMartix)]
    A=copy.deepcopy(Transpose[0:len(Transpose)-1])
    b=copy.deepcopy(Transpose[-1])
    Ans=[]
    for i in range(len(Transpose)-1):
        a=copy.deepcopy(A)
        a[i]=copy.deepcopy(b)
        Ans.append(det(a)/det(A))
    return Ans
def Mul(A,B):
    row1,col1,col2=len(A),len(A[0]),len(B[0])
    tmp=[[0]*col2 for i in range(row1)]
    for i in range(row1):
        for j in range(col1):
            for k in range(col2):
                tmp[i][k]+=A[i][j]*B[j][k]
    return tmp
n=int(input())
A=[]
for i in range(n):A.append([int(i) for i in input().split()])
A=[list(i) for i in zip(*A)]
B=[]
for i in A[0]:
    B.append([1,i,i**2])
BBT=Mul([list(j) for j in zip(*B)],B)
BTC=Mul([list(j) for j in zip(*B)],[[int(j)] for j in A[1]])
for i in range(3):
    BBT[i].append(BTC[i][0])
print(Cramer(BBT))
```

